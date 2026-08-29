# CHANGELOG
> 每版本三问：需求说了什么 → 实际交付什么 → 评测说了什么

## [Unreleased] · v0.1 基线（W1-2）
- 2026-08-29 **落地页 v1 上仓**（`site/index.html` 单文件，学生/教师双变体 `?v=` 切换，Fraunces×Newsreader 阅卷手稿风）：hero 标注卡用**真实确定性 coach 输出**非 mockup；表单与分析未配置时安全降级（实测拦截 ✓）；声称→PT 映射见 `site/claims_map.md`（上线只需 11 条 PT 过目）
- 2026-08-29 **R3 修订：Plausible → PostHog**（免费 1M events/月＋用户级漏斗；E1–E3 匿名段 cookieless memory 无 banner，E4 起邮件 token identify）——消掉 funnel_spec 原§4.1"聚合漏斗"限制
- 2026-08-28 **定名 growth-agent**；ADR-002 同日修订：公开范围收窄为**系统公开＋业务数据私有**（`data/` 整目录不入仓，业务指标经批准后以脱敏聚合形态发布）
- 2026-08-28 仓库初始化：PRD v0.1（草稿，2/7 决策点已闭合）、REQ-001（基线漏斗，11 条 AC↔EV）、ADR-001（Agent 只提案，管道才执行）、ADR-002（全公开 + 中文为主 + PII 红线）、实验预注册模板、评测演进约定
