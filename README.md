![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/gaofengnan/unregistry-debian/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/gaofengnan/unregistry-debian/latest/total)
![GitHub Release](https://img.shields.io/github/v/release/gaofengnan/unregistry-debian)
![GitHub Release Date](https://img.shields.io/github/release-date/gaofengnan/unregistry-debian)

<h1>
   <p align="center">
     <a href="https://unregistry.org/"><img src="https://github.com/gaofengnan/unregistry-debian/blob/main/unregistry-logo.png" alt="unregistry Logo" width="128" style="margin-right: 20px"></a>
     <a href="https://www.debian.org/"><img src="https://github.com/gaofengnan/unregistry-debian/blob/main/debian-logo.png" alt="Debian Logo" width="104" style="margin-left: 20px"></a>
     <br>unregistry for Debian
   </p>
</h1>
<p align="center">
 Unregistry is a lightweight container image registry that stores and serves images directly from your Docker daemon's storage.
</p>
<p align="center">
The included docker pussh command (extra 's' for SSH) lets you push images straight to remote Docker servers over SSH. It transfers only the missing layers, making it fast and efficient.
</p>
# unregistry for Debian

> Fork of [dariogriffo/unregistry-debian](https://github.com/dariogriffo/unregistry-debian) (MIT); the original packaging is by Dario Griffo. Served at [deb.gaofn.xyz](https://deb.gaofn.xyz) for Debian 12 (bookworm) and 13 (trixie).

This repository contains build scripts to produce the _unofficial_ Debian packages
(.deb) for [unregistry](https://github.com/psviderski/unregistry/) hosted at [deb.gaofn.xyz](https://deb.gaofn.xyz)

Currently supported Debian distros are:
- Bookworm (v12)
- Trixie (v13)
- Forky (v14)
- Sid (testing)

Currently supported Ubuntu distros are:
- Jammy (22.04)
- Noble (24.04)
- Questing (25.10)
- Resolute (26.04)

Supported architectures:
- amd64 (x86_64)
- arm64 (aarch64)

`unregistry` is built from the upstream tag with Go, so those are the two
architectures cross-compiled here. `docker-pussh` is a bash script and ships
as a single `Architecture: all` package that installs on any architecture.

This is an unofficial community project to provide a package that's easy to
install on Debian. If you're looking for the unregistry source code, see
[unregistry](https://github.com/psviderski/unregistry/).

## Install/Update

### The Debian way

```sh
sudo install -d -m 0755 /etc/apt/keyrings
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.gpg -o /etc/apt/keyrings/deb.gaofn.xyz.gpg
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.sources -o /etc/apt/sources.list.d/deb.gaofn.xyz.sources
# Debian 12 (bookworm): fetch deb.gaofn.xyz-bookworm.sources instead
sudo apt update
sudo apt install -y unregistry
sudo apt install -y docker-pussh
```

### Manual Installation

1. Download the .deb package for your Debian version available on
   the [Releases](https://github.com/gaofengnan/unregistry-debian/releases) page.
2. Install the downloaded .deb package.

```sh
sudo dpkg -i <filename>.deb
```
## Updating

To update to a new version, just follow any of the installation methods above. There's no need to uninstall the old version; it will be updated correctly.

## Roadmap

- [x] Produce a .deb package on GitHub Releases
- [x] Set up a debian mirror for easier updates

## Disclaimer

- This repo is not open for issues related to unregistry. This repo is only for _unofficial_ Debian packaging.
