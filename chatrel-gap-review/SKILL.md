---
name: chatrel-gap-review
description: |
  聊天记录关系分析报告自动审计与知识库蒸馏。扫描 humanOS 项目收件箱中的 Markdown 报告，判断哪些维度覆盖不足，并把对应论文证据蒸馏到本地知识库和 Skill 参考资料。
  触发方式：/chatrel-gap-review、/报告补洞、/知识库蒸馏、「看看报告哪里没覆盖」「把报告缺口蒸馏到知识库」
---

# chatrel-gap-review：报告缺口审计与知识库蒸馏

你负责把已经生成的聊天记录关系分析报告，转化为可持续改进的知识库。

## 配置变量

- `HUMANOS_ROOT`：humanOS 项目根目录。
- `CHATREL_REFERENCES_DIR`：chatrel Skill 的参考资料目录。

## 默认路径约定

- 报告收件箱：`${HUMANOS_ROOT}/chatrel_analysis_reports_inbox`
- 知识输出：`${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge`
- 自动化脚本：`${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py`
- RAG 配置：`${HUMANOS_ROOT}/Knowledge of 心理学/rag_system/config/evaluation_dimensions.json`
- chatrel 参考资料：`${CHATREL_REFERENCES_DIR}`
- 随包公开知识库：`references/chatrel_report_knowledge`

## 随包知识库

`references/chatrel_report_knowledge` 包含脱敏后的维度规则、输出字段、覆盖审计快照和论文引用。使用这个目录作为默认参考资料；本地运行产生的新审计结果仍输出到 `${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge`。

`references/foundation_knowledge` 提供更宽的 dyadic relationship 基础知识库元数据；`references/chat_analysis_pipeline` 提供从聊天分析到关系报告的流程、schema、prompt 和脚本说明。需要补充基础理论或报告方法时，再读这两个目录。

## 工作流

1. 扫描报告收件箱里的 `.md` 文件。
2. 按 15 个维度判断覆盖状态：已覆盖、覆盖不足、未覆盖。
3. 对覆盖不足和未覆盖维度调用 RAG 证据检索。
4. 把论文证据蒸馏到 `${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge`：
   - `latest_gap_audit.md`
   - `latest_distilled_knowledge.md`
   - `distilled/dimensions/*.md`
5. 同步更新 chatrel Skill 的参考资料：
   - `references/knowledge_gap_findings.md`
   - `references/knowledge_distilled_from_reports.md`

## 执行命令

```bash
: "${HUMANOS_ROOT:?Set HUMANOS_ROOT to your humanOS project root}"
: "${CHATREL_REFERENCES_DIR:?Set CHATREL_REFERENCES_DIR to your chatrel references directory}"

"${HUMANOS_ROOT}/Knowledge of 心理学/.venv/bin/python" \
  "${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py"
```

## 输出原则

- 先给缺口：哪些维度缺、为什么缺、补什么。
- 每个补洞建议要连接到论文证据、聊天记录指标、报告输出字段。
- 低样本、缺语音转写、缺图片内容、缺上下文时，明确降置信度。
- 生成的知识要服务后续 `/chatrel-diagnosis` 和 `/chatrel-triage`。
