---
title: macOS 常用命令
author: Chic Cheung
tags:
  - macOS
categories: macOS
index_img: /img/4.jpg
banner_img: /img/4.jpg
abbrlink: 5624
date: 2020-05-24 18:00:39
---

## 磁盘分区

- 查看磁盘分区

  `sudo diskutil list`

  

- 挂载 disk0s1 分区

  `sudo diskutil mount disk0s1`

  

- 卸载 disk0s1 分区

  `sudo diskutil unmount disk0s1`

  

-  /dev/disk2 重分区

  `diskutil partitionDisk /dev/disk2 2 MBR FAT32 "EFI" 200Mi HFS+J "install_osx" R`

  

- /dev/disk2 重分区

  `diskutil partitionDisk /dev/disk2 1 MBR FAT32 "SAMSUNG" R`

  

- 使用 App Store 下载的镜像创建启动盘

  `sudo "/Applications/Install macOS Catalina.app/Contents/Resources/createinstallmedia" --volume  /Volumes/install_osx --nointeraction`



## 配置环境

- 安装 Apple Command Line Tools

  `xcode-select --install`

  

- 允许任意来源程序运行

  `sudo spctl --master-disable`

  

- 安装 oh-my-zsh

  `sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"`

  

- Github 设置 proxy

  `git config --global http.https://github.com.proxy socks5://127.0.0.1:7891`

  `git config --global http.http://github.com.proxy socks5://127.0.0.1:7891`

  

- Github 取消 proxy

  `git config --global --unset http.https://github.com.proxy`

  `git config --global --unset http.http://github.com.proxy`

  

- Git 配置 proxy

  ```bash
  git config --global http.proxy http://127.0.0.1:7890
  
  git config --global https.proxy https://127.0.0.1:7890
  
  git config --global http.proxy socks5://127.0.0.1:7891
  
  git config --global https.proxy socks5://127.0.0.1:7891
  
  git config --global --unset http.proxy
  
  git config --global --unset https.proxy
  
  ```

- 为 zsh 设置 proxy 函数

  `echo "alias proxy='export all_proxy=socks5://127.0.0.1:7891'" >> ~/.zshrc`

  `echo "alias unproxy='unset all_proxy'" >> ~/.zshrc`

  

- 重载 zsh 配置文件

  `source ~/.zshrc`

  

- 安装 Homebrew

  `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`

  

- 安装 Sourcetree

  `brew cask install sourcetree`

  

- 安装 node@12

  `brew install node@12`

  

- npm 取消 proxy

  `npm config delete proxy`

  

- 安装 Hexo

  `npm install hexo-cli -g`

  

## 安装应用

- 安装常用软件

  ```bash
brew cask install sogouinput aliwangwang baidunetdisk typora upic iina motrix vmware-fusion visual-studio-code java miniconda && open '/usr/local/Caskroom/sogouinput/58a,1588947491/sogou_mac_58a.app' && conda init "$(basename "${SHELL}")"
  ```

  

- 安装 搜狗拼音输入法

  `brew cask install sogouinput`

  `open '/usr/local/Caskroom/sogouinput/58a,1588947491/sogou_mac_58a.app'`

  

- 安装 百度网盘

  `brew cask install baidunetdisk`

  

- 安装 阿里旺旺

  `brew cask install aliwangwang`

  

- 安装 Typora

  `brew cask install typora`

  

- 安装 uPic

  `brew cask install upic`

  

- 安装 IINA

  `brew cask install iina`

  

- 安装 Motrix

  `brew cask install motrix`

  

- 安装 VMware Fusion

  `brew cask install vmware-fusion`

  

- 安装 Visual Studio Code

  `brew cask install visual-studio-code`

  

- 安装 OpenJDK

  `brew install java`

  

- 安装 Miniconda

  `brew cask install miniconda`

