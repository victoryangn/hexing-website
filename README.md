# HeXing Protection Technology - Corporate Website

深圳市和兴防护科技有限公司企业官网

## 技术栈
- **Hugo** v0.160.1 Extended — 静态站点生成器
- **DecapCMS** — 后台内容管理系统（无头CMS）
- **GitHub Pages** — 免费托管 + 自动部署

## 本地开发

```bash
# 安装 Hugo Extended (如未安装)
# 下载: https://github.com/gohugoio/hugo/releases

# 启动本地服务器
hugo server -D

# 构建
hugo --minify
```

## 目录结构
```
├── config.toml          # Hugo 配置
├── content/
│   ├── zh/              # 中文内容
│   └── en/              # 英文内容
├── themes/hexing/
│   ├── layouts/         # 页面模板
│   └── assets/css/      # 样式表
├── static/
│   ├── admin/           # DecapCMS 后台
│   └── images/          # 图片资源
└── .github/workflows/   # GitHub Actions 自动部署
```

## 更新产品

### 方式1：通过 DecapCMS 后台
访问 `https://hexingtac.com/admin/` 进行可视化编辑

### 方式2：直接编辑 Markdown
1. 在 `content/zh/products/` 或 `content/en/products/` 添加 `.md` 文件
2. Git commit + push
3. GitHub Actions 自动构建部署

### 方式3：AI助手 (Wmac)
告诉 AI 助手要添加/修改的产品信息，AI 会直接编辑文件并推送

## 域名
hexingtac.com
