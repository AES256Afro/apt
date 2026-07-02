# VideoKidnapper APT repository

Signed APT repository serving [VideoKidnapper](https://github.com/AES256Afro/VideoKidnapper) `.deb` packages for Debian/Ubuntu-family distros (amd64).

## Install

One-time setup:

```bash
sudo install -d /etc/apt/keyrings
curl -fsSL https://aes256afro.github.io/apt/videokidnapper.asc | sudo tee /etc/apt/keyrings/videokidnapper.asc > /dev/null
echo "deb [signed-by=/etc/apt/keyrings/videokidnapper.asc] https://aes256afro.github.io/apt stable main" | sudo tee /etc/apt/sources.list.d/videokidnapper.list
sudo apt update
```

Then:

```bash
sudo apt install videokidnapper
```

Upgrades arrive through normal `sudo apt upgrade`.

## How this repo is maintained

Do not edit `dists/` or `pool/` by hand — the release workflow in the
[VideoKidnapper repo](https://github.com/AES256Afro/VideoKidnapper) regenerates and signs them
(`apt-ftparchive` + GPG) on every tagged release and pushes here via a deploy key.
See `packaging/deb/README.md` over there for the full pipeline.

Signing key fingerprint: `AE75 B3E7 AA43 FDC5 CDF2 AE58 3C3F 0BDB 03B3 3789`
