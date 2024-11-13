# 简介
针对 AIoT 领域，构建一个注重安全的操作系统。

# 架构
TODO

# 构建
使用 openEuler Embedded 提供的 `oebuild` 构建和配置的工具来构建适用于树莓派 4B 或飞腾派的镜像。当前仅支持在 64 位的 x86 环境下进行构建，并且需要以普通用户执行 `oebuild` 命令。最低支持 Python3.8 版本，推荐 Python3.10。

## 安装依赖
openEuler: `sudo dnf install python3 python3-pip docker`
Ubuntu: `sudo apt install python3 python3-pip docker`

## 构建 Linux 镜像

1. 使用 `oebuild init -u https://gitee.com/itexp/yocto-meta-openeuler.git openeuler_phytium && cd $_` 命令创建 oebuild 工作要使用的目录。
2. 执行 `oebuild update` 进行初期环境的准备。
3. 执行 `oebuild generate -p phytiumpi -d build_phytium` 生成构建目录以及配置文件 compile.yaml
4. 执行 `oebuild bitbake` 命令进入构建容器环境。
5. 执行 `bitbake openeuler-image` 启动构建。

## 构建 ArceOS 镜像
TODO

# 部署
TODO

## 烧写 Linux 镜像
TODO

# 验证

TODO
