<p align="center">
    <img src="https://qclic.github.io/images/site/logo.svg" alt="secos-logo" width="64"><br>
    一个专注于 AIoT 领域的安全操作系统<br/>
    <br/>
</p>

[English](README.md) | 中文版

# 架构
![ARCH](https://qclic.github.io/images/homepage/secos.arch.svg)

# 构建
目前基于 openEuler 和 Jailhouse 构建。首先通过 `git clone --recursive git@github.com:qclic/SecOS.git` 拉取源代码。

## 构建 Linux 镜像
使用 openEuler Embedded 提供的 `oebuild` 构建和配置的工具来构建 Linux 镜像。首先，安装依赖，对于 openEuler 系统，使用 `sudo dnf install python3 python3-pip docker` 命令继续安装；对于 Ubuntu 系统，使用 `sudo apt install python3 python3-pip docker` 命令安装即可。

1. 使用 `oebuild init -u git@github.com:qclic/yocto-meta-openeuler.git <build_baord_folder> && cd $_` 命令创建 oebuild 工作要使用的目录。
   - `<build_baord_folder>`: 存放指定开发板的构建的输出内容的文件夹，例如 `build_phtiumpi`, `build_raspi4` 等.
2. 执行 `oebuild update` 进行初期环境的准备。
    - `<build_board>`: 目前支持 `phytiumpi` 或 `raspberrypi4-64`
    - `<build_folder>`: 用于存放构建出来的镜像的文件夹名字，例如，`phytiumpi` 或 `raspi4`
3. 执行 `oebuild generate -p phytiumpi -d build_phytium` 生成构建目录以及配置文件 compile.yaml。然后 `cd build/<build_folder>` 进入到构建目录中
4. 执行 `oebuild bitbake` 命令进入构建容器环境。
5. 执行 `bitbake openeuler-image` 启动构建。

## 构建 ArceOS 镜像
ArceOS 是使用 Rust 语言进行开发的，首先请根据 [Rust 官网](https://www.rust-lang.org/)安装 Rust 开发环境。

1. 使用命令 `cargo install ostool` 安装依赖
2. 使用命令 `ostool build` 进行构建

# 技术文档

查看 [The SecOS Document](https://qclic.github.io/) 以了解更多关于本项目的信息。

# 开源许可

SecOS 的源代码和文档主要使用 MIT 协议， 部分组件保持原有开源协议！

