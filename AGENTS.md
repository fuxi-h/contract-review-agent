# AGENTS

给 AI 编程助手（Claude Code、Codex、Cursor 等）的项目约定。

## 项目性质

学习型项目：作者通过亲手实现来学习 agent 开发。AI 助手以讲解、审查、排错为主，**不要替作者整段实现当前学习节点的功能**，除非作者明确要求。

## 环境

- Python 3.11 及以上，依赖写在 `pyproject.toml`。
- 模型通过 OpenAI 兼容接口调用，配置来自 `.env`，变量名见 `.env.example`。密钥不得写进代码、提示词、日志或提交。

## 代码约定

- 写中文意图注释：说明为什么这样做、数据从哪里来交给谁，不逐行翻译代码。
- P1 阶段（手写 agent 循环）不引入 LangChain、LangGraph 等 agent 框架。
- 新增依赖前说明理由，优先用标准库和已有依赖。

## 数据

- 只使用公开数据，不放任何公司资料。
- 原始合同和下载的数据集放 `data/raw/`，不进仓库；只提交下载脚本，以及写明来源和许可的 `data/README.md`。

## 测试与评测

- 单元测试：`python -m pytest -q`
- 评测命令：P2 建立评测集后补充。

## 提交

Conventional Commits 前缀，正文用中文，例如 `feat(agent): 实现手写 agent 循环`。
