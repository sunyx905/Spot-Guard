# Spot Guard

Binance Agent OS Mini Hackathon · Track A

一个基于 Binance Agent OS / MCP 的现货安全副驾驶。
Agent 只负责观察和建议，不自动下单。

## 它解决什么问题

很多交易 Agent 一接上就会催你下单。
Spot Guard 把流程拆成 4 步，把最终开关留在用户手里：

1. 观察：用官方 MCP 读取 BTC / ETH / BNB 现货行情
2. 检查：读取 Agentic 子账户余额
3. 建议：输出 WAIT / BUY_SMALL / BLOCK，并给出理由
4. 确认：只有用户明确说「确认」后，才允许提交小额现货单

## 风控规则

- 只做现货，禁止合约、杠杆、提现
- 单笔建议不超过 20 USDT
- 行情或余额数据不完整时，必须 BLOCK
- 禁止全仓、禁止连续加仓
- 下单前必须复述：交易对、方向、金额、下单类型

## 怎么运行

1. 在兼容客户端接入官方 MCP：
   https://agent.binance.com/mcp/agentic
2. 把 `skills/spot-guard/SKILL.md` 交给 Agent
3. 对 Agent 说：「按 Spot Guard 规则，给我一份现货简报」

支持 Claude / ChatGPT / VS Code / Grok 等已接入 Binance MCP 的客户端。

## Demo 流程

见 `DEMO.md`
