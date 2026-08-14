# 汇率换算计算器

一个面向手机、iPad 和桌面端的纯前端计算器 + 汇率换算工具，可直接部署到 GitHub Pages。

**当前版本：v1.1.0**

## 主要功能

- 基础四则运算、百分比、括号与正负号
- 最近计算历史，本机保存
- 个性化姓名与多套主题
- 多币种汇率换算
- 常用币种与中亚货币
- USD / EUR 兑人民币历史走势
- 响应式移动端与 iPad 布局
- PWA，可安装到手机/电脑桌面
- 应用外壳离线缓存
- GitHub Actions 自动部署 GitHub Pages

## PWA 与离线说明

首次联网访问后，应用主页面、图标和配置文件会被缓存，因此之后即使暂时离线，也可以打开计算器主体。

汇率实时数据和走势图依赖第三方网络接口。离线时无法获取新的市场数据，但程序原有的 `localStorage` 汇率缓存仍可继续用于最近一次已保存的数据。

## GitHub Pages 自动部署

项目已包含：

```text
.github/workflows/deploy-pages.yml
```

推荐部署方法：

1. 新建 GitHub 仓库。
2. 将本项目全部文件上传到仓库根目录。
3. 打开仓库 **Settings → Pages**。
4. 在 **Build and deployment → Source** 选择 **GitHub Actions**。
5. 推送到 `main` 分支后，会自动部署。

## 命令行上传

```bash
git init
git add .
git commit -m "Initial release v1.1.0"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
git push -u origin main
```

## 项目结构

```text
.
├── .github/
│   └── workflows/
│       └── deploy-pages.yml
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
├── .gitignore
├── .nojekyll
├── index.html
├── manifest.webmanifest
├── sw.js
├── LICENSE
└── README.md
```

## 数据来源与免责声明

程序会尝试从公开汇率服务获取参考数据，并将最近获取的数据保存到浏览器本机。

页面中的银行现汇/现钞买入卖出参考价包含基于市场中间价的估算点差，仅适合预算和快速估算；实际成交价格请以银行 App、网银或柜台为准。

## 本地运行

可以直接打开 `index.html`，但 PWA Service Worker 通常要求通过 HTTP/HTTPS 运行。

推荐：

```bash
python -m http.server 8080
```

然后访问：

```text
http://localhost:8080
```

## License

MIT
