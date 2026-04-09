# Install Skopeo Action

Installs Skopeo in GitHub Actions runner. Source: [https://github.com/containers/skopeo](https://github.com/containers/skopeo)

## Inputs

- `mode` (optional): Installation mode.
  - Leave empty for binary installation (default).
  - Use `build` to build Skopeo from source.
- `version` (optional): Skopeo version.
  - For binary installation: Leave empty for the latest `skopeo-v` tagged release from `jetsung/install-skopeo`. If a specific version is provided but not found, it falls back to the latest `skopeo-v` tagged release.
  - For source build: Leave empty for the latest stable release from `containers/skopeo`. Use `dev` or `master` to build from the respective branches of `containers/skopeo`.

## Example usage

### Binary Installation (Default)

```yaml
uses: jetsung/install-skopeo@v1
with:
  version: "1.21.0" # Install a specific binary version (e.g., skopeo-v1.21.0)
  # or omit version for the latest available binary
```

### Build from Source

```yaml
uses: jetsung/install-skopeo@v1
with:
  mode: 'build'
  version: "1.21.0" # Build a specific version (e.g., v1.21.0 tag from containers/skopeo)
  # or omit version for the latest stable build from source
  # or use version: 'master' for the latest development version from source
```
