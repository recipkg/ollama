# Ollama 来源与候选选择

## 标准库缺口与比较

标准库已有 Dify、LangGraph、OpenHands、OpenClaw、LibreChat 和 AnythingLLM 等 Agent/应用材料，但尚无本地模型运行器和推理 API 服务。Ollama 提供 CLI、本地服务和应用接入，补充 Agent 的模型执行基础设施。

GitHub API 星数与仓库大小取 2026-10-29 快照：

| 候选 | Stars | 仓库大小 | 固定版本/近期发布 | 选择范围 |
| --- | ---: | ---: | --- | --- |
| `ollama/ollama` | 185,186 | 96,828 KB | `v0.40.13`，2026-10-28 | 本地模型运行器、CLI 与 API 服务 |
| `ggml-org/llama.cpp` | 132,716 | 466,431 KB | `v0.8.0`，2026-10-28 | 更底层的 C/C++ 推理运行时与库 |
| `vllm-project/vllm` | 95,830 | 333,528 KB | `v0.32.0`，2026-10-18 | 面向高吞吐服务的 Python 推理引擎 |

选 Ollama 是因为它覆盖 CLI、模型生命周期和 HTTP 接口，面向本地用户/Agent 集成明确，且候选中星数最高、版本近期。星数只帮助发现候选，不代表质量、硬件兼容或可重建性。Ollama 仓库接近 100 MB；本轮不克隆源码、不下载发行包或模型，采用固定提交的官方小型文档与本机旧版 CLI 观察。

## 固定来源、版本与许可

- 项目：[ollama/ollama](https://github.com/ollama/ollama)，固定 release：[v0.40.13](https://github.com/ollama/ollama/releases/tag/v0.40.13)。
- 发布日期：2026-10-28；固定源码提交：`04088e7c9d41cba5d33bafbf788d87a465c79d5b`。
- 代码仓库 `LICENSE` 为 MIT。模型权重、模型卡、外部集成和发行组件可能有各自许可证；不能由 Ollama 代码许可推断模型许可。
- 仓库快照（2026-10-29）：185,186 stars，96,828 KB。系统本机 `/usr/local/bin/ollama` 是 `0.20.2`，仅用于标出版本差异，不作为固定版本行为证据。

## 依赖与运行边界

- `software-quality`：Recipkg [质量合同](https://github.com/recipkg/recipkg/tree/41e5b55c6612a9a5a10e499b5ace6a1a3fed0f2b/recipes/software-quality)，固定至 `41e5b55c6612a9a5a10e499b5ace6a1a3fed0f2b`，用于 CLI/API 反馈、错误处理、资源管理和有依据的性能验收，不是运行时服务。
- 模型权重与 registry 是外部输入和服务；各模型需要独立许可与体积评估，Recipkg 不打包权重。
- 操作系统、CPU/GPU、驱动和加速运行时是平台前提；固定版本覆盖矩阵及实际验收尚未整理。
- 不声明 `llama.cpp` 为 Recipkg 依赖：它是候选项目/底层实现来源，不是 Ollama 用户必须单独安装的稳定行为接口。

## 固定版本阅读清单

- [v0.40.13 发布说明](https://github.com/ollama/ollama/releases/tag/v0.40.13)
- [固定 README](https://github.com/ollama/ollama/blob/04088e7c9d41cba5d33bafbf788d87a465c79d5b/README.md)
- [固定 CLI 文档](https://github.com/ollama/ollama/blob/04088e7c9d41cba5d33bafbf788d87a465c79d5b/docs/cli.mdx)
- [固定 API 文档](https://github.com/ollama/ollama/blob/04088e7c9d41cba5d33bafbf788d87a465c79d5b/docs/api.md)
- [固定 OpenAPI 描述](https://github.com/ollama/ollama/blob/04088e7c9d41cba5d33bafbf788d87a465c79d5b/docs/openapi.yaml)
- [固定 LICENSE](https://github.com/ollama/ollama/blob/04088e7c9d41cba5d33bafbf788d87a465c79d5b/LICENSE)
- 对照：[llama.cpp](https://github.com/ggml-org/llama.cpp) 与 [vLLM](https://github.com/vllm-project/vllm)。
