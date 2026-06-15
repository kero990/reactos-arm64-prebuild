# reactos-arm64-prebuild

[English](#english) | [中文说明](#中文说明)

---

<a name="english"></a>
## English

This repository provides automated, daily-updated nightly prebuilds of the experimental **ReactOS ARM64** port. It leverages GitHub Actions to compile the source code on native ARM64 runners, generating ready-to-test `bootcd.iso` and `livecd.iso` images.

### 🌟 Project Context & Milestone

On **May 27, 2026**, the official ReactOS team published a historic milestone on X (formerly Twitter) in [Status 2059339272486887737](https://x.com/reactos/status/2059339272486887737):

> *"For 8 months, our contributor sidihmeed has been working on getting ReactOS ARM64 port to boot. Here's the first success! Being still in an experimental state, you may want to try it."*

This repository is dedicated to keeping up with the hard work of contributor Ahmed Arif ([@sidihmeed](https://x.com/sidihmeed) / [ahmedarif193](https://github.com/ahmedarif193)) by compiling his [ahmedarif193/reactos](https://github.com/ahmedarif193/reactos) repository.

---

### 🚀 Features

* **Automated Pipelines**: Automatically builds whenever upstream changes are pushed or via manual dispatch.
* **Native ARM64 Compilation**: Built on native GitHub `ubuntu-24.04-arm` runners to ensure fast and error-free builds.
* **ISO Generation**: Compiles both `bootcd.iso` and `livecd.iso` targets.
* **No Virtualization/Sudo Overhead**: Uses a clean user-space RosBE (ReactOS Build Environment) installation pipeline.

### 💾 How to Download

Testing the latest ARM64 build is straightforward:
1. Navigate to the [Releases](../../releases) tab of this repository.
2. Find the latest build (tagged chronologically with commit date and short SHA).
3. Download either `bootcd.iso` or `livecd.iso`.

### ⚙️ How the CI/CD Workflow Works

1. **Environment Setup**: Checks out the ReactOS repository and recursive submodules, then installs host dependencies (`clang`, `bison`, `flex`, `meson`, `ninja`).
2. **RosBE Bootstrap**: Installs the Unix ReactOS Build Environment locally in user space without requiring superuser permissions.
3. **Environment Injection**: Exports `ROSBE_ROOT` and prepends the toolchain bins (`llvm-mingw` and `mingw-gcc`) directly to `$GITHUB_PATH`.
4. **Configuration & Compilation**: Configures the project using Clang for the `arm64` release architecture and builds via Ninja.
5. **Release Deployment**: Automatically tags the build and pushes the ISO assets to GitHub Releases.

---

<a name="中文说明"></a>
## 中文说明

本仓库提供了 **ReactOS ARM64** 实验性分支的自动化、每日更新的预构建镜像。通过 GitHub Actions，我们在原生 ARM64 运行器上进行编译，自动生成可供测试的 `bootcd.iso` 和 `livecd.iso`。

### 🌟 项目背景与里程碑

在 **2026年5月27日**，ReactOS 官方在 X（原 Twitter）上发表了一条具有历史意义的推文 [Status 2059339272486887737](https://x.com/reactos/status/2059339272486887737)：

> *“在长达 8 个月的开发后，我们的贡献者 sidihmeed 成功让 ReactOS ARM64 分支首次启动。这是阶段性的成功！由于目前仍处于实验性阶段，欢迎大家下载尝试。”*

本仓库旨在跟进贡献者 Ahmed Arif（[@sidihmeed](https://x.com/sidihmeed) / [ahmedarif193](https://github.com/ahmedarif193)）的最新工作成果，对他的 [ahmedarif193/reactos](https://github.com/ahmedarif193/reactos) 仓库代码进行持续性的编译构建。

---

### 🚀 项目特性

* **全自动工作流**：随上游代码提交或手动触发自动启动构建。
* **原生 ARM64 编译**：基于 GitHub 官方提供的原生 `ubuntu-24.04-arm` 运行器，无需架构模拟，构建高效稳定。
* **完整镜像生成**：同时编译生成 `bootcd.iso`（安装光盘）与 `livecd.iso`（免安装光盘）。
* **轻量安全**：完全在用户空间（非 sudo）下安装并注册 RosBE (ReactOS 编译环境) 链，保持 CI 运行环境整洁。

### 💾 如何下载体验

1. 点击本仓库顶部的 [Releases](../../releases) 页面。
2. 找到最新生成的构建版本（以提交日期和 Short SHA 命名）。
3. 根据需要直接下载 `bootcd.iso` 或 `livecd.iso` 镜像。

---

## 🛡️ License & Disclaimer

ReactOS is licensed under the **GNU GPL v2** (or later versions). The build artifacts provided here are highly experimental nightlies and may contain bugs. Use them for testing and emulation purposes (such as in QEMU or on supported ARM64 hardware) at your own risk.
