# Nomatron QR

Generate light and dark PNG QR codes with the Nomatron emblem for any HTTP or HTTPS webpage. Generation runs offline; each QR code contains your original URL.

## Install

On macOS, after the first stable release:

```sh
brew install nomatronio/tap/nomatron-qr
```

Supports Apple Silicon and Intel Macs. Upgrade with `brew update && brew upgrade nomatron-qr`.

On Windows, download the AMD64 (x64) or ARM64 ZIP from [Releases](https://github.com/nomatronio/qr-code-gen-releases/releases), extract it, and run `nomatron-qr.exe` in PowerShell. You can add its directory to your PATH.

Every release includes SHA-256 hashes in `checksums.txt`. The archives include third-party licence notices under `licenses/`.

## Use

```sh
nomatron-qr https://nomatron.io
nomatron-qr https://nomatron.io/docs --output-dir ./qr-codes --name docs
nomatron-qr --size 2048 --force https://nomatron.io
```

In PowerShell, use `./nomatron-qr.exe` when running the executable from the current directory.

By default, the command writes `nomatron-qr-light.png` and `nomatron-qr-dark.png` in your current directory. Existing files are protected unless you pass `--force`.

| Flag | Short | Default | Purpose |
| --- | --- | --- | --- |
| `--output-dir` | `-o` | `.` | Output directory; created if needed |
| `--name` | `-n` | `nomatron-qr` | Output filename prefix |
| `--size` | `-s` | `1024` | Square PNG dimensions, 256–4096 pixels |
| `--force` | `-f` | `false` | Replace existing output files |
| `--help` | `-h` | | Show usage |
| `--version` | `-v` | | Show installed version |

Flags may appear before or after the URL. Quote URLs containing shell characters such as `&`.

The emblem sits alone in a clear square at the centre. Dark PNGs use inverted colours; use the light PNG for the broadest scanner compatibility. Preserve the outside quiet zone and check the code with your intended camera before printing.

These are static QR codes. To change a destination without regenerating a code, encode a URL you control and manage its redirect yourself.

This repository hosts public binaries and installation documentation. The application source is maintained privately.
