# 查课啦官网 · GitHub Pages 源码说明

这是从现有查课啦 / Schedia 双语官网整理出的**查课啦中文版独立源码**，可用于更新你现有的 GitHub Pages 网站。首页、隐私政策、数据删除指引、使用条款和技术支持页均已包含。页面、图片和脚本使用相对路径；无论现有 Pages 网址位于域名根目录还是 `/<仓库名>/` 下，都能正常打开。Schedia 英文版、服务器配置、SSL 证书和登录凭据不在本目录中。

## 源码目录

| 文件或文件夹 | 用途 |
| --- | --- |
| `index.html` | 中文首页：产品功能、实机截图、交互演示、合作与联系方式 |
| `privacy/index.html` | 隐私政策 |
| `privacy-choices/index.html` | 隐私选择与数据删除指引 |
| `terms/index.html` | 使用条款 |
| `support/index.html` | 技术支持与联系渠道 |
| `style.css` | 响应式布局、主题和动效 |
| `app.js` | 首页演示、设备截图切换、导航、弹窗和打印交互 |
| `config.js` | 查课啦 App Store 下载地址 |
| `assets/` | 查课啦图标与 iPhone、iPad、Apple Watch 截图 |
| `.nojekyll` | 让 GitHub Pages 直接发布静态文件 |

这是**可直接发布的 HTML/CSS/JavaScript 源码**，不需要 npm、构建命令或数据库。需要修改政策时，直接编辑对应目录的 `index.html`；如果政策日期或功能描述变化，也检查其他政策页和首页是否需要同步。

## 更新你现有的 GitHub 网站

1. 先查看仓库的 **Settings → Pages**，确认当前发布来源：分支和 `/(root)`、`/docs`，或者 GitHub Actions。把本目录内容放到**实际发布目录**；如果 Pages 使用 `main` 的 `/docs`，就放到 `/docs` 里面。不要把 ZIP 当成一个文件上传，也不要多嵌套一层 `Chakela-GitHub-Pages/`。
2. 上传时覆盖同名的 `index.html`、`style.css`、`app.js`、`config.js`、`assets/` 和四个政策/支持目录。保留你仓库已有的 `CNAME`、GitHub Actions 工作流及其他与你的域名或发布方式有关的文件；本包没有这些文件。
3. 提交后等待 Pages 发布完成，再在**未登录 GitHub 的浏览器窗口**检查首页和下面四个页面。若使用自定义域名，以 **Settings → Pages** 显示的实际发布网址为准，不要猜测 URL。

GitHub 官方说明：[配置 Pages 发布来源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)、[保留自定义域名的 CNAME](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages)。

当前网站使用公开仓库 `McWhirl-V/chakela` 的 `main` 分支根目录发布，当前没有配置自定义域名。以下是已部署页面地址；若将来修改仓库名或域名，应同步更新 App Store Connect 中的链接。

| App Store Connect 字段 | 对应网页 |
| --- | --- |
| Privacy Policy URL | `https://mcwhirl-v.github.io/chakela/privacy/` |
| User Privacy Choices URL | `https://mcwhirl-v.github.io/chakela/privacy-choices/` |
| Support URL | `https://mcwhirl-v.github.io/chakela/support/` |
| Marketing URL | `https://mcwhirl-v.github.io/chakela/` |

如你的仓库名是 `<你的GitHub用户名>.github.io`，网址中不应包含 `/chakela`。Apple 的字段说明：[App Privacy](https://developer.apple.com/help/app-store-connect/reference/app-privacy/)、[Platform Version Information](https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information/)。

## 修改与预览

- 下载按钮在 `config.js` 中配置，当前指向已验证可访问的查课啦中国区 App Store 页面。商店地址变更时只需修改 `zh.appStoreUrl`。
- 邮箱为 `mcwhirl@qq.com`；若更换邮箱，在五个 HTML 文件中搜索并逐一修改正文、合作入口和页脚。
- 修改外观请编辑 `style.css`；交互在 `app.js`。页面不依赖外部字体、分析脚本或构建工具。
- 本地预览：在本目录运行 `python -m http.server 8765`，再打开 `http://127.0.0.1:8765/`。请使用本地服务器预览，不要直接双击 HTML 文件。

页脚保留了**“查课啦 App ICP 备案：皖ICP备2026033163号-1A”**及工信部查询入口。这是 App 备案号，不能当作 GitHub Pages 网站的 ICP 或公安备案号。本独立版移除了原 `mc985.com` 网站“备案办理中”状态；若以后把这份源码发布到已获批备案的域名，应依据实际获批的网站备案与公安备案信息再更新页脚。

隐私政策内容来自现有查课啦资料。每次发布 App 新版本或更改数据处理方式后，应核对网页中教务导入、iCloud、诊断报告、权限和删除步骤是否仍与实际 App 一致。
