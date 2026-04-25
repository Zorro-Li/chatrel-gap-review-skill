# chatrel-gap-review

微信聊天记录分析、两个人关系分析、聊天记录生成关系报告的开源方法库。

这个仓库把一条完整链路放在一起：

- 从聊天记录里提取关系信号。
- 把关系信号组织成可引用的分析维度。
- 把分析维度写成关系报告。
- 再把报告里的缺口回流成知识库。

## 这类项目在小红书最容易拿到什么流量

如果目标是小红书流量，最大入口不是泛泛的“心理学知识”，而是搜索流量。

这个题材最容易被搜的不是抽象词，而是具体问题词：

- 微信聊天记录分析
- 两个人关系分析
- 聊天记录生成关系报告
- 聊天记录怎么看关系强度
- 回复速度怎么看关系
- 语言风格匹配怎么看
- 聊天里的权力角色怎么看
- 冲突破裂和修复怎么看

所以这个 README 不按“技术仓库说明书”的方式写，而按“用户正在搜索什么”来写。

## 你大概率是因为这些问题进来的

- 微信聊天记录能不能分析两个人关系？
- 聊天记录怎么做成一份关系分析报告？
- 两个人关系强不强，聊天里看什么？
- 回复速度、互惠、语言风格匹配，怎么落成结构化判断？
- 聊天分析怎么做得更可靠，怎么避免拍脑袋？
- 报告写完以后，怎么继续补洞，怎么把缺口沉淀成知识？

这个仓库就是为这些问题准备的。

## 这个仓库到底是什么

这不是一个只会输出结论的 prompt 仓库。

这是一个把“聊天分析 -> 关系报告 -> 报告补洞 -> 知识沉淀”做成方法资产的开源 skill 包。

它适合三类人：

- 想做微信聊天记录分析的人。
- 想把两个人关系分析做成内容或产品的人。
- 已经能写报告，但报告质量不稳定、知识沉淀不稳定的人。

## 仓库里有什么

```text
chatrel-gap-review/
├── SKILL.md
└── references/
    ├── README.md
    ├── chatrel_report_knowledge/
    ├── foundation_knowledge/
    └── chat_analysis_pipeline/
```

三组公开知识包各自负责不同事情：

- `chatrel_report_knowledge/`
  - 负责报告补洞。
  - 提供维度规则、输出字段、覆盖审计快照、蒸馏后的维度知识。

- `foundation_knowledge/`
  - 负责基础知识库。
  - 提供 dyadic taxonomy 和公开论文元数据清单。

- `chat_analysis_pipeline/`
  - 负责从聊天分析到关系报告的方法层。
  - 提供 analysis blueprint、chat-specific retrieval overview、RAG config、output schema、prompt、视频脚本。

## 如果你要做“小红书能跑起来”的内容

这个仓库最适合拆成搜索型内容矩阵。

不要先讲“大而全”的关系学理论。先讲用户会主动搜的问题。

优先顺序应该是：

1. 先打总需求词：
   - 微信聊天记录分析
   - 两个人关系分析
   - 聊天记录关系报告

2. 再打可拆的子问题词：
   - 关系强度
   - 回复速度
   - 语言风格匹配
   - 共情支持
   - 权力角色
   - 冲突修复

3. 再打“怎么做得可靠”这种方法词：
   - 聊天分析怎么做得可靠
   - 聊天记录分析怎么避免误判
   - 聊天分析怎么写成报告

仓库里已经直接给了这类拆法：

- `chat_analysis_pipeline/video_scripts/`：8 条可直接做成小红书短视频的逐字稿。
- `chat_analysis_pipeline/chat_record_analysis_blueprint.md`：从字段到特征到报告的总蓝图。
- `chat_analysis_pipeline/rag_system/`：报告生成的维度、schema 和 prompt。

## 你会拿到什么

如果你是做产品，你会拿到：

- 一套聊天关系分析的维度体系。
- 一套从聊天记录到关系报告的结构化方法。
- 一套报告补洞和知识回流机制。

如果你是做内容，你会拿到：

- 一组强搜索需求的内容主题。
- 一套能拆成系列内容的分析框架。
- 一组可以反复复用的视频脚本和方法文档。

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

1. 扫描已经生成好的 Markdown 关系报告。
2. 按 15 个维度判断哪些内容已覆盖、哪些内容覆盖不足、哪些内容缺失。
3. 对覆盖不足和缺失维度调用 RAG 证据检索。
4. 输出新的覆盖审计和知识蒸馏结果。
5. 把结果同步到后续可复用的参考资料。

本地默认路径约定：

```text
报告收件箱：${HUMANOS_ROOT}/chatrel_analysis_reports_inbox
知识输出：${HUMANOS_ROOT}/Knowledge of 心理学/chatrel_report_knowledge
自动化脚本：${HUMANOS_ROOT}/Knowledge of 心理学/automation/chatrel_report_gap_audit.py
RAG 配置：${HUMANOS_ROOT}/Knowledge of 心理学/rag_system/config/evaluation_dimensions.json
```

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
- 改基础知识库时，更新 `chatrel-gap-review/references/foundation_knowledge/`。
- 改分析到报告的方法层时，更新 `chatrel-gap-review/references/chat_analysis_pipeline/`。
- 改报告补洞知识时，更新 `chatrel-gap-review/references/chatrel_report_knowledge/`。
- 改 GitHub 首页说明时，更新根目录 `README.md`。

这个仓库最有价值的地方，不是“又一个 AI 分析工具”，而是它把聊天关系分析做成了可以复用、可以拆内容、可以继续长知识库的资产。
