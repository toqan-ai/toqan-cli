# toqan-cli

Public release artifacts for the Toqan OS CLI.

Source code lives in a private repository. This repository only hosts versioned
binaries and checksums.

## Install

Pick the asset for your OS and architecture from a
[release](https://github.com/toqan-ai/toqan-cli/releases), check
`SHA256SUMS`, and install the binary on your `PATH`:

```sh
curl -fsSL -O https://github.com/toqan-ai/toqan-cli/releases/download/v1.2.3/toqan_1.2.3_darwin_arm64
curl -fsSL -O https://github.com/toqan-ai/toqan-cli/releases/download/v1.2.3/SHA256SUMS
grep ' toqan_1.2.3_darwin_arm64$' SHA256SUMS | shasum -a 256 -c -
install -m 755 toqan_1.2.3_darwin_arm64 /usr/local/bin/toqan
toqan version
```

On Linux, use `sha256sum -c -` in place of `shasum -a 256 -c -`.

Replace `v1.2.3` / `1.2.3` and the `darwin_arm64` suffix with the release and
platform you need.
