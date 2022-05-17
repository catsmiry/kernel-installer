# kernel-installer
Automatic install script for [The Linux kernel](https://www.kernel.org)

Inspired by [LinuxKernelBuild](https://github.com/Angristan/LinuxKernelBuild)

[![GitHub release](https://img.shields.io/github/release/tmiland/kernel-installer.svg?style=for-the-badge)](https://github.com/tmiland/kernel-installer/releases)
[![licence](https://img.shields.io/github/license/tmiland/kernel-installer.svg?style=for-the-badge)](https://github.com/tmiland/kernel-installer/blob/master/LICENSE)
![Bash](https://img.shields.io/badge/Language-SH-4EAA25.svg?style=for-the-badge)

### Script to install the latest [stable/mainline/longterm] kernel from source on Debian-based distributions, for all architectures.

### Dependencies

Will be installed when running script.
```bash
wget curl git rsync fakeroot build-essential ncurses-dev xz-utils libssl-dev bc liblz4-tool paxctl libelf-dev flex bison
```

### Download the script:

Quick install with default options:

With Curl:
```bash
curl -sSL https://github.com/tmiland/kernel-installer/raw/main/kernel_installer.sh | bash || exit 0
```
With Wget:
```bash
wget -qO - https://github.com/tmiland/kernel-installer/raw/main/kernel_installer.sh | bash || exit 0
```

For latest release

```bash
curl -s https://api.github.com/repos/tmiland/kernel-installer/releases/latest \
| grep "browser_download_url.*sh" \
| cut -d : -f 2,3 \
| tr -d \" \
| wget -qi -
```

For main branch
```bash
wget https://github.com/tmiland/kernel-installer/raw/main/kernel_installer.sh
```

Set execute permission:
```bash
chmod +x kernel_installer.sh
```
For usage, run:
```bash
./kernel_installer.sh -h
```

Watch install log:
```bash
tail -f ./kernel_installer.log
```

- installation log in kernel_installer.log
- [./src/slib.sh](https://github.com/tmiland/kernel-installer/blob/main/src/slib.sh) function script is sourced remotely if not found locally
  - This script is a combination of functions for spinners, colors and logging
    - Source: Spinner: [swelljoe/spinner](https://github.com/swelljoe/spinner)
    - Source: Run ok: [swelljoe/run_ok](https://github.com/swelljoe/run_ok)
    - Source: Slog: [swelljoe/slog](https://github.com/swelljoe/slog)
    - Source: Slib: [virtualmin/slib](https://github.com/virtualmin/slib)

***Note: you will need to run this script as root***

If root password is not set, type:

```bash
sudo passwd root
```

Then:

```bash
su root
```

## Testing

Tested and working on: Debian 11

## Feature request and bug reports
- [Bug report](https://github.com/tmiland/kernel-installer/issues/new?assignees=tmiland&labels=bug&template=bug_report.md&title=Bug-report:)
- [Feature request](https://github.com/tmiland/kernel-installer/issues/new?assignees=tmiland&labels=enhancement&template=feature_request.md&title=Feature-request:)

## Donations
<a href="https://www.buymeacoffee.com/tmiland" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
- [PayPal me](https://paypal.me/milanddata)
- [BTC] : 33mjmoPxqfXnWNsvy8gvMZrrcG3gEa3YDM

## Web Hosting

Sign up for web hosting using this link, and receive $100 in credit over 60 days.

[DigitalOcean](https://m.do.co/c/f1f2b475fca0)

#### Disclaimer 

*** ***Use at own risk*** ***

### License

[![MIT License Image](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0c/MIT_logo.svg/220px-MIT_logo.svg.png)](https://github.com/tmiland/kernel-installer/blob/master/LICENSE)

[MIT License](https://github.com/tmiland/kernel-installer/blob/master/LICENSE)