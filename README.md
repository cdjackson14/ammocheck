# AmmoCheck

This checks several online sources for availability of 9mm ammo, then emails out the result.

This was originally created in 2020 when ammo became hard to find in stock.

## Required Items

* curl  - Normally already installed, if not see below
* sSMTP - https://wiki.debian.org/sSMTP

On most Debian systems, install with:

```bash
sudo apt install ssmtp
sudo apt install curl
```

