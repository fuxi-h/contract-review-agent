# contract-review-agent

合同审查 agent：上传一份合同，自动拆解条款，对照法规和审查规则识别风险并给出修改建议，关键结论交由人工确认。

这是一个学习型项目：从手写 agent 循环开始，逐阶段加入 LangGraph、RAG、MCP、多 agent、评测和上线能力；每个阶段对照阅读 [openai/codex](https://github.com/openai/codex) 处理同一问题的方式。

> 状态：P1 进行中。下文的“目标流程”是规划，不代表已经实现。

## 目标流程

合同文件 → 文档解析 → 条款拆解 → 风险识别（检索法规与审查规则）→ 人工确认 → 审查报告

## 路线图

| 阶段 | 主题 | 阶段产出 | 状态 |
|---|---|---|---|
| P1 | 底层：模型 API 与手写 agent 循环 | 不依赖框架的 agent 循环 | 进行中 |
| P2 | 合同数据、条款拆解、评测集 v0 | 条款拆解 + 评测基线 | 未开始 |
| P3 | LangGraph 原理与重写 | 检查点、人工审批、流式事件 | 未开始 |
| P4 | RAG：法规与审查规则库 | 混合检索 + 重排，结论带引用 | 未开始 |
| P5 | 工具、MCP 与多 agent | MCP server + 单/多 agent 对比 | 未开始 |
| P6 | 评测与执行轨迹 | LangSmith 轨迹 + LLM-as-judge + 回归报告 | 未开始 |
| P7 | 上线 | API、SSE、前端、安全、部署 | 未开始 |
| P8 | 作品集 | 文档、演示视频、技术文章 | 未开始 |

## 目录结构

```
contract-review-agent/
├── src/contract_review/   # 主代码
├── docs/notes/            # 阶段复盘与 Codex 对照笔记
├── .env.example           # 环境变量模板
└── pyproject.toml
```

后续阶段按需增加 `scripts/`、`data/`、`evals/`、`tests/`。

## 快速开始

需要 Python 3.11 及以上。

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate；macOS/Linux: source .venv/bin/activate
pip install -e ".[dev]"
cp .env.example .env   # 填入模型地址、密钥和模型名
```

模型通过 OpenAI 兼容接口调用，DeepSeek、通义、智谱等均可。

## 评测结果

尚未建立基线，P2 完成后在这里记录。

## 许可

[MIT](LICENSE)
