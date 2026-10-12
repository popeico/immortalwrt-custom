# immortalwrt-custom

Custom ImmortalWrt 25.12 firmware images. Release assets only.

## Downloads

| File | Device |
| ---- | ------ |
| `immortalwrt-25.12.2-rockchip-armv8-friendlyarm_nanopi-r2s-squashfs-sysupgrade.img.gz` | NanoPi R2S (sysupgrade) |
| `immortalwrt-25.12.2-x86-64-generic-squashfs-combined-efi.img.gz` | x86/64 VM, UEFI boot |

Verify integrity after download:

```sh
sha256sum -c sha256sums-friendlyarm_nanopi-r2s.txt  # R2S
sha256sum -c sha256sums-generic.txt                # x86/64
```

## What's customized (vs stock ImmortalWrt 25.12)

- SSH: `dropbear` replaced with `openssh-server` + `openssh-sftp-server`
- ROOTFS partition: 768 MB
- Added packages: `curl`, `openssl-util`, `htop`, `coreutils-ls`, `coreutils-base64`, `v2ray-geoip`, `v2ray-geosite`, `qemu-ga` (x86 only)
- `dae` v2.1.1 and `naiveproxy` preinstalled under `/usr/bin` (upstream binaries, not ImmortalWrt feed packages); upgrade them on-device later with `upgrade-bin <dae|naiveproxy>`
- First boot enables `sshd`. `dae`/`naiveproxy` are installed but **not** enabled — they must not interfere with normal boot; after writing `/etc/dae/config.dae`, run `/etc/init.d/dae enable && /etc/init.d/dae start`

## Source & license

Built from unmodified ImmortalWrt 25.12.2 with the official ImageBuilder:
only the package selection and first-boot configuration above differ from stock.

- ImmortalWrt upstream: https://github.com/immortalwrt/immortalwrt (GPL-2.0-only)
- dae: https://github.com/daeuniverse/dae (AGPL-3.0)
- naiveproxy: https://github.com/klzgrad/naiveproxy
