# 高校教授个人主页（示例）

这个项目是一个个人主页示例，适合用于展示高校教授/实验室带头人的信息，页面简洁、易改、可扩展。当前已升级为“配置文件 + Markdown 内容驱动版”。

## 当前功能

- 个人简介（姓名、职称、研究方向）
- 个人信息（单位、邮箱、课程、招生方向）
- 实验室介绍
- 代表性成果（时间线）
- 论文列表（示例）
- 专著列表（示例）
- 项目与经费（示例）
- 招生信息
- 联系方式与常用链接

## 如何使用（配置 + Markdown 版）

1. 打开 `site.config.json`，修改基础信息（标题、头像、个人信息、链接、页脚等）。
2. 打开 `site.content.md`，修改正文内容（简介、成果、论文、项目、招生等）。
3. 运行一个本地静态服务后访问页面（例如 `python -m http.server`），让浏览器能读取文件。
4. 打开 `index.html` 预览效果。

## 建议修改的位置（只改数据）

- 基础配置：`site.config.json`
  - 页面标题：`pageTitle`
  - 顶部姓名和头像：`hero.nameAndTitle`、`hero.avatarUrl`
  - 个人信息：`profile.left`、`profile.right`
  - 联系链接：`links`
- 页面正文：`site.content.md`
  - `## 个人简介`
  - `## 实验室介绍` / `## 实验室要点`
  - `## 代表性成果`（格式建议：`- 2026：内容`）
  - `## 论文` / `## 专著` / `## 项目与经费`
  - `## 招生简介` / `## 招生要点`

## 配置文件示例（site.config.json）

```json
{
  "pageTitle": "王明教授 | 个人主页",
  "hero": {
    "nameAndTitle": "王明 教授 / 博士生导师",
    "avatarUrl": "https://via.placeholder.com/240x240.png?text=Professor",
    "avatarAlt": "王明教授头像",
    "tags": ["国家杰青", "IEEE Senior Member"]
  }
}
```

## Markdown 内容示例（site.content.md）

```md
## 个人简介
这里写简介正文。

## 论文
- 论文1
- 论文2
```

## 后续扩展建议

- 新增“团队成员”模块：按老师/博士后/博士生分类。
- 新增“新闻动态”模块：按时间倒序发布讲座、获奖和论文接收信息。
- 新增“下载中心”：提供简历、招生通知、课题介绍 PDF。
- 增加多套配置：如 `site.config.zh.json` / `site.config.en.json`。
- 新增多语言：将 `siteData` 按语言拆分为 `zh`、`en` 两套内容。
- 增加排序：给论文和项目增加年份字段，自动按年份倒序显示。

## 说明

当前内容中的姓名、成果、论文、专著均为演示示例，可自由替换。  
本版本中页面内容由 `site.config.json` 与 `site.content.md` 自动渲染，后续扩展建议优先补充数据内容，再扩展渲染逻辑。
