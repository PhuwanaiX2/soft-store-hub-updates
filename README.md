# Soft Store Hub Updates

Public update channel for Soft Store Hub.

## Files

- `update_manifest.json` is the launcher update manifest.
- Release assets contain the actual Windows executable packages.
- GitHub Pages serves the manifest at `https://phuwanaix2.github.io/soft-store-hub-updates/update_manifest.json`.

## Release Checklist

1. Update `AppInfo.CurrentVersion` in the launcher code.
2. Build `Soft Store Hub.exe`.
3. Rename the release asset, for example `SoftStoreHub-1.2.2.exe`.
4. Calculate SHA256:

   ```powershell
   Get-FileHash ".\SoftStoreHub-1.2.2.exe" -Algorithm SHA256
   ```

5. Create a GitHub Release tag such as `v1.2.2`.
6. Upload the exe asset to the release.
7. Update `update_manifest.json` with the new version, download URL, SHA256, and changelog.

The launcher accepts only HTTPS update URLs and verifies SHA256 before replacing itself.
