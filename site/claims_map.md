# claims_map · 落地页声称 → product-truth 映射
> Check 层的人工版：页面上每条产品声称在此对账。**上线前置条件 = 下表引用的 PT 条目全部过目 ✅**（不必等 21 条全过，只需这 11 条）。
> 非声称内容（真实 coach 输出引文、设计文案）不在映射范围，但 coach 引文已在 2026-08-28 本地实测原样复现。

| 页面位置 | 页面表述（要义） | PT | 状态 |
|---|---|---|---|
| Hero 主标+副标（双变体） | 教师只有一轮官方书面反馈；EconLens 提供无限轮 criterion-referenced **练习**反馈在前 | PT-01, PT-03 | 待过目 |
| Hero 副标（教师版） | 学生先清机械问题，教师那一轮花在经济学上 | PT-01 | 待过目 |
| 检查条 strip | 8 项检查：≤800 词 / ~90 术语词库 / 9 key concepts / 离线即时 | PT-10 | 待过目 |
| §1 步骤 2 | 检查映射 criteria A–E | PT-10, PT-12 | 待过目 |
| §1 步骤 3 | 每轮留痕：词数/相似度/分带轨迹，可导出过程报告 | PT-16 | 待过目 |
| §2 标题 | It will never write it for you（代码强制执行，违约拒绝展示） | PT-02, PT-13 | 待过目 |
| §2 R·01–R·04 | 逐字引文 / 只提问不改写 / evidence 锚定 / AI 不改机械结果 | PT-13, PT-14 | 待过目 |
| §3 三条引文 | 真实确定性 coach 输出（2026-08-28 实测原文） | —（产品输出非声称） | 已实测 ✓ |
| Footer 1 | not affiliated with or endorsed by the IBO；IB 为注册商标 | PT-92 | 待过目（措辞重点） |
| Footer 2 | 分带估计=练习参考非分数预测 | PT-91 | 待过目 |
| Footer 3 | 过程档案不证明作者身份 | PT-93 | 待过目 |
| Footer 4 | 标准转写自 IB Guide (first assessment 2022)，高风险使用对照现行 Guide | PT-21 | 待过目 |

**部署前替换清单**：`BUTTONDOWN_USERNAME`（两处表单 action）、`POSTHOG_KEY`（一处常量）。未替换时表单不外发（JS 拦截并提示）、分析不初始化（零控制台错误）。

**刻意未写进页面的**（PT-90/94/95 红线自查）：任何提分/学习增益表述 ✗；任何用户数/压测数 ✗；"unlimited feedback" 均限定为 practice feedback ✗→✓。
