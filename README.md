# Sentra Works

Sentra Works is a desktop workspace for coding agents (Claude Code and Codex), with Workspaces,
Tasks, Calendar and Meetings, Forge proposals, Sentra Slides, and Gateways to your other
computers.

This repository holds Sentra Works releases: the app, Sentra Works Gateway, and theme packs.
**[Download the latest release](https://github.com/OmarSultan85/sentra-works-releases/releases/latest).**

## Install the app

Open the latest release and download the file for your computer from its **Assets**:

| Computer               | File                                     |
| ---------------------- | ---------------------------------------- |
| Mac with Apple silicon | `Sentra-Works-<version>-arm64.dmg`       |
| Mac with Intel         | `Sentra-Works-<version>-x64.dmg`         |
| Windows (x64)          | `Sentra-Works-<version>-x64.exe`         |
| Linux (x64)            | `Sentra-Works-<version>-x86_64.AppImage` |

Forge, Sentra Slides, and Computer use need a Mac with Apple silicon.

Until the installers are signed:

- **macOS:** the first time you open Sentra Works, macOS refuses it. Open **System Settings →
  Privacy & Security** and choose **Open Anyway**. If macOS says the app is damaged, run
  `xattr -dr com.apple.quarantine "/Applications/Sentra Works.app"` once. To update, download the
  new DMG.
- **Windows:** SmartScreen warns about the installer. Choose **More info → Run anyway**.
- **Linux:** make the AppImage executable (`chmod +x Sentra-Works-*.AppImage`) and run it.

## Install Sentra Works Gateway

A gateway is another computer you control that runs Sentra Works Gateway, linked to the app on
the computer you work on. Run the installer on the gateway computer, as your normal user (not
root or an administrator).

macOS and Linux:

```bash
curl -fsSL https://github.com/OmarSultan85/sentra-works-releases/releases/latest/download/install.sh | sh
```

Windows (PowerShell):

```powershell
irm https://github.com/OmarSultan85/sentra-works-releases/releases/latest/download/install.ps1 -OutFile install.ps1
powershell -ExecutionPolicy Bypass -File .\install.ps1
```

The installer downloads the gateway package for that computer from the same release and checks
it against `SHA256SUMS` before installing. To install by hand, download your computer's
`sentra-gateway-<version>-<os>-<arch>` package, `SHA256SUMS`, and `install.sh` or `install.ps1`
into one folder, then run `sh install.sh --package ./sentra-gateway-<version>-<os>-<arch>.tar.gz`
(on Windows, `install.ps1 -Package .\sentra-gateway-<version>-win32-<arch>.zip`). Then, in Sentra
Works, open **Settings → Gateways** to link it.

## Theme packs

Each release attaches theme packs (`*.sentra-theme.json`, and all of them in
`sentra-works-theme-packs-<version>.zip`). In Sentra Works, open **Settings → Appearance**, choose
**Import file…**, and pick a pack.

## Check a download

Every release lists the SHA-256 of each file in `SHA256SUMS`. In the folder holding your
downloads and `SHA256SUMS`:

```bash
shasum -a 256 --check --ignore-missing SHA256SUMS   # macOS
sha256sum --check --ignore-missing SHA256SUMS       # Linux
```

## License

Sentra Works is released under the MIT license, which also carries the copyright notices of the
projects it derives from; see [LICENSE](LICENSE).
