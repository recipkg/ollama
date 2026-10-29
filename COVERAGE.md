# 覆盖状态

**阶段：提取中。尚无依据本配方进行的独立重建。**

## 固定来源

- Ollama `v0.40.13`，发布于 2026-10-28；固定源码提交 `04088e7c9d41cba5d33bafbf788d87a465c79d5b`。
- 2026-10-29 GitHub API 元数据：仓库 185,186 stars、大小 96,828 KB、MIT 许可。未克隆完整仓库或下载发行包/模型权重。
- 读取固定提交的 `README.md`、`docs/cli.mdx`、`docs/api.md`、`docs/openapi.yaml` 和 `LICENSE`；这些是文档观察，不等同于运行验证。

## 本机观察

- `/usr/local/bin/ollama --version` 输出 `0.20.2`，比固定目标旧多个版本；仅检查了版本和帮助。帮助列出 run/serve/pull/push/create/show/list/ps/stop/cp/rm 等 CLI 家族。
- 未启动或探测本机服务，未查询模型列表，未访问 registry，未下载模型，也未执行推理。旧版 CLI 输出不能视为 v0.40.13 行为证据。

## 文档观察

- 固定 README 和 CLI 文档描述本地模型运行，以及应用/Agent integration；CLI 文档包含 `run`、`launch`、多模态输入和 embeddings 示例。
- 固定 API 文档描述流式与非流式 `/api/chat`、`/api/generate`、`/api/embed`、工具调用、图片输入、加载/卸载、模型 CRUD、registry push/pull。
- 文档说明取消的模型 pull 可续传，多个请求可共享下载进度；需实测确认实现行为与错误边界。
- 模型文件、硬件驱动、注册表服务和各模型许可是外部边界。本机没有固定版本二进制与许可测试模型，不能用旧版或文字样例填补。

## 缺口

- 未运行固定版本 `v0.40.13`；未独立重建；没有运行本地 HTTP API 验收。
- 未测试 CLI 新旧命令差异、请求校验、流式终止、工具调用、图片、embedding、错误码、模型状态或持久化。
- 未测试 registry 续传、并发、摘要校验、权限、空间不足和中断恢复。
- 未测试 CPU/GPU/Metal/ROCm、跨平台构建、推理正确性、tokens/s、首 token 延迟、内存或并发；没有性能预算。
- 桌面 UI、云端产品、完整模型目录和所有模型架构/权重许可不在当前覆盖声明中。
