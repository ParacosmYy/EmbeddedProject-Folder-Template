# EmbeddedProject-Folder-Template

> 嵌入式项目目录结构模板。建议后续并入 `GS_Embedded_Template`，与 ARM GCC/CMake 工程模板统一维护。

## 仓库定位

本仓库用于提供一套适合嵌入式产品开发的项目归档结构，覆盖需求、硬件、固件、软件、结构、测试、工具和交付资料。

| 项目 | 说明 |
|------|------|
| 类型 | 工程目录模板 |
| 适用场景 | 新嵌入式项目立项、项目资料归档、团队协作规范 |
| 主要价值 | 让资料从一开始就有固定位置，避免越做越乱 |
| 后续建议 | 与 `GCC_Cmake_ARM` 合并为 `GS_Embedded_Template` |

## 目录结构

```text
EmbeddedProject-Folder-Template/
├── 00_Project_Management/       # 需求、风险、计划、缺陷管理
├── 00_Reference/                # 芯片手册、协议文档、参考资料
├── 01_Function_Map/             # 功能清单、流程图、状态图
├── 02_Hardware/                 # 原理图、PCB、BOM、硬件设计资料
├── 03_Firmware/                 # 固件产物：hex/bin/map/elf
├── 04_Software/                 # 上位机、脚本、SDK、源码
├── 05_Mechanical/               # 结构设计资料
├── 06_FCT/                      # 产测、工装、测试流程
└── 07_Tools/                    # 烧录、加密、自动化测试工具
```

## 使用方式

1. 复制本仓库作为新项目的资料根目录；
2. 按模块把资料放到对应目录；
3. 空目录用 `.gitkeep` 保留；
4. 不要把临时构建产物、IDE 缓存、个人私有配置提交进仓库；
5. 项目稳定后，在 `README.md` 中补充硬件版本、固件版本和交付说明。

## Git 辅助命令

删除所有空目录占位文件：

```bash
find . -type d -not -path "*/.git*" -exec rm -f {}/.gitkeep \;
```

为空目录补充 `.gitkeep`：

```bash
find ./ -type d -empty -not -path "./.git/*" -exec touch {}/.gitkeep \;
```

## 后续合并建议

建议新建或重命名为：

```text
GS_Embedded_Template
```

并合并以下能力：

- 工程目录模板：来自本仓库；
- ARM GCC + CMake 模板：来自 `GCC_Cmake_ARM`；
- VSCode / OpenOCD / CMake / CI 配置；
- 新项目 README 模板；
- 嵌入式项目 `.gitignore` 模板。
