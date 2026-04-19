# Hexing Website — 和兴防护科技官网

> **深圳市和兴防护科技有限公司** 企业官网
> 🌐 [hexingtac.com](https://hexingtac.com) | 🏭 军品出口代理、防弹装备、战术服装

---

## 📋 项目概览

Hugo 静态网站，双语言（中文/英文），部署在 GitHub Pages，面向国际军警采购客户展示公司产品。

- **公司**: 深圳市和兴防护科技有限公司 (Shenzhen HeXing Protection Tech. Co., Ltd.)
- **域名**: hexingtac.com（HTTPS 强制）
- **中文站**: `/`（根路径）| **英文站**: `/en/`
- **产品数量**: 109 个（中英文各 109 个 Markdown 文件）
- **产品图片**: 368 张（JPG/PNG）

---

## 🛠 技术栈

| 组件 | 版本/说明 |
|------|----------|
| **Hugo** | v0.160.1 Extended（必须用 Extended 版） |
| **主题** | 自定义主题 `themes/hexing/`（非子模块） |
| **CMS** | DecapCMS（`/admin/` 后台可视化编辑） |
| **部署** | GitHub Actions → GitHub Pages |
| **CSS** | 单文件 `themes/hexing/assets/css/main.css` |

---

## 📁 目录结构

```
hexing-website/
├── hugo.toml                    # Hugo 主配置（菜单、多语言、参数）
├── content/
│   ├── zh/                      # 中文内容
│   │   ├── _index.md            # 首页
│   │   ├── about/               # 关于我们
│   │   ├── contact/             # 联系我们
│   │   └── products/            # 产品中心（109个.md文件）
│   │       ├── vests/           # 防弹衣（37个）
│   │       ├── helmets/         # 防弹头盔（15个）
│   │       ├── shields/         # 防弹盾牌（9个）
│   │       ├── plates/          # 防弹插板（7个）
│   │       ├── uniforms/        # 军警制服（10个）
│   │       ├── tactical-clothing/  # 战术服装（8个）
│   │       ├── tactical-jackets/   # 冲锋衣（6个）
│   │       ├── hunting-clothing/   # 狩猎服装（5个）
│   │       ├── down-jackets/    # 羽绒服（2个）
│   │       ├── cotton-jackets/  # 棉服（3个）
│   │       └── clothing-footwear/ # 服装鞋靴（3个）
│   └── en/                      # 英文内容（镜像结构）
│       └── products/            # English products (109 .md files)
├── themes/hexing/
│   ├── layouts/
│   │   ├── index.html           # 首页模板（分类卡片+特色产品）
│   │   ├── _default/
│   │   │   ├── baseof.html      # 基础骨架
│   │   │   ├── list.html        # 产品列表页
│   │   │   └── single.html      # 产品详情页
│   │   ├── about/list.html
│   │   ├── contact/list.html
│   │   └── partials/
│   │       ├── header.html      # 导航栏（含下拉菜单）
│   │       ├── footer.html      # 页脚
│   │       └── product-card.html # 产品卡片组件
│   └── assets/css/
│       └── main.css             # 全局样式（单文件）
├── static/
│   ├── CNAME                    # 自定义域名 hexingtac.com
│   ├── admin/                   # DecapCMS 后台
│   │   ├── index.html
│   │   └── config.yml
│   └── images/
│       ├── logo.jpg             # 公司Logo
│       └── products/            # 产品图片
│           ├── ccgk/            # 中国CCGK源产品图片
│           └── fronter/         # Fronter源产品图片
├── i18n/                        # 国际化翻译文件
├── data/                        # Hugo数据文件
└── .github/workflows/
    └── hugo-deploy.yml          # CI/CD 自动部署
```

---

## 🚀 本地开发

```bash
# 安装 Hugo Extended v0.160.1+
# Linux: snap install hugo --channel=extended
# macOS: brew install hugo

# 启动开发服务器（热重载）
hugo server -D

# 构建生产版本
hugo --minify
```

开发服务器默认运行在 `http://localhost:1313`

---

## 📦 产品内容格式

每个产品是一个 Markdown 文件，frontmatter 格式：

```yaml
---
title: 产品名称
description: SEO描述
date: 2026-04-18
draft: false
category: 分类名称（如：防弹衣/防刺服）
images:
  - /images/products/ccgk/产品图1.jpg
  - /images/products/ccgk/产品图2.jpg
specs: "  参数名1： 值1\n  参数名2： 值2\n"
---

## 产品描述

产品介绍内容...

## 产品规格

参数名1： 值1
参数名2： 值2
```

### 产品分类 slug 对照表

| 中文分类 | URL Slug | 产品数 |
|---------|----------|--------|
| 防弹衣 | `vests` | 37 |
| 防弹头盔 | `helmets` | 15 |
| 军警制服 | `uniforms` | 10 |
| 防弹盾牌 | `shields` | 9 |
| 战术服装 | `tactical-clothing` | 8 |
| 防弹插板 | `plates` | 7 |
| 冲锋衣 | `tactical-jackets` | 6 |
| 狩猎服装 | `hunting-clothing` | 5 |
| 棉服 | `cotton-jackets` | 3 |
| 服装鞋靴 | `clothing-footwear` | 3 |
| 羽绒服 | `down-jackets` | 2 |

### 添加新产品

1. 在 `content/zh/products/<slug>/` 创建 `.md` 文件
2. 在 `content/en/products/<slug>/` 创建对应英文版
3. 图片放到 `static/images/products/` 下对应目录
4. `git add -A && git commit -m "feat: add product xxx" && git push`

---

## 🎨 品牌设计规范

```
主色（深绿）:   #1B5E20    — 导航、按钮、标题
强调色（金色）:  #D4A843    — CTAs、高亮
橄榄绿:        #558B2F    — 次要元素
背景白:        #FFFFFF    — 卡片背景
文字黑:        #1A1A1A    — 正文
```

Logo: 盾牌/徽章形状，深绿色+浅橄榄绿，白色字母"H"和"X"，黑色边框。

---

## 🔄 部署流程

```
git push origin main
    → GitHub Actions (.github/workflows/hugo-deploy.yml)
    → Hugo build --minify
    → GitHub Pages deploy
    → hexingtac.com 更新（通常1-2分钟）
```

**关键配置**：
- `hugo.toml` 的 `baseURL = "https://hexingtac.com/"`
- `static/CNAME` 文件内容为 `hexingtac.com`
- ⚠️ **不要**在 Actions 里加 `--baseURL` 参数，否则会覆盖自定义域名

---

## ⚠️ 已知陷阱 & 注意事项

### 1. GitHub Pages + 自定义域名
`hugo-deploy.yml` 中 `configure-pages` action 输出的 `base_url` 是 `victoryangn.github.io/hexing-website`，**不要用它**作为 Hugo 的 `--baseURL`，否则所有链接会带 `/hexing-website/` 前缀。让 Hugo 用 `hugo.toml` 中的 `baseURL` 即可。

### 2. 产品卡片白底
产品图片如果背景浅色+`object-fit: cover`，会看不清。确保 `.product-card` 和 `.product-card img` 的背景色设为 `#fff`，并用 `object-fit: contain` 让图片完整显示。

### 3. Hugo Extended 必须
本站使用了 SCSS/asset pipeline 功能，**必须**用 Hugo Extended 版本，普通版会报错。

### 4. 双语言内容同步
中英文产品必须**一一对应**。添加产品时记得同时创建 `content/zh/` 和 `content/en/` 下的文件。

### 5. 图片路径
frontmatter 中的 `images` 路径以 `/images/` 开头（绝对路径），对应 `static/images/` 目录。

---

## 🏢 公司信息

- **公司全称**: 深圳市和兴防护科技有限公司
- **英文**: Shenzhen HeXing Protection Tech. Co., Ltd.
- **地址**: 深圳市光明区凤凰街道甲子塘社区同仁路52号 三环科技大厦A栋820
- **英文地址**: R. 820, Building A, Sanhuan Technology Building, No. 52, Tongren Road, Jiazitang Community, Fenghuang Sub-district, Guangming District, Shenzhen City, Guangdong Province, China. Post Code: 518107
- **联系人**: Victor Yang（杨总）+86 13402060841
- **主营**: 军品出口代理、防弹装备（衣/盔/板/盾）、军警制服、战术服装、冲锋衣、帐篷背包
- **核心市场**: 菲律宾、马来西亚、索马里、加纳等

---

## 📝 常用命令速查

```bash
# 本地开发
hugo server -D

# 构建+部署（一键）
hugo --minify && git add -A && git commit -m "update" && git push

# 检查构建错误
hugo --minify 2>&1

# 新建产品（手动）
# 1. 创建 content/zh/products/<slug>/xxx.md
# 2. 创建 content/en/products/<slug>/xxx.md
# 3. 放图片到 static/images/products/<source>/
```

---

## 🤖 AI Agent 协作指南

本仓库由 **Wmac**（Hermes Agent）维护，也支持其他 AI 编程工具（Claude Code、Codex 等）协作。

### 给 Agent 的建议

1. **修改模板** → 改 `themes/hexing/layouts/` 下的 `.html` 文件
2. **修改样式** → 改 `themes/hexing/assets/css/main.css`（单文件CSS）
3. **修改配置** → 改 `hugo.toml`（菜单、语言、参数）
4. **添加产品** → 在 `content/{zh,en}/products/<slug>/` 添加 `.md`
5. **产品数据源** → 中国CCGK (chinaccgk.cn) 是主要产品数据来源
6. **部署** → push 到 main 分支即可，GitHub Actions 自动构建部署
7. **验证** → 本地 `hugo server -D` 预览，或 push 后访问 hexingtac.com
