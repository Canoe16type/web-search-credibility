# Web Search Credibility

面向任意 Agent 的高可信度联网检索 Skill。

English: [README.en.md](README.en.md) · [SKILL.en.md](SKILL.en.md)

它规定一套可重复的检索流程：什么时候搜索、如何选择权威来源、如何交叉验证、如何核对原文、来源冲突时怎么处理，以及如何标注来源。

不依赖特定搜索厂商、聊天平台或 Markdown 方言；运行时提供网页搜索或页面抓取能力即可使用。

## 适用场景

- 产品 / API 文档、版本、价格、参数
- 政策、标准、法规、公告
- 企业与金融信息
- 游戏、动漫、虚构作品的官方设定
- 核对链接或某个说法
- Agent 准备凭记忆回答可验证事实时

## 设计原则

- **官方与一手来源优先**
- **关键结论交叉验证**；单一来源要标注
- **读原文，不只看摘要**
- **区分事实、观点和推测**
- **有冲突就说明冲突**
- **引用真正用过的来源**
- **不为显得认真而搜索**

## 文件

```text
SKILL.md                             核心流程与规则
references/authoritative-sources.md  各领域来源清单与检索模板
examples/citation-styles.md          三种引用风格示例
LICENSE                              MIT
```

## 安装

把 `SKILL.md` 和 `references/` 放进 Agent 的 Skill 目录，或让 Agent 直接读取本仓库。

工具名不同时，把 `SKILL.md` 里的能力名映射到实际工具即可，不需要改代码。

## 许可证

MIT，见 [LICENSE](LICENSE)。

Copyright (c) 2026 Canoe16type
