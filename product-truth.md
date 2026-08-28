# product-truth · EconLens 可公开声称清单 v0.1
> **全系统事实之锚**：落地页、邮件、任何对外内容里的产品声称，必须能溯源到本文件的一个 PT 编号；Check 层按此逐条核。
> 状态：**草稿，全文待逐条过目**（REQ-001 裁决点⑦）。每条初始 [待过目]，过目后改 ✅；被否决的条目移入 §D 禁止声称。
> 来源标注：`README §x` = D:\econlens\README.md；`disk` = 2026-08-28 磁盘实测。

## A. 定位声称

| ID | 声称（可直接用于英文文案的含义） | 来源 | 状态 |
|---|---|---|---|
| PT-01 | EconLens 是 IB Economics IA commentary 的练习反馈教练：在学生用掉唯一一轮官方教师书面反馈**之前**，提供无限轮 criterion-referenced 练习反馈 | README 首段 | [待过目] |
| PT-02 | **AI 不代写**：只按评分标准逐条诊断、引用学生自己的句子、用苏格拉底式追问；不生成可交付文本 | README 首段 + 反代写合同 | [待过目] |
| PT-03 | IB 经济 IA = 3 篇基于真实新闻的 commentary（各 ≤800 词），占 HL 20% / SL 30%；教师对正式草稿只能给一轮书面反馈 | README「解决什么问题」；**IB 规定属外部事实，须对照当年最新 IB Guide 复核后方可外用** | [待过目] |

## B. 功能声称

| ID | 声称 | 来源 | 状态 |
|---|---|---|---|
| PT-10 | Preflight 机械预检**完全离线**：词数（800 上限）、图表引用、术语密度（内置约 90 词经济术语词库）、九大 key concept 检测、与文章贴合度（4-gram 重叠 + 数字复用）、评价角度线索、段落结构 | README 功能表 | [待过目] |
| PT-11 | Claim/Evidence Map：逐句检测因果与评价性 claim，标记附近无证据信号的观点 | README 功能表 | [待过目] |
| PT-12 | AI criterion 反馈按 A–E 五 criterion 逐条：分带估计＋优点＋问题＋苏格拉底追问 | README 功能表 | [待过目] |
| PT-13 | **反代写合同**（违约拒绝展示，自动重试一次）：引文必须逐字存在于草稿、字段 ≤45 词、禁改写类措辞、追问必须以问号结尾 | README 功能表 + 测试覆盖 | [待过目] |
| PT-14 | Workflow Coach 只回答「你现在的推理哪一步还没有被证明」，从不回答「应该怎么写」；evidence 必须锚定（`check:` 或 `quote:`），AI 输出永不改变机械评分结果 | README v0.3 节 | [待过目] |
| PT-15 | 无 API key 也可用：确定性预检＋过程档案＋同格式回退 coach（内置问题库）；OpenAI 兼容端点可换 provider 不动产品逻辑 | README 快速开始 + 回退节 | [待过目] |
| PT-16 | 过程档案：每轮草稿 SHA-256、词数、与上轮相似度、分带轨迹，一键导出 HTML 诚信报告 | README 功能表 | [待过目] |
| PT-17 | 跨三篇 commentary 的 portfolio 合规检查：不同 unit / key concept / 来源 | README 功能表 | [待过目] |

## C. 数字声称

| ID | 声称 | 来源 | 状态 |
|---|---|---|---|
| PT-20 | 106 项自动化测试，全部离线（LLM 走 mock） | **disk：`pytest --collect-only` = 106（2026-08-28 实测）**。⚠️ README 写 88 已过时，须回修 README，两处不一致前本条只用 106 | [待过目] |
| PT-21 | 评分标准按 IB Economics Guide（first assessment 2022）转写：A(3)/B(2)/C(2)/D(3)/E(4)，单篇 14 分、portfolio 45 分 | README 诚实边界；**转写件非官方件，外用必须带"transcribed from"限定** | [待过目] |

## D. 边界与禁止声称（Check 层黑名单，硬性）

| ID | 禁止 | 依据 |
|---|---|---|
| PT-90 | ❌ 任何**学习增益/提分效果**声称（"提高你的 IA 分数"类）——未做真实学生对照实验 | README 诚实边界 + 证据纪律（E-PRJ-EDU3 禁写项） |
| PT-91 | ❌ 分带估计说成**分数预测**；正式评分以教师与 IB moderation 为准 | README 诚实边界 |
| PT-92 | ❌ 暗示 **IB 官方关联或背书**；落地页须带 "not affiliated with or endorsed by the IB" 类声明（IB 为注册商标） | 常识合规，[待过目：措辞] |
| PT-93 | ❌ 过程档案说成**作者身份证明**——只能证明修改过程逐轮发生在工具内 | README 诚实边界 |
| PT-94 | ❌ 300 人压测/合成面板数据当**真实用户数据**引用 | 证据纪律（pilot_300=合成） |
| PT-95 | ❌ "unlimited feedback" 不得暗示等同或替代教师反馈；措辞限定为 practice feedback | PT-01 的边界面 |
