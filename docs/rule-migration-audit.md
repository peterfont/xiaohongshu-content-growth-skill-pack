# v9-v15 规则迁移审计

本文件只做迁移索引，不是第二份运行规则源。当前事实源只有 `skills/*/SKILL.md`。

| 来源 | 关键规则 | v16 落点 |
|---|---|---|
| v9 | 用户三层、行为类型、6页结构 | topic / behavior / visual |
| v9/v10 | 6页必须6个独立生成任务 | visual-generator |
| v11 | 点击五维 | behavior-predictor |
| v11 | 身份利益/行动选择/抽象认知 | topic-planner |
| v11 | 用户先看到自己，再看到知识 | behavior / content |
| v11 | 高收藏低CTR先救入口 | behavior / performance |
| v11 | 评论问题只是出口 | behavior |
| v11 | 路径打开型 | behavior |
| v11 | H0-H3、V1-V4 | topic / strategy |
| v12 | 正文≤1000字，默认650–900，纯文本 | content-generator |
| v13 | 选题≠标题≠正文；母题/子题 | topic / content |
| v14 | 关注理由与互动分离 | behavior / content |
| v15 | 标题≤20字，默认12–18 | content-generator |
| 新增 | 搜索→收集→整理→删减→重写→朗读→修改 | research-agent |
| 新增 | 评论作为用户语言数据库 | research-agent |
| 修正 | 不用统一绝对曝光阈值给账号定级 | performance-analyst |

重构原则：
- 保留有效规则，不保留重复补丁文本；
- 新规则覆盖旧冲突规则；
- 旧历史版本不作为当前运行依赖；
- 只维护这一套模块化版本。

补充迁移：v11 当前账号内容比例、H1/H2重点假设、账号长期主线已迁移到 `current-account-experiment-rules.md`。
