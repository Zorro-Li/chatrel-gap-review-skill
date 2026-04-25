# chatrel-gap-review

一个面向 Codex 的开源 skill，用来审计聊天关系分析报告里的覆盖缺口，并把缺失维度背后的论文证据、指标规则和输出字段蒸馏成可复用知识库。

这个 skill 适合已经有聊天关系分析报告产出的工作流。它负责补洞、校验覆盖面、沉淀知识，不负责原始聊天记录导入和基础报告生成。

## 它能做什么

- 扫描报告收件箱里的 Markdown 报告。
- 按 15 个关系分析维度判断覆盖状态。
- 对覆盖不足和缺失维度拉取证据并生成补洞建议。
- 把补洞结果沉淀成结构化知识文件。
- 同步更新 skill 可复用的参考资料。

## 适用场景

- 你已经能生成聊天关系分析报告，想做报告质检。
- 你希望把“这次没写好”的问题沉淀成“下次自动补上”的知识。
- 你需要一个研究证据驱动的报告补洞层，而不是纯经验修补。

## 覆盖维度

当前知识库覆盖以下 15 个关系分析维度：

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

每个维度都会被归入以下状态之一：

- 已覆盖
- 覆盖不足
- 缺失

## 仓库内容

```text
chatrel-gap-review/
├── SKILL.md
└── references/
    └── chatrel_report_knowledge/
        ├── PUBLICATION_NOTES.md
        ├── README.md
        ├── latest_gap_audit.md
        ├── latest_distilled_knowledge.md
        └── distilled/
            └── dimensions/*.md
```

关键文件：

- `chatrel-gap-review/SKILL.md`：skill 入口，定义触发方式、路径约定和执行流程。
- `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`：按维度拆分的蒸馏知识。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_gap_audit.md`：当前审计框架的覆盖快照。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_distilled_knowledge.md`：合并后的知识总览。

## 安装

使用 Codex 自带的 skill installer：

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo Zorro-Li/chatrel-gap-review-skill \
  --path chatrel-gap-review
```

安装后重启 Codex，让 skill 元数据重新加载。

## 快速开始

1. 设置本地路径变量：

```bash
export HUMANOS_ROOT="/path/to/humanOS"
export CHATREL_REFERENCES_DIR="/path/to/chatrel/references"
```

2. 确保本地工作区具备以下路径约定：

```text
报告收件箱：${HUMANOS_ROOT}/chatrel_analysis_reports_inbox
知识输出：${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge
自动化脚本：${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py
RAG 配置：${HUMANOS_ROOT}/Knowledge of 心理学/rag_system/config/evaluation_dimensions.json
```

3. 在 Codex 中触发 skill：

```text
/chatrel-gap-review
/报告补洞
/知识库蒸馏
看看报告哪里没覆盖
把报告缺口蒸馏到知识库
```

## 工作方式

这个 skill 的工作流分成五步：

1. 扫描报告收件箱中的 `.md` 报告。
2. 依据 15 个维度判断哪些内容已经覆盖、哪些内容不足、哪些内容缺失。
3. 对覆盖不足和缺失维度调用 RAG 证据检索。
4. 输出新的覆盖审计和知识蒸馏结果。
5. 把结果同步到 chatrel skill 的参考资料，供后续诊断和分流复用。

## 输出文件

本地运行后会生成或更新以下文件：

```text
latest_gap_audit.md
latest_distilled_knowledge.md
distilled/dimensions/*.md
```

这些输出分别用于：

- 记录本次报告在哪些维度存在缺口。
- 汇总本次新增的蒸馏知识。
- 让每个维度都有可独立维护、可复用的知识文件。

## 公开知识包

这个仓库随包发布了一个脱敏后的公开知识包：

```text
chatrel-gap-review/references/chatrel_report_knowledge
```

公开知识包包含：

- 维度规则
- 输出字段
- 覆盖审计快照
- 论文标题
- 证据等级
- DOI 和参考链接

这个公开知识包可以直接作为默认参考资料使用。本地运行时，新产出的私有结果仍然写回你自己的 `humanOS` 工作区。

## 隐私与边界

公开仓库只保留可复用分析知识。以下内容不在公开仓库中：

- 原始聊天记录
- 私有报告全文
- 自动运行日志
- JSON evidence bundle
- 私有报告文件名
- 本机绝对路径
- PDF 文件
- 长篇原始证据摘录

这个 skill 的设计目标是公开规则和结构，保留私有数据在本地。

## 局限

- 它依赖一个已经存在的 `humanOS` 本地工作区。
- 它假设输入是已经生成好的 Markdown 报告。
- 它服务的是“报告补洞与知识蒸馏”阶段，不覆盖聊天解析和基础诊断的完整上游流程。

## 适合怎么维护

- 改工作流时，更新 `chatrel-gap-review/SKILL.md`。
- 改维度知识时，更新 `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`。
- 改 GitHub 首页说明时，更新根目录 `README.md`。

这个仓库适合保持小而清晰：入口放在 `SKILL.md`，细节放在 `references/`，公开主页只解释用途、安装、使用方式和边界。
