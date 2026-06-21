# silverblue-surface &nbsp; [![bluebuild build badge](https://github.com/thattransgal/silverblue-surface/actions/workflows/build.yml/badge.svg)](https://github.com/thattransgal/silverblue-surface/actions/workflows/build.yml)

This is a bluebuild workflow for building a fedora silverblue image with the surface-linux kernel preinstalled and used as the default kernel.

## Installing

Install the base Fedora Silverblue iso, OR download one of the premade isos linked [here]()

If you chose to use the fedora silverblue iso route then you will need to rebase, to rebase follow the steps below.

To rebase an existing atomic Fedora installation to the latest build:

- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/thattransgal/silverblue-surface:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/thattransgal/silverblue-surface:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```


  To install from a premade iso download the iso from the link above and follow the install prompts.
