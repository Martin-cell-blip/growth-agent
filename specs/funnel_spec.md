# funnel_spec · 漏斗口径定义 v0.1
> REQ-001 R1 交付物 · 本文件是漏斗口径的**唯一真源**（PRD 与周报引用此处，不得另定义）
> 状态：草稿（AC-01/AC-02 验收前须过一次冷读测试）

## 1. 三态判定

| 状态 | 判定边界 | 不算的情形 |
|---|---|---|
| **visitor** | 落地页产生 `visit` 事件的独立访客（以 Plausible Unique Visitors 口径为准，随工具口径披露） | 爬虫（Plausible 默认过滤）；预览/自测流量（用 `utm_source=selftest` 标记并在报表剔除） |
| **lead** | 完成邮箱**双重确认**（`email_confirm` 事件） | 只提交未确认；一次性邮箱域（黑名单校验，v0.1 人工抽查） |
| **activated** | 在**托管 Demo** 内首次完成一次草稿分析（`first_analysis`：preflight 结果返回即算，无论是否使用 coach 反馈） | 打开 Demo 未提交草稿；粘贴样例文章但未运行分析 |

## 2. 六事件定义

| # | 事件 | 触发条件 | 去重规则 |
|---|---|---|---|
| E1 | `visit` | 落地页 pageview | Plausible 默认（同访客同日计一次 unique） |
| E2 | `scroll50` | 落地页滚动过 50% 视口深度 | 每访客每次会话至多一次 |
| E3 | `email_submit` | 留资表单提交成功（服务端确认收到） | 同邮箱重复提交计一次 |
| E4 | `email_confirm` | 点击确认邮件内链接，double opt-in 完成 | 同邮箱终身一次 |
| E5 | `first_analysis` | 托管 Demo 返回一次完整 preflight 结果 | 同会话去重；跨会话以 Demo 侧匿名 id 尽力去重（见 §4 限制） |
| E6 | `d7_return` | activated 后第 4–10 天内再次产生 Demo 分析事件 | 每 activated 用户至多一次 |

## 3. 指标与换算

- **北极星**：visitor→activated 转化率 = `distinct(E5) / distinct(E1)`（同报表期）
- 中段诊断：E1→E3（留资率）、E3→E4（确认率）、E4→E5（激活率）
- **n 披露口径**：任何转化率必须同行披露分子分母绝对值；n<30 的比率标注"仅方向参考"

## 4. v0.1 已知限制（如实披露，不掩饰）

1. **聚合漏斗，非用户级链路**：Plausible 无 cookie，落地页访客与 Demo 激活者无法逐人关联；比率为聚合计数之比。用户级归因（邮件带一次性 token 链接）留给 v0.2。
2. **跨站计数**：落地页与 Demo 若分属两个域，E1 与 E5 分别计数——渠道归因靠 UTM 贯穿。
3. 自测流量剔除依赖纪律（`utm_source=selftest`），无技术强制。

## 5. 依赖声明（⚠️ REQ-001 范围修订提案）

`first_analysis` 与 `d7_return` 依赖一个**可公开访问的托管 Demo**。EconLens 原生支持无 key 模式（确定性预检 + 同格式回退 coach，零 LLM 成本、无滥用面），具备零成本托管条件。**原 REQ-001 未含此项 → 提案新增 R7「托管 Demo（无 key 模式）」**，待裁决；裁决前 E5/E6 无法上线，漏斗只能测到 E4。
