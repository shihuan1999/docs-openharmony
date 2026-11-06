<!--
 * Copyright 2022-2023 SPACEMIT. All rights reserved.
 * Use of this source code is governed by a BSD-style license
 * that can be found in the LICENSE file.
 *
 * @Author: William Zhou
 * @Date: 2026-11-06
 * @FilePath: \doc\docs-openharmony\zh\technical_topics\skills\index.md
 * @Description: oh-skill 技能仓库说明，内容同步自 Gitee
-->
sidebar_position: 10

# Skill

| 项目 | 内容 |
|------|------|
| Gitee 仓库 | [https://gitee.com/spacemit-openharmony/oh-skill](https://gitee.com/spacemit-openharmony/oh-skill) |
| 克隆命令 | `git clone https://gitee.com/spacemit-openharmony/oh-skill.git` |
| 适用平台 | SpacemiT K1 / K3，OpenHarmony 6.1 LTS |

本 Skill 仓库是 进迭时空（SpacemiT）官方 为 RISC-V 芯片平台 K1 与 K3 提供的 OpenHarmony 操作系统适配与开发技能集合。仓库旨在帮助开发者快速掌握在 SpacemiT RISC-V 硬件平台上进行 OpenHarmony 系统移植、驱动开发、应用构建及 AI 功能开发的全流程技术方案。

## 使用方法

不同 AI 工具对 skills 目录的路径约定不同。使用时，将本仓目录重命名（或软链接）为对应 AI 工具自动检测的路径即可。

| AI 工具 | Skills 目录路径（相对工作区根目录） | 说明 |
|--------|----------------------------------|------|
| GitHub Copilot | `.github/skills/` | Copilot 自动扫描该目录下的 `SKILL.md` |
| Kiro | `.kiro/skills/` | Kiro agent 自动加载该目录下的 `SKILL.md` |
| Cursor | `.cursor/skills/` | Cursor rules 扩展路径（需手动配置引用） |

**示例（GitHub Copilot）：**

直接将本仓克隆到项目路径：

```bash
git clone https://gitee.com/spacemit-openharmony/oh-skill.git .github
```

---

## Skills 列表

| Skill 名称 | 文件路径 | 适用场景 | 触发词示例 |
|-----------|---------|---------|-----------|
| `oh-code-navigation` | `skills/oh-code-navigation/SKILL.md` | OH 子系统代码定位、仓库路径查找、功能模块修改辅助 | 修改音频焦点逻辑、定位相机 HAL 接口、查找 AMS 服务代码 |
| `oh-command` | `skills/oh-command/SKILL.md` | OH 常用命令速查，涵盖设备连接、编译、日志、图形、音频、网络、应用管理、安全、内核、测试等领域 | 查看设备列表、编译代码、抓取日志、截屏、设置音量、连接 WiFi |
| `oh-debug` | `skills/oh-debug/SKILL.md` | OH 设备交互式调试：双 hdc shell 会话、hilog 抓取与中断、进程查找/杀进程、替换 so 库后重启进程验证 | 调试、hdc、shell、hilog、设备调试、日志抓取、进程控制 |
| `system-build` | `skills/system-build/SKILL.md` | OpenHarmony 系统编译构建命令速查，使用 `build.sh` 方式（非 hb build），涵盖整包编译、单目标编译、增量编译、内核快速编译等 | 系统编译、编译、构建、build、打包、重新编译、增量编译、内核编译 |
| `app-build` | `skills/app-build/SKILL.md` | OpenHarmony 应用源码编译 HAP（hvigor）：环境判定（源码工程/独立 SDK）、默认 phone/default 模块、产物与验签 | 应用编译、编译 hap、hvigor、assembleHap、app 编译 |
| `ohos-new-product` | `skills/ohos-new-product/SKILL.md` | Spacemit K1 新增产品方案：参考现有方案全量拷贝 board / vendor / 内核与 uboot dts，并完成 build 侧白名单注册 | 新建方案、新增产品、克隆方案、产品型号、新板子 |
| `oh-scrcpy` | `skills/oh-scrcpy/SKILL.md` | OH 设备投屏到 PC，含获取程序、启动投屏、画质调优、鼠标键盘注入、录制、常见报错处理 | 投屏、镜像、推屏、录屏、设备画面、虚拟屏 |
| `workflow` | `skills/workflow/SKILL.md` | 问题解决工作流，建立 work 文件、分析、制定方案、执行、验证全流程 | 解决、修复、排查、配置、不工作、crash、失败、错误 |
| `log-analysis` | `skills/log-analysis/SKILL.md` | 基于代码分析通过日志定位问题根因，预测关键日志节点，用 grep 精准匹配，对比正常/异常日志找错误分叉点 | 日志分析、代码调试、问题定位、异常排查、日志追踪、错误原因 |
| `ruyi-submit` | `skills/ruyi-submit/SKILL.md` | ruyi 社区修改提交流程，使用 fork + MR 方式自动完成代码提交到 ruyi 社区 | ruyi 提交、社区修改、提交、创建MR、创建PR |
| `v2d` | `skills/v2d/V2D_USAGE_SKILL.md` | SpaceMIT K1 V2D 硬件加速使用指南，NV12→BGR/RGB 色彩转换 + 旋转/缩放/混合，单帧从 ~137ms 降到 ~2ms | V2D、硬件加速、色彩转换、NV12、图像旋转、DMA-BUF |

---

## Skill 详情

### workflow

**功能：** 问题解决工作流。

**使用场景：** 当用户需要解决某个具体问题时默认使用，覆盖分析问题、制定方案、记录过程、总结结论全流程。

**触发词：** 解决、修复、排查、配置、问题、不工作、crash、失败、错误

**argument-hint：** 描述要解决的问题，例如：`CVT Wi-Fi 无法工作` / `内核启动崩溃` / `驱动加载失败`

**工作步骤：**

1. **建立 work 文件** — 在项目目录下按模板创建 `work.md`，填写背景、问题、目标
2. **分析** — 阅读相关代码，查找同类参考配置，只记录有代码或文档支撑的事实
3. **制定方案** — 明确每处需修改的文件和内容，改动范围最小化，方案写入 `work.md`
4. **执行** — 逐文件修改，每次修改后更新 `work.md` 的"已尝试的方案"章节
5. **验证与记录** — 通过设备日志或现象观察验证结果，成功补充结论并注明"已解决"及日期，失败移入"错误方案记录"

**内置模板：** `skills/workflow/templates/work.md`

---

### oh-debug

**功能：** OpenHarmony 设备调试 skill，基于 `hdc` 交互式 shell，实现日志抓取、进程控制、测试程序运行，以及"改代码 → 编译 so → 替换设备 → 重启进程 → 抓日志验证"的完整闭环。

**使用场景：** 需要在设备上执行调试命令、抓取 `hilog`、运行测试 demo、替换 so 库验证修改时使用。

**触发词：** 调试、hdc、shell、hilog、设备调试、日志抓取、进程控制

**argument-hint：** 描述要调试的目标，例如：`抓 cast_engine 日志` / `替换 so 后重启服务` / `运行 camera_test`

**核心思路：** 启动两个独立的 `hdc shell` 会话（必要时第三个兜底），解决 Agent 无法发送 Ctrl-C 控制字符的限制：
- **Shell 1（主工作）** — 执行实际命令，如 `hilog | grep xxx`、运行测试程序
- **Shell 2（控制）** — 用 `ps -ef | grep` 找 PID，用 `kill` / `kill -9` 中断 Shell 1 中的前台命令
- **Shell 3（备用）** — Shell 1、2 都卡死时用于杀进程

**内置流程：**
- 编译 so：`build.sh -T <模块>`（改了 GN）或 `ninja -C out/<产品>` 直编（只改 C/C++），并按子系统定位 `xxx.z.so`
- 推送替换：`mount -o remount,rw /` + `hdc file send`，`md5sum` 比对确认
- 抓日志：先 `hilog -r` 清缓冲，再带关键字过滤抓取（必须在杀服务之前抓，否则丢启动日志）
- 生效验证：`ps` 找进程 → `kill -9` 触发自动拉起加载新 so → 跑测试 demo

**注意事项：** PID 每次都会变，需重新查找；`hdc file send` 等必须用一次性 shell 命令，不放进交互会话；`kill` 默认 SIGTERM(15)，强制终止用 `-9`；日志捕获必须与测试 demo 同步进行，事后补抓不可靠。

**文件：** `skills/oh-debug/SKILL.md`

---

### system-build

**功能：** OpenHarmony 系统编译构建命令速查，使用 `build.sh` 脚本方式（**不使用 hb build**）。

**使用场景：** 用户询问如何编译 OH 系统、产品整包、单个模块或内核时使用。

**触发词：** 系统编译、编译、构建、build、打包、编译产物、重新编译、增量编译、内核编译、编译失败

**argument-hint：** 描述要编译的内容，例如：`编译整包` / `编译 sharing_framework 模块` / `编译 musepaper2 产品`

**内置能力：**
- 整包编译（含 ccache、no-prebuilt-sdk 选项）
- 指定 GN 参数编译（屏幕模式等硬件参数）
- 单目标 / 模块编译（`-T <target_name>`）
- 增量 / 快速重编（`--fast-rebuild`）
- 限制并发数（内存不足场景）
- 编译产物路径说明
- 内核快速编译 `quick_kernel.sh`（增量编译内核并重打 boot.img）
- 常见编译问题排查

---

### app-build

**功能：** OpenHarmony 应用源码编译 HAP（hvigor 命令行），先判定系统与工程形态，再选择工具链编译 release/debug HAP。

**使用场景：** 用户要编译 `applications/standard` 下的应用（settings、systemui 等）、查 HAP 产物或验签时使用。

**触发词：** 应用编译、编译 hap、hvigor、assembleHap、app 编译、编译应用

**argument-hint：** 应用/模块，例如：`settings release` / `systemui 主模块`

**内置能力：**
- 环境判定：Linux OH 源码工程（用 `prebuilts/` 工具、`HVIGOR_USER_HOME` 放工程根）与「仅应用代码 + 独立 SDK」（用系统 node）；Windows 先预览目录
- 关键变量与环境变量：node / SDK / hvigorw / ohpm 路径
- 编译前检查：modelVersion、compileSdkVersion、HAP 模块识别、`ohpm install --all`、签名、JDK
- 默认编译 phone/default 基础模块，编完提示其它可选模块，不自动全量编译
- 产物位置、按 `entryModules` 区分的命名、release 校验与 `hap-sign-tool` 验签
- 常见错误：modelVersion、pnpm、SDK license、`@ohos.cast` 等

**文件：** `skills/app-build/SKILL.md`

---

### ohos-new-product

**功能：** 在 Spacemit K1 OpenHarmony 仓库中新增一个产品方案，覆盖 board 方案、vendor 方案、内核 / uboot dts 与 build 侧注册。

**使用场景：** 用户要求"新建方案 xxx""克隆 xxx 方案""加一个产品型号"时使用。以现有方案作为参考方案全量拷贝并改名，所有步骤一次做完，最后跑收尾自检。

**触发词：** 新建产品、新增方案、克隆方案、产品型号、新板子、board 方案、new product

**argument-hint：** 例如：`创建一个 product1 的方案，代码配置拷贝 product2`

**工作步骤：**

1. **前置检查** — 确认参考方案在 `device/board/spacemit/` 与 `vendor/spacemit/` 下存在，并 grep build 侧各白名单
2. **内核 dts** — 拷贝 `k1-x_<REF>.dts` 为 `k1-x_<NEW>.dts`，改 `model`，在 dts Makefile 追加 dtb
3. **uboot dts** — 参考方案无专属 dts 时从 `k1-x_deb1.dts` 拷贝，改 `model`，追加 Makefile 条目（FIT 由 `build_uboot.sh` 动态生成，无需手改 `uboot_fdt.its`）
4. **board 方案** — 整目录拷贝改名，逐项确认 `BUILD.gn`、`ohos.build`、`build_kernel.sh`、`env_k1-x.txt`、`kernel_patch/*.patch` 中的 dts 路径、`updater` 的 prdID
5. **vendor 方案** — 整目录拷贝改名，确认 `config.json`、`product.gni`、`product_<NEW>.para`（真实机型名）、开机 logo，并清理编译残留
6. **build 侧注册** — `compile_standard_whitelist.json`（逐行插入）、`subsystem_components_whitelist.json`、`ohos_exec_script_allowlist.gni`、`third_party/libjpeg-turbo` 的 `visibility`、`applications/standard/hap/BUILD.gn` 应用裁剪条件
7. **收尾自检** — JSON 格式校验、参考方案名残留检查、枚举型白名单全树扫描、group / part / dts 名一致性抽查

**关键认知：** 产品发现走 `./build.sh --product-name` → `vendor/spacemit/<NAME>/config.json` → `device_build_path` → board 目录，**不需要**在 `productdefine/` 下登记；`device/soc/spacemit` 多产品共用，新方案不应改动。

**文件：** `skills/ohos-new-product/SKILL.md`

---

### oh-scrcpy

**功能：** OpenHarmony 投屏工具 ohscrcpy 使用指南。

**使用场景：** 需要把 OH 设备画面镜像到 PC，并用 PC 的鼠标键盘操作设备时使用。

**触发词：** 投屏、mirror、scrcpy、镜像、推屏、录屏、设备画面、虚拟屏

**argument-hint：** 描述你要做的事，例如：`启动投屏` / `多设备投屏` / `调清晰度` / `投屏报错`

**内置能力：**
- 获取现成客户端程序的位置
- 启动投屏（单设备 / 多设备 / 详细日志）
- 常用命令行选项（录制、窗口尺寸、UI 补齐开关、直连调试）
- 画质调优（density、码率、关键帧间隔、分辨率、码率模式）
- 客户端鼠标 / 键盘操作对照表
- 无物理显示器设备的处理方式
- 常见报错排查与端口转发手工清理
- 日志落盘环境变量

**文件：** `skills/oh-scrcpy/SKILL.md`

---

### oh-code-navigation

**功能：** OpenHarmony (OH) 项目代码导航与修改辅助。

**使用场景：**
- 修改 OH 某个功能模块
- 定位某子系统代码路径
- 查找某组件的服务 / HAL / 接口实现
- 在 oh6 工作区修改音频、视频、相机、蓝牙、Wi-Fi、窗口、ArkUI、权限、IPC、驱动等功能时自动定位仓库并读取相关代码

**触发词：** 修改、查找、定位、分析、OH、OpenHarmony、子系统、组件、HAL、驱动、服务

**argument-hint：** 描述要修改或查找的功能，例如：`修改音频焦点逻辑` / `定位相机 HAL 接口`

**内置能力：**
- 快速关键词 → 路径映射表（音频、视频、相机、蓝牙、Wi-Fi、窗口、ArkUI、IPC 等 50+ 子系统）
- 仓库内部结构惯例（`frameworks/`、`services/`、`interfaces/`、`sa_profile/`、`test/`）
- 修改注意事项（接口层/服务层/HAL 层/构建文件/产品开关同步修改指引）
- 完整路径地图（详见 `skills/oh-code-navigation/references/path-map.md`）

---

### log-analysis

**功能：** 基于代码分析通过日志定位问题根因。

**使用场景：** 从代码预测关键日志节点，使用 grep 匹配确认执行流程，通过对比正常与异常日志找出错误分叉点，快速定位问题原因。

**触发词：** 日志分析、代码调试、问题定位、异常排查、日志追踪、错误原因

**argument-hint：** 提供代码位置或问题现象，例如：`模块 A 崩溃了` / `功能 B 返回错误` / `服务 C 未响应`

**工作流程：**

1. **根据代码预测关键日志节点** — 分析初始化、功能执行、异常处理、资源释放各阶段的日志输出点
2. **使用 grep 精准匹配日志** — 针对预测的日志节点使用 `grep` 在日志文件中精准查找，确认代码执行路径
3. **对比正常与异常日志** — 找出正常流程和异常流程的日志分叉点
4. **定位问题根因** — 根据分叉点附近的代码逻辑和日志内容确定问题原因

**核心原则：**
- ✅ 允许：预测关键日志节点、精准 grep 匹配、逐步验证路径、对比差异
- ❌ 禁止：一次性读取整个日志文件、无目标浏览日志、笼统统计所有日志

---

### ruyi-submit

**功能：** ruyi 社区修改提交流程，使用 fork + MR 方式自动完成代码提交。

**使用场景：** 当用户需要将本地修改提交到 ruyi 社区时使用。

**触发词：** ruyi 提交、社区修改、提交、创建MR、创建PR

**argument-hint：** 描述你要提交的仓库和内容，例如：`提交 camera_framework 修改` / `提交音频模块修改`

**工作流程：**

1. **Step 0：同步并检查冲突** — `repo sync -c .` 更新仓库到最新，确认无冲突
2. **Step 1：本地提交** — `git add` + `git commit -m "<类型>: <简短描述>"`
3. **Step 2：fork 上游** — 通过 GitLab API fork 上游项目，记录 fork_id 和 SSH 地址
4. **Step 3：推送分支** — 添加 fork remote，推送到指定分支（默认 `OpenHarmony-6.1-Release`）
5. **Step 4：创建 MR** — 通过 API 创建 Merge Request，指向上游仓库

**内置能力：**
- 自动从 `~/.git-credentials` 提取 token
- 自动从 manifest 查找目标分支
- 通过 API 搜索上游项目 ID
- 处理 fork 已存在的情况（409 错误）
- 完整的回退流程（关闭 MR、删除 fork、撤销 commit）

---

### v2d

**功能：** SpaceMIT K1 V2D 2D 图形硬件加速器使用指南。

**使用场景：** 在 OpenHarmony 应用中将 NV12→BGR/RGB 色彩转换、旋转、缩放、混合等图像处理任务卸载到 V2D 硬件加速器，替代 CPU 标量运算（K1 无 NEON/SIMD）。

**触发词：** V2D、硬件加速、色彩转换、NV12、BGR、图像旋转、DMA-BUF、SpaceMIT K1

**argument-hint：** 描述要完成的图像处理任务，例如：`NV12 转 BGR` / `相机帧旋转 180°` / `V2D 初始化失败排查`

**核心能力：**
- NV12/NV21 ↔ RGB/BGR 色彩空间转换（BT.601/BT.709）
- 旋转（0/90/180/270°、镜像翻转）+ 缩放
- 双图层 Alpha 混合 / OSD 水印叠加
- DMA-BUF 零拷贝，sync fence 异步通知
- 两种接入方式：自带 `v2d_converter.cpp`（推荐）或 `dlopen` 加载系统 `libv2d.so`
- 性能调优：驱动时钟策略修改（fd 生命周期模式），单帧从 ~137ms 降至 ~2ms
- 完整排错手册（内核结构体对齐、DVFS 干扰、fence_wait 暴涨等）

**文件：** `skills/v2d/V2D_USAGE_SKILL.md`

---

### oh-command

**功能：** OpenHarmony 常用命令速查。

**使用场景：** 用户询问 OpenHarmony/OH/鸿蒙 如何执行某项操作时使用。

**触发词：** 查看设备、编译代码、抓取日志、截屏、设置音量、连接 WiFi、安装应用、SELinux、XTS 测试

**argument-hint：** 描述你想执行的操作，例如：`查看设备列表` / `编译代码` / `抓取日志`

**内置命令领域：**

| 章节 | 覆盖命令 |
|------|----------|
| 设备连接 (hdc) | `hdc list targets`、无线调试、文件传输、服务重启 |
| 代码编译 (build) | `./build.sh`、单目标编译、快速重编、代码格式化、提交代码 |
| 日志调试 | `hilog`（级别/限流/脱敏/缓冲区）、`hitrace`、`hisysevent`、`dumpcatcher`、`addr2line` |
| 图形 / 显示 / 输入 | 截屏、窗口信息、帧率、息屏、模拟点击/滑动/按键 |
| 媒体 / 音频 / 编解码 | PCM dump、媒体日志、`pactl` 音量、hcodec debug |
| 网络 / WiFi | `ifconfig`、`netstat`、`wpa_supplicant`、`wpa_cli` 扫描/连接 |
| 应用管理 (bm / aa) | 列出/查看/启动/卸载应用 |
| 安全 (SELinux / 证书) | `setenforce`/`getenforce`、license 环境切换 |
| 内核 / 系统信息 | 系统位数、内核配置、CPU 温度/频率 |
| 测试 (XTS / Monkey / 内存) | XTS 单用例、Monkey 测试、hiprofiler 内存泄露抓取 |

---

## 目录结构

```
oh-skill/
├── README.md
└── skills/
    ├── oh-code-navigation/
    │   ├── SKILL.md                  # Skill 主文件
    │   └── references/
    │       └── path-map.md           # OH 完整路径地图
    ├── oh-command/
    │   └── SKILL.md                  # OH 常用命令速查
    ├── oh-debug/
    │   └── SKILL.md                  # OH 设备交互式调试（hdc 双 shell）
    ├── system-build/
    │   └── SKILL.md                  # OH 系统编译构建（build.sh）
    ├── app-build/
    │   └── SKILL.md                  # OH 应用编译（hvigor，HAP）
    ├── ohos-new-product/
    │   └── SKILL.md                  # Spacemit K1 新增产品方案
    ├── oh-scrcpy/
    │   └── SKILL.md                  # OH 设备投屏使用指南
    ├── workflow/
    │   ├── SKILL.md                  # 问题解决工作流
    │   └── templates/
    │       └── work.md               # work 文件模板
    ├── log-analysis/
    │   └── SKILL.md                  # 基于代码的日志分析与问题定位
    ├── ruyi-submit/
    │   └── SKILL.md                  # ruyi 社区修改提交流程
    └── v2d/
        ├── V2D_USAGE_SKILL.md        # V2D 硬件加速使用指南（Skill 主文件）
        ├── v2d_converter.h           # V2D 转换器头文件
        ├── v2d_converter.cpp         # V2D 转换器实现
        ├── v2d_perf_test.cpp         # 性能对比测试
        └── v2d_perf_test             # 测试二进制
```

