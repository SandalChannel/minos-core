# MinOS Core Image

Containerfile for building a MinOS/VanillaOS Core image.

This fork of the [Vanilla OS Core](https://github.com/Vanilla-OS/core-image) image uses the Debian Stable repository rather than Debian Sid.

> [!IMPORTANT]
> This image is not intended to be used directly. It is used as a base image for other images.
> Like the MinOS (DevX) Desktop and Nvidia images.

## Build

> [!NOTE]
> The fsguard compiled plugin `.so` file should be downloaded from the [latest release](https://github.com/Vanilla-OS/vib-fsguard/releases/latest) and be placed under a `plugins` directory beside the `recipe.yml` file.

```bash
vib build recipe.yml
podman image build -t sandalchannel/core .
```

## Verify Image Build Provenance Attestation

All the image builds/pushes are attested for build provenance and integrity using the [attest-build-provenance`](https://github.com/actions/attest-build-provenance) action. The attestations can be verified [here](https://github.com/Vanilla-OS/core-image/attestations) or by having the latest version of [GitHub CLI](https://github.com/cli/cli/releases/latest) installed in your system. Then, execute the following command:

```sh
gh attestation verify oci://ghcr.io/vanilla-os/core:main --owner Vanilla-OS
```
