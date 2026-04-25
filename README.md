# chatrel-gap-review

把聊天关系分析报告里的缺口找出来，再把这些缺口沉淀成下次可复用的知识。

这是一个面向 Codex 的开源 skill，服务于两个动作：

- 审计一份已经写完的聊天关系分析报告。
- 把覆盖不足的维度蒸馏成结构化知识库。

## 一句话定位

这是一个报告补洞器，也是一个知识蒸馏器。

## 谁该用

- 你已经能产出聊天关系分析报告。
- 你觉得报告质量不稳定，有些维度经常漏写。
- 你希望把“这次缺了什么”沉淀成“下次自动补什么”。
- 你要的是研究证据驱动的补洞层，不是拍脑袋修文案。

## 它解决的核心问题

大多数报告系统都会卡在这里：

- 有输出，没有质检。
- 有缺口，没有系统化补法。
- 有经验，没有沉淀成知识。

`chatrel-gap-review` 把这三件事收口成一条链路：

1. 找出哪些维度已经覆盖。
2. 找出哪些维度覆盖不足。
3. 找出哪些维度完全缺失。
4. 用证据和字段把缺口沉淀成知识。

## 它会产出什么

运行后会生成或更新三类文件：

```text
latest_gap_audit.md
latest_distilled_knowledge.md
distilled/dimensions/*.md
```

这些文件分别承担三个职责：

- `latest_gap_audit.md`：记录这份报告缺了什么。
- `latest_distilled_knowledge.md`：汇总这次新增了什么知识。
- `distilled/dimensions/*.md`：把每个维度拆成可维护、可复用的知识文件。

## 它审计什么

当前知识库覆盖 15 个关系分析维度：

- 数据充分性
- 关系背景
- 关系强度
- 互惠与投入平衡
- 回复节奏
- 话题连续性
- 情绪与情感表达
- 情绪支持
- 信任、亲密与默契
- 冲突修复
- 权力与角色结构
- 语言风格匹配
- 时间趋势
- 语音、图片与媒介线索
- 安全边界与置信度

每个维度都会被标记为以下状态之一：

- 已覆盖
- 覆盖不足
- 缺失

## 仓库结构

```text
chatrel-gap-review/
├── SKILL.md
└── references/
    ├── README.md
    ├── chatrel_report_knowledge/
    ├── foundation_knowledge/
    └── chat_analysis_pipeline/
```

关键文件：

- `chatrel-gap-review/SKILL.md`：skill 入口，定义触发方式、路径约定和执行流程。
- `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`：按维度拆分的蒸馏知识。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_gap_audit.md`：当前审计框架的覆盖快照。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_distilled_knowledge.md`：合并后的知识总览。
- `chatrel-gap-review/references/foundation_knowledge/dyadic_taxonomy.json`：基础知识库的领域和信号分类。
- `chatrel-gap-review/references/foundation_knowledge/dyadic_papers_manifest.json`：基础知识库的公开论文元数据清单。
- `chatrel-gap-review/references/chat_analysis_pipeline/`：从聊天分析到关系报告的流程知识、schema、prompt 和脚本。

## 安装

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo Zorro-Li/chatrel-gap-review-skill \
  --path chatrel-gap-review
```

安装后重启 Codex，让 skill 元数据重新加载。

## 第一条命令

先准备本地路径变量：

```bash
export HUMANOS_ROOT="/path/to/humanOS"
export CHATREL_REFERENCES_DIR="/path/to/chatrel/references"
```

然后在 Codex 里直接触发：

```text
/chatrel-gap-review
/报告补洞
/知识库蒸馏
看看报告哪里没覆盖
把报告缺口蒸馏到知识库
```

## 工作流

这个 skill 的流程固定为五步：

1. 扫描报告收件箱里的 Markdown 报告。
2. 按 15 个维度判断覆盖状态。
3. 对覆盖不足和缺失维度调用 RAG 证据检索。
4. 输出新的覆盖审计和知识蒸馏结果。
5. 同步更新后续可复用的参考资料。

本地默认路径约定：

```text
报告收件箱：${HUMANOS_ROOT}/chatrel_analysis_reports_inbox
知识输出：${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge
自动化脚本：${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py
RAG 配置：${HUMANOS_ROOT}/Knowledge of 心理学/rag_system/config/evaluation_dimensions.json
```

## 公开知识包

仓库随包发布了三组公开知识包：

```text
chatrel-gap-review/references/chatrel_report_knowledge
chatrel-gap-review/references/foundation_knowledge
chatrel-gap-review/references/chat_analysis_pipeline
```

它们分别提供：

- 报告补洞知识：维度规则、输出字段、覆盖审计快照、论文标题、证据等级、DOI 和参考链接。
- 基础知识库：dyadic taxonomy 和公开论文元数据清单。
- 分析到报告的方法层：analysis blueprint、chat-specific retrieval overview、RAG config、output schema、prompt、视频脚本。

这些目录可以直接作为默认参考资料使用。本地运行产生的新结果仍然写回你自己的 `humanOS` 工作区。

## 边界

这个 skill 服务于“报告补洞与知识蒸馏”阶段。

它要求你已经具备：

- 一个可用的 `humanOS` 本地工作区。
- 已经生成好的 Markdown 报告。
- 上游聊天解析和基础诊断能力。

## 隐私范围

公开仓库只保留可复用分析知识。以下内容保留在本地：

- 原始聊天记录
- 私有报告全文
- 自动运行日志
- JSON evidence bundle
- 私有报告文件名
- 本机绝对路径
- SQLite 数据库
- retrieval chunk stores
- PDF 文件
- 长篇原始证据摘录

## 维护建议

- 改工作流时，更新 `chatrel-gap-review/SKILL.md`。
- 改维度知识时，更新 `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`。
- 改 GitHub 首页说明时，更新根目录 `README.md`。

这个仓库适合保持小、清晰、稳定：入口放在 `SKILL.md`，细节放在 `references/`，主页只负责把产品说清楚。
