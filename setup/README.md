# setup

Configure a C++ toolchain for GitHub Actions:

- Activate MSVC on Windows.
- Install clang-format when unavailable.
- Configure ccache on Linux and macOS.
- Configure sccache and set `CC`/`CXX` for MSVC on Windows.

## Usage

```yaml
- name: Setup C++
  uses: actions-ext/cpp/setup@51c484ef64088c62434226039d0e3359f5fc8df6
```

## Inputs

| Name           | Default | Description                            |
| :------------- | :------ | :------------------------------------- |
| `cache`        | `true`  | Enable compiler caching.               |
| `cache_key`    | `cpp`   | Additional compiler cache key.         |
| `clang_format` | `true`  | Install clang-format when unavailable. |
| `msvc_arch`    | `x64`   | MSVC target architecture on Windows.   |
