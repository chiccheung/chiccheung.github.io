---
title: 使用 OpenCore 在线安装 macOS
author: Chic Cheung
tags:
  - OpenCore
  - macOS
categories: macOS
index_img: /img/1.jpg
banner_img: /img/1.jpg
abbrlink: c8c18f86
---

## 特性

- 支持各版本的 macOS 的下载安装
- Apple 服务器获取原始镜像文件
- Recovery 文件体积仅 500 MB+
- Python 脚本与生俱来的跨平台特性

## 要求

- 正常使用的 OpenCore 引导文件
- 内置网卡在 macOS 下正常驱动

## 步骤

- 下载 [OpenCore 引导文件](https://github.com/chiccheung/HP-Zhan66-Pro14-G2-macOS)

- 下载 [macrecovery](https://github.com/acidanthera/OpenCorePkg/tree/master/Utilities/macrecovery)

  ```bash
  curl -OL https://raw.githubusercontent.com/acidanthera/OpenCorePkg/master/Utilities/macrecovery/macrecovery.py
  ```

- 获取 `BaseSystem.chunklist`、`BaseSystem.dmg`  

  ```bash
  python ./macrecovery.py -b Mac-E43C1C25D4880AD6 -m 00000000000000000 -os latest download
  ```

- *获取历史镜像可参阅 [recovery_urls.txt](https://github.com/acidanthera/OpenCorePkg/blob/master/Utilities/macrecovery/recovery_urls.txt) 自行修改*
- 将 U 盘格式化为 `FAT 32`  格式，在根目录下新建 `com.apple.recovery.boot` 文件夹并将 `BaseSystem.chunklist`、`BaseSystem.dmg` 复制进去
- 将 OpenCore 引导文件复制到 U 盘根目录下
- 完成后的文件结构如下:

````bash
EFI
    ├── BOOT
    ├── OC
com.apple.recovery.boot
    ├── BaseSystem.chunklist
    └── BaseSystem.dmg
````

- 重启，从 U 盘引导至 OpenCore ，按空格显示隐藏选项，选择 `Install macOS` 开始在线安装

