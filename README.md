# chatrel-gap-review：聊天关系报告缺口审计 Skill

这是一个用于 Codex 的公开 skill。它会审计聊天关系分析报告，找出关系分析维度里的覆盖缺口，并把可复用的论文证据、指标规则和输出字段蒸馏成知识库。

公开仓库地址：`Zorro-Li/chatrel-gap-review-skill`

## 它解决什么问题

聊天关系分析报告很容易出现三个问题：

- 有些维度写得很细，有些维度完全缺席。
- 报告结论缺少可追溯的论文证据和指标来源。
- 每次报告补洞都靠人工经验，难以沉淀成下一次可复用的知识。

`chatrel-gap-review` 的目标是把报告审计变成稳定流程：先判断覆盖状态，再定位缺口，再把缺口转化成结构化知识。

## 它会审计哪些内容

当前知识库按 15 个关系分析维度组织：

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

每个维度都会围绕三个判断结果输出：

- 已覆盖
- 覆盖不足
- 缺失

## 仓库结构

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

- `chatrel-gap-review/SKILL.md`：Codex skill 入口文件，定义触发方式、路径约定、工作流和执行命令。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_gap_audit.md`：脱敏后的覆盖审计快照。
- `chatrel-gap-review/references/chatrel_report_knowledge/latest_distilled_knowledge.md`：合并后的脱敏知识库。
- `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`：按维度拆分的知识文件。
- `chatrel-gap-review/references/chatrel_report_knowledge/PUBLICATION_NOTES.md`：公开发布时的范围说明。

## 制作流程

这次发布按以下流程完成：

1. 定位本地原始 skill。
2. 按 Codex skill 标准结构整理成 `chatrel-gap-review/SKILL.md`。
3. 把本机绝对路径替换成配置变量：
   - `HUMANOS_ROOT`
   - `CHATREL_REFERENCES_DIR`
4. 检查本地聊天关系报告知识库，拆出可公开发布的参考资料。
5. 保留可复用内容：
   - 维度规则
   - 审计字段
   - 输出结构
   - 论文标题
   - 证据等级
   - DOI 引用
6. 把私有材料留在本地：
   - 原始聊天记录
   - 自动运行日志
   - JSON evidence bundle
   - 私有报告文件名
   - 本机绝对路径
   - PDF 文件
   - 长篇原始证据摘录
7. 对公开目录做敏感信息扫描。
8. 使用 GitHub deploy key 从终端推送到 GitHub。

## 安装方式

使用 Codex 自带的 skill installer 安装：

```bash
CODEX_HOME="${CODEX_HOME:-$HOME/.codex}"
python "$CODEX_HOME/skills/.system/skill-installer/scripts/install-skill-from-github.py" \
  --repo Zorro-Li/chatrel-gap-review-skill \
  --path chatrel-gap-review
```

安装后重启 Codex，让 skill 元数据重新加载。

## 触发方式

可用触发语：

- `/chatrel-gap-review`
- `/报告补洞`
- `/知识库蒸馏`
- `看看报告哪里没覆盖`
- `把报告缺口蒸馏到知识库`

## 本地运行配置

本地自动化依赖两个路径变量：

```bash
export HUMANOS_ROOT="/path/to/humanOS"
export CHATREL_REFERENCES_DIR="/path/to/chatrel/references"
```

`HUMANOS_ROOT` 指向本地 humanOS 项目根目录。
`CHATREL_REFERENCES_DIR` 指向 chatrel skill 的参考资料目录。

skill 内部默认使用以下路径约定：

```text
报告收件箱：${HUMANOS_ROOT}/chatrel_analysis_reports_inbox
知识输出：${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge
自动化脚本：${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py
RAG 配置：${HUMANOS_ROOT}/Knowledge of 心理学/rag_system/config/evaluation_dimensions.json
随包公开知识库：references/chatrel_report_knowledge
```

## 输出结果

本地运行后会生成或更新三类知识文件：

```text
latest_gap_audit.md
latest_distilled_knowledge.md
distilled/dimensions/*.md
```

这些文件用于服务后续的聊天关系诊断、报告补洞和知识库迭代。

## 隐私边界

公开仓库只保留可复用的分析框架和论文支持的结构化规则。私有聊天记录、私有报告语料、运行日志、证据包和本机路径均保留在本地工作区。

推送前执行了敏感词扫描，检查范围包含：

- 本机路径
- 用户名
- 私有项目名
- 私有报告名
- 邮箱
- 手机号
- 聊天字段标识

## GitHub 推送方式

仓库地址：

```text
https://github.com/Zorro-Li/chatrel-gap-review-skill
```

本地通过仓库级 GitHub deploy key 推送。deploy key 仅授权这个仓库，私钥保存在本机 SSH 目录，仓库内只保存公开 skill 和脱敏知识库。

## 推荐维护方式

新增知识时，优先更新 `chatrel-gap-review/references/chatrel_report_knowledge/distilled/dimensions/*.md`。
新增工作流时，更新 `chatrel-gap-review/SKILL.md`。
新增公开说明时，更新根目录 `README.md`。
每次推送前执行敏感信息扫描，确认公开目录只包含可复用知识。
