# Doki Releases

This repository hosts public, versioned Doki app and guest image releases. The
application source code and development instructions are in the
[Doki source repository](https://github.com/thienle99-dev/doki).

## Download

Open [Releases](https://github.com/thienle99-dev/doki-release/releases) and
choose a published version. Each release is expected to include:

- `Doki-<version>-macos-arm64.zip` — Doki for macOS 15 or later on Apple
  silicon.
- `doki-guest-aarch64.img.gz` — the compressed ARM64 guest disk image.
- `guest-release.json` — signed metadata that authenticates the guest image
  and describes its compatibility.

The app checks the manifest signature and the SHA256 digest of the downloaded
image before installing it. The compressed artifact digest and the expanded
disk image digest are both covered. Use the app's built-in bootstrap flow to
install a guest image; do not install an image from an unrelated source.

## Release integrity

Only use assets attached to a published release in this repository. The app
contains the trusted Ed25519 public key used to verify `guest-release.json`.
The signing private key is maintained as a protected GitHub Actions secret and
must never be published here.

Release tags use semantic versions such as `v1.2.3`. Draft releases may be used
while assets are being prepared; wait until a release is published before
downloading its assets.

## Source and support

- Source code: [thienle99-dev/doki](https://github.com/thienle99-dev/doki)
- Issues and development: [Doki issues](https://github.com/thienle99-dev/doki/issues)
