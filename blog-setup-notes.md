# 博客搭建知识总结

本文档记录了使用 Jekyll + GitHub Pages 搭建个人博客的完整过程和关键知识点。

---

## 一、项目结构

最终的目录结构如下：

```
ruohai0925.github.io/
├── _config.yml                          # Jekyll 全局配置
├── _layouts/
│   └── post.html                        # 自定义文章布局（覆盖 minima 默认）
├── _posts/
│   └── 2026-02-17-the-second-half.md    # 博客文章（标准命名：YYYY-MM-DD-title.md）
├── index.md                             # 首页（自动列出所有文章）
├── README.md
└── blog-setup-notes.md                  # 本文档
```

### 关键规则

- `_posts/` 目录下的文件必须以 `YYYY-MM-DD-title.md` 格式命名，Jekyll 才能识别为博客文章
- `_layouts/` 用于覆盖主题的默认布局，优先级高于主题自带的同名文件
- `_config.yml` 是全局配置，修改后需要重新构建才能生效（GitHub Pages 会自动重新构建）

---

## 二、主题选择

### 从 `jekyll-theme-minimal` 到 `minima`

| 对比项 | jekyll-theme-minimal | minima |
|--------|---------------------|--------|
| 布局 | 左侧边栏 + 右侧内容 | 居中单栏，适合长文阅读 |
| 博客支持 | 弱，无文章列表功能 | 原生支持，首页自动列出文章 |
| 文章元信息 | 不自动显示日期/作者 | 自动显示日期、作者 |
| 扩展性 | 较差 | 支持 `_layouts/` 覆盖，可自定义 |

**结论**：如果是博客类网站，`minima` 是 GitHub Pages 上最合适的内置主题。

### `_config.yml` 配置详解

```yaml
theme: minima                              # 使用 minima 主题
title: Ruohai's Blog                       # 网站标题（显示在导航栏）
description: Thoughts on CFD and AI        # 网站描述（显示在页脚，也用于 SEO）
author:
  name: Ruohai                             # 全局作者名
url: "https://ruohai0925.github.io"        # 网站根 URL
show_excerpts: true                        # 首页文章列表显示摘要

giscus:                                    # 评论系统配置（见第五节）
  repo: ruohai0925/ruohai0925.github.io
  repo_id: R_kgDORSwM5A
  category: General
  category_id: DIC_kwDORSwM5M4C2rly
```

---

## 三、文章 Markdown 格式规范

### Front Matter（文章头部元数据）

每篇文章开头必须有 YAML front matter：

```yaml
---
layout: post                               # 使用 post 布局
title: "文章标题"                            # 文章标题
date: 2026-02-17                           # 发布日期
author: Ruohai                             # 作者（可选，会覆盖全局设置）
permalink: /The-Second-Half/               # 自定义 URL 路径（可选）
---
```

`permalink` 的作用：默认 URL 是 `/2026/02/17/the-second-half.html`，设置 `permalink: /The-Second-Half/` 后变为 `/The-Second-Half/`，更简洁美观。

### Markdown 格式化技巧（对比参考 Shunyu Yao 的博客风格）

#### 1. tldr 摘要 —— 使用 blockquote

```markdown
> **tldr:** 一句话总结文章核心观点。
```

效果：在文章开头以引用框形式突出核心结论，让读者快速了解主旨。

#### 2. 章节标题 —— 使用 `##`

```markdown
## The First Half
## The Second Half
## Summary
```

注意：`#` 是页面大标题（由 front matter 的 `title` 自动生成），文章内部章节用 `##` 起步。

#### 3. 引用参考文献 —— 使用行内超链接

**错误做法**（裸 URL + 编号引用）：
```markdown
CFD emerged in the 1930s [3].
...
[3] https://en.wikipedia.org/wiki/Computational_fluid_dynamics
```

**正确做法**（行内超链接）：
```markdown
CFD [emerged in the 1930s](https://en.wikipedia.org/wiki/Computational_fluid_dynamics).
```

行内链接更适合 Web 阅读，读者可以直接点击，不需要翻到文末查找。

#### 4. 强调重点 —— 粗体和斜体

```markdown
**粗体**用于突出关键论点或结论
*斜体*用于标注术语、概念、外来词
***粗斜体***用于最重要的金句
```

示例：
- `**Computational Fluid Dynamics (CFD)**` —— 首次出现的核心概念
- `*Domain Knowledge*` —— 术语标注
- `***"code is cheap, show me the value."***` —— 核心金句

#### 5. 重要引言 —— 使用 blockquote

```markdown
> There used to be a saying, *"talk is cheap, show me the code."*
> I think it will become, ***"code is cheap, show me the value."***
```

