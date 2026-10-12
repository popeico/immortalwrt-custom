# immortalwrt-custom

Custom ImmortalWrt builds. Release assets only — no source code here.

## What this is

Personalized ImmortalWrt 25.12 images built with the official ImageBuilder:

- Target: rockchip/armv8 (NanoPi R2S) and x86/64 (generic, VM use)
- dropbear replaced with openssh-server + openssh-sftp-server
- ROOTFS 768MB, plus curl, openssl-util, htop, coreutils-ls/base64, naiveproxy, v2ray-geoip/geosite
- dae v2 binary integrated manually (not in ImmortalWrt feeds), with procd init and `upgrade-dae` for manual binary upgrades

## Source & license

ImmortalWrt is licensed under **GPL-2.0-only**.

- Upstream source: https://github.com/immortalwrt/immortalwrt
- Build recipe (workflows, package list, overlay files): https://github.com/popeico/build-factory (private)
- dae: https://github.com/daeuniverse/dae (AGPL-3.0)

These images are built from unmodified upstream binaries plus the package
selection and first-boot configuration documented in the build recipe above.
