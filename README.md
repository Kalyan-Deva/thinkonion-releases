# ThinkOnion releases

Installers for ThinkOnion, a local-first notes app. The source code is private; this repo only holds signed releases, so the app's built-in updater can download them.

## Install

Download the latest `ThinkOnion_<version>_x64-setup.exe` from [Releases](../../releases/latest) and run it. The installer isn't code-signed yet, so Windows SmartScreen asks first: choose **More info → Run anyway**.

## How updates are checked

Every installer carries two signatures, and the app installs an update only if both verify:

- **Ed25519** (`<installer>.sig`): checked by the updater while downloading.
- **ML-DSA-65** (post-quantum, the `mldsa65` field in `latest.json`): signs `thinkonion-release/v1|<version>|<SHA-256 of the installer>` and is checked before installing.

Both public keys are built into the app. `SHA256SUMS` lists each installer's hash.
