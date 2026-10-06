# Publishing a release (maintainer notes)

Source code lives in the private repo `gyuv/OLD-MAC-BRO`. This public repo `gyuv/oldmacbro` holds only the README, `docs/assets/` and GitHub Releases.

## Layout

```
oldmacbro/                      ← public
├── README.md                   ← landing page
├── releases/README.md          ← points to the Releases tab (no binaries in git)
├── docs/
│   ├── assets/*.svg            ← illustrations copied from the private repo
│   └── PUBLISHING.md           ← this file
└── .github/ISSUE_TEMPLATE/     ← bug / feature forms
```

Binaries go on **GitHub Releases**, never in git: they bloat the history forever and files over 100 MB are rejected.

## Automatic (recommended)

In the private repo's `.github/workflows/release.yml`, publish to this repo instead of the source repo:

1. Create a fine-grained PAT with **Contents: Read and write** on `gyuv/oldmacbro` only.
2. Save it in the **private** repo as the secret `PUBLIC_REPO_TOKEN`.
3. Replace the "Publish GitHub Release" step with:

```yaml
      - name: Publish GitHub Release (public repo)
        env:
          GH_TOKEN: ${{ secrets.PUBLIC_REPO_TOKEN }}
        run: |
          cd dist
          shasum -a 256 OldMacBro-*.dmg > SHA256SUMS.txt
          gh release create "$TAG" OldMacBro-*.dmg SHA256SUMS.txt \
            --repo gyuv/oldmacbro \
            --title "OldMacBro $TAG" \
            --notes "Intel (x86_64) build for macOS 12+. The app is ad-hoc signed: on first launch, right-click OldMacBro.app and choose Open.

          SHA-256: $(cut -d' ' -f1 SHA256SUMS.txt)"
```

Drop `--target` and `--generate-notes`: the commit SHA and commit-based notes belong to the private repo and would leak its history. `gh` creates the tag in the public repo on its default branch.

Then `git tag v1.3.1 && git push origin v1.3.1` in the private repo.

## One-time: mirror existing releases (v1.0.0 to v1.3.0)

Releases v1.0.0 to v1.3.0 currently exist only in the private repo, so their links 404 for the public. Copy them here once, from a Mac with `gh` logged in as you:

```bash
for tag in v1.0.0 v1.1.0 v1.2.0 v1.2.1 v1.2.2 v1.2.3 v1.3.0; do
  dir=$(mktemp -d)
  gh release download "$tag" --repo gyuv/OLD-MAC-BRO --pattern '*.dmg' --dir "$dir"
  (cd "$dir" && shasum -a 256 *.dmg > SHA256SUMS.txt)
  gh release create "$tag" "$dir"/* --repo gyuv/oldmacbro \
    --title "OldMacBro $tag" \
    --notes "Intel (x86_64) build for macOS 12+. See CHANGELOG.md. On first launch, right-click OldMacBro.app and choose Open."
done
```

Create them oldest first (as above) so v1.3.0 ends up as **Latest**. Afterwards you can delete the private repo's releases, or keep them as a backup.

## Manual

1. Build: `./Scripts/build_dmg.sh` in the private repo.
2. Here: **Releases → Draft a new release**, tag `vX.Y.Z`, attach `OldMacBro-X.Y.Z.dmg` and its checksum, publish.

## Checklist

- [ ] Add the version to `CHANGELOG.md` and `releases/README.md`.
- [ ] Version badge updates itself (it reads the latest release).
- [ ] Copy changed `docs/assets/*.svg` from the private repo.
- [ ] Never commit source, `.entitlements`, scripts or tokens here.
