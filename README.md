# 双身份狼人杀发牌工具

一个面向线下聚会的双身份狼人杀发牌辅助页面。它根据人数生成候选身份组合，并自动校验狼人数量、双狼身份、预言家冲突和金宝宝等约束。

在线体验：<https://zydwz2001.github.io/two-identities-werewolf/>

## 使用方式

项目没有后端和依赖，直接打开 `index.html` 即可。也可以启动本地静态服务器：

```bash
git clone https://github.com/zydwz2001/two-identities-werewolf.git
cd two-identities-werewolf
python3 -m http.server 8000
```

访问 <http://localhost:8000>，然后：

1. 选择 5–8 人。
2. 查看该人数对应的牌库。
3. 点击生成方案。
4. 在候选方案之间切换，选定后按玩家编号发牌。

页面只在当前浏览器中随机生成结果，不会上传玩家姓名、身份或对局数据。

## 规则实现

- `roles` 定义身份名称、图标和说明。
- `configs` 定义各人数的牌库数量。
- `createDeck()` 和 `shuffle()` 创建并打乱牌库。
- `isValidDeal()` 校验狼人玩家数、金宝宝和冲突规则。
- `dealCards()` 在尝试次数上限内生成并去重候选方案。

所有代码都在 `index.html` 中，调整规则后刷新页面即可验证。

## 发布到 GitHub Pages

仓库包含 Pages 工作流。推送到 `main` 后，在 **Settings → Pages** 中确认 Source 为 **GitHub Actions**；工作流会发布静态页面。

## 注意

这是线下桌游辅助工具，不负责夜间流程、投票、胜负判定或联网同步。生成结果使用浏览器的 `Math.random()`，不适用于需要密码学安全随机数的场景。
