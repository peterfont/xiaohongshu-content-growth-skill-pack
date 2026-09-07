---
name: xiaohongshu-content-experiment-orchestrator
version: 18.0.0
language: zh-CN
---
# 小红书内容实验总控 v18

## 使命
把内容运营变成：研究、实验、反馈、学习，而不是一次性文案生成。

## 总流程
素材 → 选题 → [按需 Research] → 行为预测 → 内容生成 → 发布 → 数据诊断 → 策略学习 → 下一轮。

## 路由规则
1. 先读取 `topic-planner`。
2. 若内容需要外部事实、用户语言、评论、案例、竞品或市场素材，调用 `research-agent`。
3. 素材确定后调用 `behavior-predictor`。
4. 再调用 `content-generator`。
5. 用户需要封面/多页图文时调用 `visual-generator`。
6. 发布后只进入 `performance-analyst` + `strategy-learner`，不要把复盘混进生产流程。

## Research 深度模式
当路由到 research-agent 时，不允许只做“搜几条资料 + 总结”。默认要求执行：
搜索词矩阵 → 多来源收集 → 原始素材池 → 分类 → 3–7个主题簇 → 用户语言库 → 正反观点/反例 → 案例/数据 → 证据缺口 → 最值得使用素材。

产品类必须额外检查详情页、竞品、好评、差评、问大家/Q&A、评论，并完成“参数→功能→场景→结果→痛点”的转换。

评论区研究按“轻量访谈”处理，提取需求、场景、语言、异议、办法、经历和行动阻力。

Research 完成后才进入 Behavior Predictor 与 Content Generator。



## Deep Research 路由（v18）
当进入 Research 模式后，再按复杂度选择执行器：
- L0 无需外部研究：已有充分一手素材；
- L1 普通 Web：少量来源即可回答；
- L2 完整 Research：需要素材池、社区观点、用户语言、反例；
- L3 ChatGPT Deep Research：跨来源、近期、争议、证据链复杂或需要多轮补缺口。

若运行环境支持 ChatGPT Deep Research：
1. 先让 `research-agent` 生成 Research Brief；
2. 把 Research Brief 交给 Deep Research；
3. Deep Research 只负责检索、阅读、核验、归纳；
4. 返回后由 `research-agent` 二次验收；
5. 验收通过后，才进入 `behavior-predictor` 与 `content-generator`。

若环境不支持 Deep Research：
- 不得声称已经调用；
- 使用当前可用 Web/搜索工具执行同一 Research Brief；
- 在 Research Pack 标记实际执行方式。

原则：
> Deep Research 是 research-agent 的研究执行器，不是独立平行 Skill。


## 快速模式与研究模式
- 快速模式：真实经历/已验证母题/已有充分素材。
- 研究模式：知识、行业、产品、舆情、评论、案例、数据。

## 发布前必须产出
选题、母题/子题、用户层、V等级、H等级、主行为、关注理由、点击五维、失败点、唯一核心假设、标题、正文、标签、配图结构/视觉任务。

## 最高优先级规则
- 选题负责研究，标题负责点击，正文负责兑现。
- 用户先看到自己，再看到知识。
- 一篇只设一个主行为，最多两个次行为。
- 一篇只验证一个核心假设。
- 预测是可验证假设，不是结果承诺。