#### 6. 文末署名

```markdown
---

*February 17, 2026*
```

用 `---` 分隔线 + 斜体日期，作为文章结尾的落款。

---

## 四、首页配置

`index.md` 内容非常简单：

```markdown
---
layout: home
---
```

`minima` 主题的 `home` 布局会自动扫描 `_posts/` 目录，按日期倒序列出所有文章标题、日期和摘要。

---

## 五、Giscus 评论系统

### 为什么选 Giscus 而不是 Disqus

| 对比项 | Disqus | Giscus |
|--------|--------|--------|
| 费用 | 免费版有广告 | 完全免费，无广告 |
| 数据存储 | Disqus 服务器 | GitHub Discussions（你自己的仓库） |
| 登录方式 | Disqus/社交账号 | GitHub 账号 |
| 适合人群 | 通用博客 | 技术博客（读者大多有 GitHub 账号） |
| 点赞/Reactions | 有限支持 | 支持 GitHub 风格的 Reactions |

### 配置步骤

#### 第 1 步：开启 GitHub Discussions

仓库 Settings → Features → 勾选 **Discussions**

#### 第 2 步：安装 Giscus GitHub App

访问 https://github.com/apps/giscus → Install → 选择目标仓库

#### 第 3 步：获取配置参数

访问 https://giscus.app/zh-CN → 填入仓库名 → 选择 Discussion 分类 → 页面自动生成 `<script>` 代码，从中提取：
- `data-repo-id`
- `data-category-id`

#### 第 4 步：代码集成

**`_config.yml`** 中添加 giscus 配置块：

```yaml
giscus:
  repo: ruohai0925/ruohai0925.github.io
  repo_id: R_kgDORSwM5A
  category: General
  category_id: DIC_kwDORSwM5M4C2rly
```

**`_layouts/post.html`** 中覆盖 minima 的默认 post 布局，在文章末尾插入 giscus 脚本：

```html
{%- if site.giscus.repo -%}
<div class="post-comments" style="margin-top: 2rem;">
  <hr>
  <script src="https://giscus.app/client.js"
      data-repo="{{ site.giscus.repo }}"
      data-repo-id="{{ site.giscus.repo_id }}"
      data-category="{{ site.giscus.category }}"
      data-category-id="{{ site.giscus.category_id }}"
      data-mapping="pathname"
      data-reactions-enabled="1"
      data-input-position="top"
      data-theme="light"
      data-lang="en"
      crossorigin="anonymous"
      async>
  </script>
</div>
{%- endif -%}
```

关键参数说明：
- `data-mapping="pathname"`：按页面路径匹配 Discussion，每篇文章自动对应一个讨论帖
- `data-reactions-enabled="1"`：开启点赞/Reactions 功能
- `data-input-position="top"`：评论输入框在上方
- `data-lang="en"`：界面语言为英文

---

## 六、部署到 GitHub Pages

### 仓库命名规则

仓库名为 `<username>.github.io` 格式（如 `ruohai0925.github.io`），GitHub 自动识别为 User Pages 站点，无需额外配置。

### 部署分支

GitHub Pages 默认从 `main` 分支部署。如果代码在 `development` 分支，有两种方式：

**方式一：合并到 main（推荐）**

```bash
git checkout main
git merge development
git push origin main
```

**方式二：修改部署源分支**

仓库 Settings → Pages → Build and deployment → Branch → 改为 `development`

### 部署后的访问地址

- 首页：`https://ruohai0925.github.io/`
- 文章：`https://ruohai0925.github.io/The-Second-Half/`（由 permalink 决定）

部署通常需要 1-2 分钟生效。

---

## 七、Git 工作流总结

本次搭建过程中的提交历史：

```
14269a6 Initial commit
50c74fb Add configuration for Jekyll theme and blog details
99c0d35 Add article on AI's impact on CFD education and industry
b24acae Revamp blog: switch to minima theme, reformat article with proper markdown
02019b6 Fix interview duration from three hours to two and a half hours
cce863c Rename author from ZDSJTU to Ruohai
a570278 Minor wording fixes: remove 'then', replace 'thorny' with 'difficult'
f1f0743 Add giscus comment system to blog posts
950ecf7 Add giscus repo_id and category_id for comment system
c28a612 Change giscus comment language from zh-CN to en
```

### Commit Message 规范

- 首行简洁描述改动（祈使句，如 "Add", "Fix", "Update"）
- 必要时用空行分隔，补充详细说明
- 多人协作时添加 `Co-Authored-By` 标注

---

*最后更新：2026-02-18*
