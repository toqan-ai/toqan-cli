# toqan-cli

Public release artifacts for the Toqan OS CLI.

Source code lives in a private repository. This repository only hosts versioned
binaries, checksums, and license files. It does not accept contributions.

## License

The binaries are licensed under the terms in [LICENSE](LICENSE).

The binaries contain open-source software. [THIRD_PARTY_LICENSES](THIRD_PARTY_LICENSES)
lists each module with its version, license, copyright holders, and a link to
the license text. Each release also ships its own `THIRD_PARTY_LICENSES` asset,
which is the record for that version.

## Install

Each release has four binaries, `SHA256SUMS`, and `THIRD_PARTY_LICENSES`.
`SHA256SUMS` covers the binaries only. The binary names have no version.

The commands below install the latest
[release](https://github.com/toqan-ai/toqan-cli/releases) for macOS on Apple
silicon. They download the binary, check it against `SHA256SUMS`, and install it
on your `PATH`:

```sh
curl -fsSL -O https://github.com/toqan-ai/toqan-cli/releases/latest/download/toqan_darwin_arm64
curl -fsSL -O https://github.com/toqan-ai/toqan-cli/releases/latest/download/SHA256SUMS
grep ' toqan_darwin_arm64$' SHA256SUMS | shasum -a 256 -c -
sudo install -m 755 toqan_darwin_arm64 /usr/local/bin/toqan
toqan version
```

On Linux, use `sha256sum -c -` in place of `shasum -a 256 -c -`. For another
platform, replace `darwin_arm64` with `darwin_amd64`, `linux_amd64`, or
`linux_arm64`.

To install a specific version, replace `latest/download` with
`download/vX.Y.Z`. Releases up to and including v0.6.0 use the file name
`toqan_<version>_<os>_<arch>`, for example `toqan_0.6.0_darwin_arm64`.
