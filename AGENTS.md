# Ollama 配方约定

阅读 `RECIPE.md`、`BUILD_PROMPT.md`、`ACCEPTANCE.md`、`SOURCES.md`、`COVERAGE.md` 与 `quality` 递归依赖。固定上游为 Ollama v0.40.13；保留 CLI、HTTP API、模型状态、许可、硬件前提和证据边界。

- 仅提交 UTF-8 Markdown；不得提交 Ollama 源码、发行文件、模型权重、缓存、真实账号信息或执行钩子。
- 不启动或停止宿主已有 Ollama 服务，不查看、拉取、复制或删除用户模型。
- 本地系统版 `0.20.2` 不是目标版本；运行观察必须标出二进制来源与版本。
- 模型 registry、权重许可、网络访问、驱动和硬件均为外部条件，不因 CLI/归档检查通过就宣称已覆盖。
- 在配方目录外独立重建；分别汇报文档来源观察、旧版本机观察、归档检查、重建结果和硬件验收。
