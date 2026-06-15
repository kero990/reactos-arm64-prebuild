# reactos-arm64-prebuild

[English](#english) | [中文说明](#中文说明)

---

<a name="english"></a>
## English

This repository provides automated prebuilds of the experimental **ReactOS ARM64** port. To keep things clean and resource-friendly, it checks for updates once a week and operates on a **Single-Release Policy** (only keeping the absolute latest successful build).

### 🌟 Project Context & Milestone

On **May 27, 2026**, the official ReactOS team published a historic milestone on X (formerly Twitter) in [Status 2059339272486887737](https://x.com/reactos/status/2059339272486887737):

> *"For 8 months, our contributor sidihmeed has been working on getting ReactOS ARM64 port to boot. Here's the first success! Being still in an experimental state, you may want to try it."*

This repository is dedicated to keeping up with the hard work of contributor Ahmed Arif ([@sidihmeed](https://x.com/sidihmeed) / [ahmedarif193](https://github.com/ahmedarif193)) by compiling his [ahmedarif193/reactos](https://github.com/ahmedarif193/reactos) repository.

---

### 🚀 Features

* **Weekly Polling (Once a week)**: Runs an automated update check every Sunday to save GitHub Actions runner quota.
* **Single-Release Policy**: To keep the repository clean, each successful build deletes the previous release and tag, ensuring only **one** up-to-date release with the latest `bootcd.iso` and `livecd.iso` is active.
* **No Changes, No Action**: If no upstream updates are detected during the weekly check, the current release remains completely untouched.
* **Native ARM64 Compilation**: Built on native GitHub `ubuntu-24.04-arm` runners.

### 💾 How to Download

Testing the latest ARM64 build is straightforward:
1. Navigate to the [Releases](../../releases) tab of this repository.
2. Download either `bootcd.iso` or `livecd.iso` from the single active release.

---

<a name="中文说明"></a>
## 中文说明

本仓库提供了 **ReactOS ARM64** 实验性分支的自动化预构建镜像。为了节省构建资源并保持仓库整洁，系统采取了**每周定时轮询**与**单 Release 覆盖策略**。

### 🌟 项目背景与里程碑

在 **2026年5月27日**，ReactOS 官方在 X（原 Twitter）上发表了一条具有历史意义的推文 [Status 2059339272486887737](https://x.com/reactos/status/2059339272486887737)：

> *“在长达 8 个月的开发后，我们的贡献者 sidihmeed 成功让 ReactOS ARM64 分支首次启动。这是阶段性的成功！由于目前仍处于实验性阶段，欢迎大家下载尝试。”*

本仓库旨在跟进贡献者 Ahmed Arif（[@sidihmeed](https://x.com/sidihmeed) / [ahmedarif193](https://github.com/ahmedarif193)）的最新工作成果，对他的 [ahmedarif193/reactos](https://github.com/ahmedarif193/reactos) 仓库代码进行持续性的监控与编译构建。

---

### 🚀 项目特性

* **每周轮询一次（节省额度）**：系统固定于每周日执行一次更新检测。如果检测到这一周内没有新代码推入，工作流将直接优雅退出，**保持现有 Release 原状**。
* **单 Release 策略**：为了保证仓库不产生历史堆积，每次编译成功后，会自动物理删除旧的 Release 及对应的 Git Tag，确保只保留**一个**包含最新镜像的 Release。
* **原生 ARM64 编译**：基于 GitHub 官方提供的原生 `ubuntu-24.04-arm` 运行器，无需架构模拟，构建高效稳定。

### 💾 如何下载体验

1. 点击本仓库顶部的 [Releases](../../releases) 页面。
2. 直接下载当前唯一的 Release 下挂载的 `bootcd.iso` 或 `livecd.iso` 镜像。

---

## 🛡️ License & Disclaimer

ReactOS is licensed under the **GNU GPL v2** (or later versions). The build artifacts provided here are highly experimental nightlies and may contain bugs. Use them for testing and emulation purposes (such as in QEMU or on supported ARM64 hardware) at your own risk.
