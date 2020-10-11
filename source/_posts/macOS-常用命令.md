---
title: macOS 常用命令
author: Chic Cheung
tags:
  - macOS
categories: macOS
index_img: /img/2.jpg
banner_img: /img/2.jpg
abbrlink: f5c6e166
date: 2020-05-24 18:00:39
---

## 磁盘分区

- 查看磁盘分区

  ```bash
  sudo diskutil list
  ```

  

- 挂载 disk0s1 分区

  ```bash
  sudo diskutil mount disk0s1
  ```

  

- 卸载 disk0s1 分区

  ```bash
  sudo diskutil unmount disk0s1
  ```

  

- /dev/disk2 重分区

  ```bash
  diskutil partitionDisk /dev/disk2 2 MBR FAT32 "EFI" 200Mi HFS+J "install_osx" R
  ```

  

- /dev/disk2 重分区

  ```bash
  diskutil partitionDisk /dev/disk2 1 MBR FAT32 "SAMSUNG" R
  ```

  

- 使用 App Store 下载的镜像创建启动盘

  ```bash
  sudo "/Applications/Install macOS Catalina.app/Contents/Resources/createinstallmedia" --volume  /Volumes/install_osx --nointeraction
  ```
  
  



## 配置环境

- 允许任意来源程序运行

  ```bash
sudo spctl --master-disable
  ```

- 安装 Apple Command Line Tools

  ```bash
xcode-select --install
  ```

- 安装 oh-my-zsh

  ```bash
  sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

- Github 配置 proxy

  ```bash
  git config --global http.https://github.com.proxy socks5://127.0.0.1:7891 && git config --global http.http://github.com.proxy socks5://127.0.0.1:7891
  ```

  ```bash
  git config --global --unset http.https://github.com.proxy && git config --global --unset http.http://github.com.proxy
  ```

- Git 配置 proxy

  ```bash
  git config --global http.proxy socks5://127.0.0.1:7891 && git config --global https.proxy socks5://127.0.0.1:7891
  ```
  
  ```bash
  git config --global http.proxy http://127.0.0.1:7890 && git config --global https.proxy https://127.0.0.1:7890
  ```
  
  ```bash
  git config --global --unset http.proxy && git config --global --unset https.proxy
  ```
  
- 为 zsh 设置 proxy 函数

  ```bash
echo "alias proxy='export all_proxy=socks5://127.0.0.1:7891'" >> ~/.zshrc && echo "alias unproxy='unset all_proxy'" >> ~/.zshrc && source ~/.zshrc
  ```

- 安装 Homebrew

  ```bash
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
  ```

  

- 安装 Github Desktop

  ```bash
brew cask install github
  ```

- 安装 node@12

  ```bash
brew install node@12 && echo 'export PATH="/usr/local/opt/icu4c/bin:$PATH"' >> ~/.zshrc && echo 'export PATH="/usr/local/opt/icu4c/sbin:$PATH"' >> ~/.zshrc && echo 'export PATH="/usr/local/opt/node@12/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc && npm config delete proxy
  ```

- 安装 Hexo

  ```bash
npm install hexo-cli -g
  ```

## 安装应用

- 安装常用软件

  ```bash
brew cask install sogouinput aliwangwang baidunetdisk paper typora upic iina motrix vmware-fusion visual-studio-code java miniconda && open '/usr/local/Caskroom/sogouinput/58a,1588947491/sogou_mac_58a.app' && echo 'export PATH="/opt/miniconda3/bin:$PATH"' >> ~/.zshrc && source ~/.zshrc && conda init "$(basename "${SHELL}")"
  ```

- 安装 搜狗拼音输入法

  `brew cask install sogouinput && open '/usr/local/Caskroom/sogouinput/58a,1588947491/sogou_mac_58a.app'`

  

- 安装 阿里旺旺

  `brew cask install aliwangwang`

  

- 安装 百度网盘

  `brew cask install baidunetdisk`

  

- 安装 pap.er

  `brew cask install paper`

  

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

