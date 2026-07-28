# setup-vcpkg-cache

Prepare a vcpkg checkout and cache its binary packages. Cache keys include runner OS and architecture, vcpkg commit, manifest, overlay-port contents, and
workflow run. Each run restores the nearest compatible cache and saves rebuilt packages under a new key.

## Usage

```yaml
- name: Setup vcpkg cache
  uses: actions-ext/cpp/setup-vcpkg-cache@main
```

## Inputs

| Name               | Default                                  | Description                            |
| :----------------- | :--------------------------------------- | :------------------------------------- |
| `cache_key`        | `vcpkg`                                  | Additional vcpkg cache key.            |
| `manifest`         | `vcpkg.json`                             | Path to vcpkg manifest.                |
| `overlay_ports`    | `vcpkg-overlays`                         | Path to overlay ports.                 |
| `vcpkg_ref`        | Empty                                    | Optional vcpkg branch, tag, or commit. |
| `vcpkg_repository` | `https://github.com/microsoft/vcpkg.git` | vcpkg Git repository.                  |
| `vcpkg_root`       | `vcpkg`                                  | Path to vcpkg checkout.                |

## Outputs

| Name             | Description                                       |
| :--------------- | :------------------------------------------------ |
| `cache-hit`      | Whether an exact binary-cache entry was restored. |
| `vcpkg-revision` | Resolved vcpkg commit used in the cache key.      |
