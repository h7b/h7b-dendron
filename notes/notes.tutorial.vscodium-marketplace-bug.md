---
id: MyzQxrBiZwHwofC9
title: Vscodium Marketplace Bug
desc: ''
updated: 1636417488911
created: 1626769515445
---
# Workaround for the error of Extension Marketplace in Vscodium

Ref: [Github](https://github.com/VSCodium/vscodium/issues/746#issuecomment-881910118)

Currently at Vscodium `v1.58.2`, the Extension Marketplace cannot be connected due to an unsupported feature from `open-vsx.org`

The workaroud: use tag `--disable-web-security`

![Github](https://user-images.githubusercontent.com/52204908/126040749-1de61b6f-43a0-4483-889f-0b6116d448e6.png)

