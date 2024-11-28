<p align="center">
    <img src="https://qclic.github.io/img/logo.svg" alt="secos-logo" width="64"><br>
    A security operating system focused on the AIoT (Artificial Intelligence of Things) field.<br/>
    <br/>
</p>

English | [中文版](README_CN.md)

# Architecture
![ARCH](https://qclic.github.io/img/secos.arch.svg)

# Build
Currently built based on openEuler and Jailhouse. Firstly, pull the source code by `git clone --recursive git@github.com:qclic/SecOS.git`.

## Build linux image
Use the oebuild tool provided by openEuler Embedded to build and configure the Linux image. First, install the dependencies. For openEuler systems, use the command `sudo dnf install python3 python3-pip docker` to install the required packages. For Ubuntu systems, use the command `sudo apt install python3 python3-pip docker` to install them.
1. Use the command `oebuild init -u git@github.com:qclic/yocto-meta-openeuler.git <build_baord_folder> && cd $_` to create the directory for the oebuild workspace.
    - `<build_baord_folder>`: The folder that stores the build output for the specified development board, such as `build_phtiumpi`, `build_raspi4` etc.
2. Execute `oebuild update` to prepare the initial environment.
3. Execute `oebuild generate -p <build_board> -d <build_folder>` to generate the build directory and the configuration file `compile.yaml`. Then `cd build/<build_folder>` go to the build directory.
    - `<build_board>`: Currently, it supports `phytiumpi` or `raspberrypi4-64`
    - `<build_folder>`: The folder that stores the build output, such as `phytiumpi` or `raspi4`.
4. Execute the `oebuild bitbake` command to enter the build container environment.
5. Execute `bitbake openeuler-image` to start the build process.

## Build ArceOS image
ArceOS is developed using the Rust programming language. First, please install the Rust development environment according to the official [Rust website](https://www.rust-lang.org/).

1. Use the command `cargo install ostool` to install the dependencies.
2. Use the command `ostool build` to build the project.

# Documents

For more information about the project, check out [The SecOS Document](https://qclic.github.io/).

# License

The source code and documentation of SecOS are primarily licensed under the MIT License, while some components retain their original open-source licenses.
