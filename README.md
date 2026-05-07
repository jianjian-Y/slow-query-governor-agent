# slow-query-governor-agent

> 基于 OpenClaw 的自动化数据库慢查询治理 Agent

## 🎯 核心功能

7×24 小时自动扫描生产环境慢查询日志，生成多版本索引优化方案，沙箱验证后自动提交带性能对比报告的 PR。

## 📊 落地效果

| 指标 | 优化前 | 优化后 |
|------|--------|--------|
| 日均分析慢查询 | 人工 50 条 | 自动 8,000+ 条 |
| 日均生成优化 PR | 0 | 15-20 个 |
| 慢查询治理周期 | 3 天 | 4 小时 |
| 数据库 CPU 负载 | 72% | 47%（↓25%） |

## 🧠 核心逻辑流

- **长链推理**：扫描→去重→EXPLAIN分析→多方案生成→沙箱回归验证→PR提交
- **多 Agent 协作**：Scanner Agent + Analyzer Agent + Sandbox Agent + PR Agent
- **闭环验证**：所有方案在 Docker 隔离沙箱回放生产流量后确认安全

## 🔧 技术栈

- OpenClaw v2026.3.31-beta.1
- Claude Sonnet 4 (Anthropic API)
- MySQL 8.0 / Docker 沙箱
- GitLab CI / GitHub Actions

## 📈 月度消耗

- 月均 Token：1.5 亿
- 月均费用：$1,572.50
- 日均请求：8,000+ 次

## 🖥️ 工作流演示

见 `/demo/terminal.html`（可下载查看完整终端运行日志）

---

*项目已稳定运行 90 天 | 支撑数据库 99.95% 的慢查询自动优化*
