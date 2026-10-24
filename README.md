# 多平台发布插件（MultiPost）

> 篝火出品 · 收录于篝火 App 应用区 · 基于开源项目 [leaperone/MultiPost-Extension](https://github.com/leaperone/MultiPost-Extension)（Apache-2.0）

写一次内容，在浏览器里一键同步发布到多个内容平台：文字动态、图文文章、视频、播客都可以。上游说明：使用 MultiPost 本身无需注册、无需登录、无需 API Key，免费。

## 下载

到 [Releases](https://github.com/campfire-code/multipost-extension/releases/latest) 下载 `multipost-extension_版本号_multipost-extension-community-1.5.0.zip`（约 2.3 MB），附 `SHA256SUMS.txt` 可核对。

- 这是上游发布的**社区版**（Apache-2.0 开源部分），篝火没有修改。
- 上游同一个发布里还有一个「专业版」`chrome-mv3-prod.zip`，内含上游**未开源的 Agent 模块**，不是 Apache-2.0，所以这里**不转发布**。上游的 Chrome / Edge 商店版本就是专业版。

## 安装（Chrome / Edge，开发者模式加载）

1. 下载 zip 并**解压到一个固定的文件夹**（装好后不要删除或移动这个文件夹，否则插件会失效）。解压后能直接看到 `manifest.json`。
2. Chrome 地址栏打开 `chrome://extensions`；Edge 打开 `edge://extensions`。
3. 打开右上角（Edge 在左下角）的「开发者模式」开关。
4. 点「加载已解压的扩展程序」，选择刚才解压的文件夹。
5. 点浏览器工具栏的拼图图标，把 MultiPost 固定出来，点击即可使用。

其他基于 Chromium 的浏览器（360、QQ 浏览器等）上游没有说明是否可用，未验证。

## 支持的平台

以下按上游源码里登记的平台整理，平台改版后个别可能失效，以实际试用为准。

- **动态（31 个）**：哔哩哔哩、抖音、X、小红书、微博、雪球、知乎、Instagram、脸书、领英、即刻、Reddit、Pinterest、快手、搜狐视频、百家号、今日头条、Threads、微信视频号、BlueSky、V2EX、豆瓣、得到、微信公众号、知识星球、小黑盒、今日头条号、Substack、脉脉、掘金，以及 Webhook。
- **文章（41 个）**：CSDN、知乎、掘金、简书、思否、阿里云、腾讯云、火山引擎、百家号、今日头条、企鹅号、豆瓣、微信公众号、WordPress、哔哩哔哩、少数派、51CTO、雪球、微博、东方财富、Substack、Medium、开源中国、InfoQ、什么值得买、人人都是产品经理、格隆汇、健康界、凯迪网、汽车之家、美篇、同花顺、懂车号、知识星球、网易号、搜狐号、大鱼号、顶端号、快传号、一点号、X。
- **视频（30 个）**：哔哩哔哩、抖音、YouTube、小红书、TikTok、微信视频号、快手、百家号、微博、即刻、BlueSky、知乎、东方财富、小黑盒、今日头条号、企鹅号、车家号、得物、易车、搜狐号、搜狐视频、网易号、大鱼号、支付宝、一点号、拼多多、vivo 视频、爱奇艺、优酷、腾讯视频。
- **播客（7 个）**：QQ 音乐、荔枝、喜马拉雅、小宇宙、蜻蜓 FM、网易云音乐播客、Spotify。

## 使用须知

- 插件的做法是在浏览器里打开各平台的发布页并自动填写内容，所以**目标平台本身需要你先在同一个浏览器里登录**（这是对其工作方式的说明，具体表现以实际试用为准）。
- 会向各平台批量发布内容，**请遵守各平台的发布规则**，避免高频、重复发布导致账号被限制。
- 插件申请了较宽的权限（读取所有网站、标签页、剪贴板读写等，见 `manifest.json`），请只安装来自篝火发布页的包，并核对 SHA256。
- 界面语言默认中文。

## 验收用例

| 操作 | 应得到 |
|---|---|
| 按上面步骤在 Chrome 加载解压后的文件夹 | 扩展页出现 MultiPost 1.5.0，无报错 |
| 在浏览器里登录一个平台（如知乎），用插件发一条动态并选择该平台 | 自动打开该平台发布页并填入内容 |

## 和上游的区别

- 仅新增中文说明与篝火发布流程（`tool.json`、`.github/workflows/release.yml`），软件代码与上游一致。
- 上游仓库本身不含发布流水线，这里转发布的 zip 取自上游的 `extension-v1.5.0` 发布，只转发社区版。

## 归属与许可证

本仓库由**篝火**整理发布，是篝火 App 应用区收录的开源工具之一。软件全部功能与版权归 [leaperone/MultiPost-Extension](https://github.com/leaperone/MultiPost-Extension) 原作者所有，按 Apache-2.0 许可证再分发（完整协议见 `LICENSE`）。全部工具目录见 [toolkit-hub](https://github.com/campfire-code/toolkit-hub)。

---

以下为上游原始说明：

<div align="center">
<img src="https://github.com/user-attachments/assets/b30c6c81-9c8b-4c78-a2df-9266b84b6f14" width="200" height="200" alt="MultiPost Logo" />

# MultiPost

![GitHub License GitHub许可证](https://img.shields.io/github/license/leaper-one/MultiPost-Extension) ![GitHub Repo stars GitHub星星](https://img.shields.io/github/stars/leaper-one/MultiPost-Extension) ![GitHub commit activity GitHub提交活动](https://img.shields.io/github/commit-activity/m/leaper-one/MultiPost-Extension) [![Website 网站](https://img.shields.io/website?url=https%3A%2F%2Fmultipost.app)](https://multipost.app) [![Ask DeepWiki](https://deepwiki.com/badge.svg)](https://deepwiki.com/leaperone/MultiPost-Extension)

[English](README.md) | [中文](docs/README-zh.md) | [日本語](docs/README-jp.md) | [Français](docs/README-fr.md) | [한국어](docs/README-kr.md)

> A browser extension that helps users publish content to multiple social media platforms with one click.
> 一个用于在多个社交平台上发布内容的浏览器扩展。

⭐ If you find this project helpful, please consider giving it a star! Your support helps us grow and improve! ⭐
</div>

## Open-source snapshot / 开源部分

This repository contains the Apache-2.0 open-source components of the MultiPost extension. The MultiPost monorepo builds and publishes the official Chrome and Edge packages, which also include the proprietary Agent module. This repository maintains source code only and does not run release workflows.

本仓库维护 MultiPost 扩展的 Apache-2.0 开源部分。Chrome 和 Edge 商店中的 MultiPost 扩展由主仓库构建和发布，包含未在本仓库公开的 Agent 模块。本仓库只维护源码，不运行发布流水线。

## 主要功能 / Key Features
- 一键发布内容（文本、图片、视频等）到多个平台。（支持知乎、微博、小红书、抖音等10多个主流平台）无需登录、无需注册、无需API Key。完全免费！
  Post your content (text, images, videos, etc.) to multiple platforms with one click. (Over 10 mainstream platforms including TikTok, YouTube Zhihu, Weibo, Xiaohongshu, TikTok, etc.) No login, no registration, no API Key required. Free!
- 两种API接口 / 2 types of API Interface:
  - 扩展API：在您自己的Web应用中调用扩展的API发布内容。
    Extension API: Calling the extension's API to publish content in your own web app.
  - RESTful API：在脚本或服务器中调用RESTful API发布内容。
    RESTful API: Calling the RESTful API to publish content in your script or server.

该扩展解决了内容创作者在多平台发布时的痛点。通过一次编辑，内容可以同步到所有平台，大大提高工作效率。
This extension solves the pain points of content creators when publishing across multiple platforms. Through a single edit, content can be synchronized to all platforms, greatly improving work efficiency.

## How to start
- [multipost.app](https://multipost.app) - Official website
- [Documentation | 文档](https://docs.multipost.app)
- [Developer Documentation | 开发者文档](https://multipost.app/docs/development)
- [MultiPost Article Editor](https://md.multipost.app/) - [(Repo)](https://github.com/leaperone/multipost-wechat-markdown-editor) - Online editor for creating and publishing content to multiple platforms.
- [Chrome extension - ![Chrome Web Store Version Chrome网上商店版本](https://img.shields.io/chrome-web-store/v/dhohkaclnjgcikfoaacfgijgjgceofih)](https://chromewebstore.google.com/detail/multipost/dhohkaclnjgcikfoaacfgijgjgceofih) ![Chrome Web Store Users Chrome网上商店用户](https://img.shields.io/chrome-web-store/users/dhohkaclnjgcikfoaacfgijgjgceofih) ![Chrome Web Store Last Updated](https://img.shields.io/chrome-web-store/last-updated/dhohkaclnjgcikfoaacfgijgjgceofih)
- [Edge extension - ![](https://img.shields.io/badge/dynamic/json?label=edge%20add-on&prefix=v&query=%24.version&url=https%3A%2F%2Fmicrosoftedge.microsoft.com%2Faddons%2Fgetproductdetailsbycrxid%2Fckoiphiceimehjkolnfffgbmihoppgjg)](https://microsoftedge.microsoft.com/addons/detail/multipost/ckoiphiceimehjkolnfffgbmihoppgjg) [![](https://img.shields.io/badge/dynamic/json?label=users&query=%24.activeInstallCount&url=https%3A%2F%2Fmicrosoftedge.microsoft.com%2Faddons%2Fgetproductdetailsbycrxid%2Fckoiphiceimehjkolnfffgbmihoppgjg)](https://microsoftedge.microsoft.com/addons/detail/multipost/ckoiphiceimehjkolnfffgbmihoppgjg)
<!-- ![Edge add-on last updated](https://img.shields.io/badge/dynamic/json?label=last%20updated&query=%24.lastUpdateDate&url=https%3A%2F%2Fmicrosoftedge.microsoft.com%2Faddons%2Fgetproductdetailsbycrxid%2Fckoiphiceimehjkolnfffgbmihoppgjg) -->

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=leaperone/multipost-wechat-markdown-editor,leaperone/MultiPost-Extension&type=Date)](https://www.star-history.com/#leaperone/multipost-wechat-markdown-editor&leaperone/MultiPost-Extension&Date)

## Contact Us
- [Discord](https://discord.gg/GNsCX9zFwQ)
- 微信群
  - 微信扫一扫加入 MultiPost 微信群
    <img src="docs/multipost-wechat-group.jpg" width="350" alt="MultiPost WeChat Group QR Code" />
- [点击加入腾讯频道【MultiPost】](https://pd.qq.com/s/ajj47bgjb) ，频道号：multipostapp
- Email: [support@undersky.ai](mailto:support@undersky.ai)（UnderSky / Agent 模型账户；MultiPost 扩展问题请用 GitHub Issues）
- [GitHub Issues](https://github.com/leaperone/MultiPost-Extension/issues)
- 腾讯频道
  - 微信扫一扫
    <img src="https://github.com/user-attachments/assets/1044058f-036e-4942-af07-e4bd48a1e1d6" width="350" alt="MultiPost Tencent Channel Wechat" />
  - QQ 扫一扫
    <img src="https://github.com/user-attachments/assets/fc9edf3b-1ed5-4aa7-99f9-b39dcab3f449" width="350" alt="MultiPost Tencent Channel QQ" />
