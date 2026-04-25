# Chatrel Gap Review Skill

A public Codex skill for auditing chat relationship analysis reports, identifying missing analytical dimensions, and distilling reusable relationship-science knowledge into a local reference base.

This repository is English-first for the GitHub homepage. A Chinese version is included below.

## What This Skill Does

`chatrel-gap-review` helps Codex review Markdown relationship-analysis reports and answer three questions:

- Which relationship-analysis dimensions are covered?
- Which dimensions are missing or underdeveloped?
- Which literature-backed rules, metrics, and output fields should be added to the knowledge base?

The skill is designed for a local `humanOS` workflow, but the published package contains only reusable skill instructions and redacted reference knowledge.

## Repository Contents

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

Key files:

- `chatrel-gap-review/SKILL.md`: the Codex skill entrypoint.
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_gap_audit.md`: redacted audit coverage snapshot.
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_distilled_knowledge.md`: merged redacted knowledge distilled from report gaps.
- `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`: one reusable knowledge file per analysis dimension.
- `chatrel-gap-review/references/chatrel_report_knowledge/PUBLICATION_NOTES.md`: what was included and excluded during publication.

## How This Package Was Built

1. The original local skill was located inside the `humanOS` workspace.
2. A clean public repository layout was created with the standard Codex skill folder shape: `chatrel-gap-review/SKILL.md`.
3. Machine-specific paths were replaced with environment variables:
   - `HUMANOS_ROOT`
   - `CHATREL_REFERENCES_DIR`
4. The local relationship-report knowledge base was reviewed and split into a public subset.
5. Reusable dimension rules, audit fields, literature titles, evidence levels, and DOI references were kept.
6. Private material was excluded before publication:
   - raw chat records
   - generated `runs/` logs
   - JSON evidence bundles
   - private report filenames
   - local absolute paths
   - PDF files
   - long extracted evidence snippets
7. The public tree was scanned for sensitive strings before push.
8. The repository was pushed through SSH using a repository-scoped GitHub deploy key. The private key remains local and is not committed.

## Install

Install the skill from GitHub:

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo Zorro-Li/chatrel-gap-review-skill \
  --path chatrel-gap-review
```

Restart Codex after installation so the skill metadata is reloaded.

## Usage

Trigger examples:

- `/chatrel-gap-review`
- `/报告补洞`
- `/知识库蒸馏`
- `看看报告哪里没覆盖`
- `把报告缺口蒸馏到知识库`

For local automation, set the required paths first:

```bash
export HUMANOS_ROOT="/path/to/humanOS"
export CHATREL_REFERENCES_DIR="/path/to/chatrel/references"
```

Then follow the command documented in `chatrel-gap-review/SKILL.md`.

## Privacy Scope

The published files are intended as reusable analysis knowledge. They contain no raw chat records and no private report corpus. The public package keeps the reasoning framework and literature-backed schema, while local execution can still write private audit outputs back into a private `humanOS` workspace.

## 中文说明

### Chatrel Gap Review Skill

这是一个公开的 Codex skill，用来审计聊天关系分析报告里的缺口，判断哪些关系分析维度覆盖不足，并把可复用的论文证据、指标和输出字段蒸馏成知识库。

GitHub 主页采用英文优先；中文说明放在下半部分，方便中文使用者安装和理解。

### 这个 Skill 做什么

`chatrel-gap-review` 会帮助 Codex 检查 Markdown 格式的关系分析报告，并回答三个问题：

- 哪些关系分析维度已经覆盖？
- 哪些维度缺失或覆盖不足？
- 哪些论文支持的规则、指标和输出字段应该补进知识库？

它服务于本地 `humanOS` 工作流。公开仓库只包含 skill 指令和已脱敏的参考知识。

### 仓库内容

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

主要文件：

- `chatrel-gap-review/SKILL.md`：Codex skill 入口文件。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_gap_audit.md`：脱敏后的覆盖审计快照。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_distilled_knowledge.md`：合并后的脱敏知识库。
- `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`：按分析维度拆开的知识文件。
- `chatrel-gap-review/references/chatrel_report_knowledge/PUBLICATION_NOTES.md`：公开发布时包含和排除的范围。

### 这次是怎么做成并上传的

1. 在本地 `humanOS` 工作区里定位原始 skill。
2. 按 Codex skill 的标准结构整理成公开目录：`chatrel-gap-review/SKILL.md`。
3. 把本机路径替换成配置变量：
   - `HUMANOS_ROOT`
   - `CHATREL_REFERENCES_DIR`
4. 检查本地关系报告知识库，并拆出可公开发布的子集。
5. 保留可复用的维度规则、审计字段、论文标题、证据等级和 DOI 引用。
6. 发布前排除私有内容：
   - 原始聊天记录
   - 自动运行产生的 `runs/` 日志
   - JSON evidence bundle
   - 私有报告文件名
   - 本地绝对路径
   - PDF 文件
   - 长篇原始证据摘录
7. 推送前对公开目录做敏感词扫描。
8. 通过 SSH 和 GitHub deploy key 从终端推送到 GitHub。私钥只保存在本机，没有提交进仓库。

### 安装

从 GitHub 安装：

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo Zorro-Li/chatrel-gap-review-skill \
  --path chatrel-gap-review
```

安装后重启 Codex，让 skill 元数据重新加载。

### 使用方式

触发方式：

- `/chatrel-gap-review`
- `/报告补洞`
- `/知识库蒸馏`
- `看看报告哪里没覆盖`
- `把报告缺口蒸馏到知识库`

本地跑自动化脚本前，先设置路径：

```bash
export HUMANOS_ROOT="/path/to/humanOS"
export CHATREL_REFERENCES_DIR="/path/to/chatrel/references"
```

具体执行命令见 `chatrel-gap-review/SKILL.md`。

### 脱敏边界

公开文件只作为可复用的分析知识使用。仓库里没有原始聊天记录，也没有私有报告语料。公开包保留分析框架和论文支持的结构化规则；本地运行时产生的新审计结果仍然可以写回私有的 `humanOS` 工作区。
