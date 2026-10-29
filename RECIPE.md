# Ollama 软件配方（提取中）

```toml
format = "recipkg/1"

[package]
name = "ollama"
version = "0.1.0"
kind = "software"
description = "Ollama v0.40.13 本地模型运行器、CLI 与 HTTP API 的行为重建配方；模型和硬件验证未完成。"
entry = "BUILD_PROMPT.md"

[dependencies.quality]
git = "https://github.com/recipkg/recipkg.git"
rev = "41e5b55c6612a9a5a10e499b5ace6a1a3fed0f2b"
subdir = "recipes/software-quality"
```

## 来源与范围

固定上游为 Ollama `v0.40.13`，提交 `04088e7c9d41cba5d33bafbf788d87a465c79d5b`。本配方提炼本地模型服务、命令行和 HTTP API；Ollama 桌面应用界面与云端产品不在当前重建范围。来源选择、许可和采样边界见 `SOURCES.md`。

`quality` 提供 CLI/API 可读性、错误处理、代码组织和性能证据要求，不是运行时服务。模型权重、模型注册表、硬件加速后端和网络服务属于外部运行条件；配方不包含模型文件，也不假定不同模型采用相同许可证。

Ollama 主仓库使用 MIT 许可证。模型、外置组件和发行包中的各项内容可能有独立许可，应按固定版本发布材料逐项核实。
