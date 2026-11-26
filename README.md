# 每日早报 · 游戏与 AI

**网址：https://mizepeng.github.io/daily-digest/**

每天早上 8 点（新加坡时间）更新的资讯早报，分「游戏」和「AI」两个板块，各 12 到 20 条，按「重要 / 值得关注 / 简讯」分层。游戏以 PC 为主，AI 覆盖主要实验室、产品发布、开源模型、研究和行业动态。每条附原始来源链接，往期可以按日期切换查看。

纯静态站点，零构建，用 GitHub Pages 从 main 分支根目录发布。

## 文件

- `index.html`：页面本身，读取 `data/` 里的 JSON 渲染，平时不用改。
- `data/index.json`：所有期的日期列表，`{"dates": ["2026-11-27", "2026-11-26"]}`，顺序不限，页面会按新到旧排。
- `data/YYYY-MM-DD.json`：每一期内容。
- `.nojekyll`：让 GitHub Pages 原样发布文件。

## 每期 JSON 格式

```json
{
  "date": "2026-11-27",
  "updated": "2026-11-27T00:00:00Z",
  "games": { "important": [条目], "notable": [条目], "brief": [条目] },
  "ai":    { "important": [条目], "notable": [条目], "brief": [条目] }
}
```

条目：

```json
{
  "title": "一句话标题",
  "summary": "一两句说明",
  "url": "https://原始来源或实际读过的页面",
  "source": "来源名称，转述时写「某某（转述 某某）」",
  "date": "11-27",
  "tag": "你在玩"
}
```

`tag` 可省略，只给 Dota 2、巫师3重制版、狂热运输3 的条目加。`url` 必须以 https:// 开头，否则标题不带链接。每个板块合计 12 到 20 条。

## 每日更新

1. 写好 `data/YYYY-MM-DD.json`（日期用新加坡时间当天）。
2. 把这个日期加进 `data/index.json` 的 `dates`。
3. 提交并推送到 main：

```
git add data/
git commit -m "Add digest for YYYY-MM-DD"
git push origin main
```

GitHub Pages 通常在一两分钟内更新。网址不带 `#` 时显示最新一期，`#2026-11-26` 打开指定一期。
