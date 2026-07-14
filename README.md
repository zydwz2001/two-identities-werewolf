# 双身份狼人杀发牌工具

一个面向线下朋友聚会的双身份狼人杀发牌和规则辅助网站。

## Product Background

双身份狼人杀不是常见小程序或 App 支持的主流玩法。我们是在综艺节目里看到这个玩法后，在线下朋友聚会中复刻并完善规则。

实际玩的时候遇到两个问题：

- 每局都需要一名玩家担任法官，影响参与感。
- 双身份发牌有规则限制，比如特殊身份不能冲突、狼人玩家数需要控制、至少保留双平民组合，手工发牌经常要反复重发。

这个工具先解决最影响开局效率的环节：根据人数自动生成满足约束的发牌方案。

## Features

- 支持 5-8 人局。
- 自动展示对应人数的牌库配置。
- 一次生成多套可选发牌方案。
- 标记狼人阵营、好人阵营、金宝宝和双狼情况。
- 内置角色说明和核心规则。
- 生成失败时有兜底提示，避免空结果。

## Rule Model

当前约束包括：

- 每位玩家获得两张身份牌。
- 只要有一张狼人牌，即属于狼人阵营。
- 狼人和预言家不能在同一名玩家手中。
- 每局至少有一个双平民玩家，也就是“金宝宝”。
- 不同人数使用不同牌库配置，并控制狼人玩家数量区间。

## Tech Architecture

```text
index.html
  HTML structure
  CSS styles
  role configuration
  deck generation
  validity checks
  result rendering
```

The project is a single-file static website. It does not require a backend or external dependencies.

## Run Locally

Open `index.html` directly in a browser.

If you prefer using a local static server:

```bash
python3 -m http.server 8080
```

Then visit:

```text
http://localhost:8080
```
