# 做个样子 JustForShow 官方网站 — 需求与设计说明

#官网 #站点设计 #JustForShow

> 状态：已定稿（v1.0.0） · 日期：2026-09-25
> 本文档先于代码存在；任何口径变更须先回写本文档。

## 1. 需求

为做个样子 JustForShow（数据文件样例提取工具，Windows）建设官方产品站，结构与风格对齐同作者的 PassGone / ExifMate 官网仓库，视觉采用白卡片风格与应用界面一致。

- 域名：`https://justforshow.weibaba.fun`（全局规范第 12 条默认口径）。
- 反馈邮箱：`feed@weibaba.fun`；版权：© 2026 Weibaba. All rights reserved.
- 下载入口：微软商店 `https://apps.microsoft.com/detail/9P30MRGVSPJV`（唯一权威渠道，来源应用仓库 `store/identity.md`，Store ID `9P30MRGVSPJV`）。
- 公测口径：当前为公测期，全功能免费，无任何限制（来源应用仓库 `README.md`）。
- 站点红线（硬性）：纯静态、零追踪——无统计/分析、无任何外部资源请求（无 CDN 字体、外链图片）、无 Cookie、无表单、无服务端代码；全站无 JS（`<a href>` 外链导航除外）；仓库内不得出现用户数据、操作日志、凭据、本机路径。

## 2. 品牌视觉

| 项 | 值 | 来源 |
|---|---|---|
| 品牌橙（主色） | `#E8833A` | 任务指定，与应用主按钮/品牌图标（橙白小丑鱼）一致 |
| 品牌橙 hover | `#D06E28` | 主色加深 |
| 提示底色 | `#FDF3EA` | 主色浅化 |
| 正文墨色 | `#2B2F36` | 深灰墨 |
| 页面背景 | `#F6F7F9` | 浅灰底，配合白卡片 |
| 字体 | 系统字体栈（Microsoft YaHei UI / Segoe UI / system-ui） | 站点红线：零外部字体 |

素材派生（脚本化，禁止各尺寸手改）：

- `assets/img/web_logo.png`：复制自应用仓库 `store/web_logo.png`（1456×720），用作页首横幅 logo；`assets/img/og.png` 为同图，用作全站 og:image。
- `favicon.ico`（16/32/48 多尺寸）、`favicon.png`（64）、`apple-touch-icon.png`（180，白底压平）：由应用仓库 `store/ico/app_icon_no_text.png` 经 Pillow 派生；导航栏小图标复用 `/favicon.png`，不新增文件。

## 3. 站点结构

```
/                     中文主站（lang=zh-CN）
/en/                  English（lang=en）
/privacy/             隐私政策（中英双语同页直排，锚点跳转，零 JS；内容 = 应用 PRIVACY.md，不增删事实）
/assets/style.css     全站唯一样式（白卡片风格骨架 + 品牌橙配色）
/assets/img/          web_logo.png、og.png（同图）
/favicon.ico|.png、/apple-touch-icon.png   由应用源图标派生
/robots.txt /sitemap.xml /_headers /.well-known/security.txt
README.md、AGENTS.md、docs/site-design.md
```

主站信息架构（单页简洁版）：导航（品牌 + 功能/下载/隐私 + 中英切换）→ Hero 白卡片（横幅 logo + slogan「大文件做样，结构全保留」+ 一句话定位 + 特性 pills + 商店按钮）→ 公测提示条（全功能免费 + 反馈邮箱）→ 功能区（支持格式芯片行 + 6 张功能卡）→ 下载区（商店大按钮 + 占位截图框）→ 页脚（四栏 + © 行）。三页面互链：中文 ↔ English ↔ 隐私政策。

SEO：每页 title/description/canonical/og 全套；`hreflang` 三向声明（zh-CN `/`、en `/en/`、x-default `/`）；内联 JSON-LD `SoftwareApplication`（版本 `1.0.0`，来源应用仓库 `pyproject.toml`）。

## 4. 口径来源（权威，禁止编造）

| 站点内容 | 权威来源 |
|---|---|
| 功能特性、支持格式、公测口径 | 应用仓库 `README.md` / `README.en.md`（中英逐节对应） |
| 隐私政策页全部内容 | 应用仓库 `PRIVACY.md`（逐字，不增删事实；生效日期 2026-09-25） |
| 商店链接、Store ID | 应用仓库 `store/identity.md` |
| 应用版本号（JSON-LD） | 应用仓库 `pyproject.toml`（`version = "1.0.0"`） |
| 域名、反馈邮箱、版权 | 全局规范第 12 条 + 任务指定口径 |

## 5. 决策记录

- 截图暂不上线（2026-09-25）：候选截图（应用仓库 `tmp/app_real_font.png`）的源/输出目录输入框中可见本机绝对路径，违反「仓库不得出现本机路径」红线，不予采用（此处置亦不引用该路径字面量）；页面放虚线占位框「界面截图 · 即将补充」，待无本机路径、无敏感示例数据的干净截图就绪后，缩至宽 1200 存为 `assets/img/shot-main.png` 并回写本文档。
- 隐私页不加「关于本网站」节（2026-09-25）：任务红线要求隐私页内容 = `PRIVACY.md` 不增删事实，较 PassGone 先例（曾增补网站自述节）从严执行。
- 零 JS（2026-09-25）：隐私页中英双语同页直排、锚点跳转，不引入语言切换脚本；主站无任何脚本（含 JSON-LD，属数据非逻辑）。
- 导航图标复用 favicon（2026-09-25）：`web_logo.png` 为含中英文的横幅构图，缩小后不可辨，导航改用 `/favicon.png` 64px 方形图标 + 文字品牌，避免新增图像文件。

## 6. 部署（Cloudflare Pages）

- 构建命令：无；输出目录：`/`（仓库根即站点根）。
- 生产分支 `main`；`_headers` 输出 nosniff / DENY / Referrer-Policy / Permissions-Policy。
- DNS：CNAME `justforshow` → Pages 域名（用户侧操作）。

## 7. 版本

| 日期 | 版本 | 说明 |
|---|---|---|
| 2026-09-25 | v1.0.0 | 初版：中文主站、英文版、隐私政策（双语同页）、全套图标派生与配套文件；截图因含本机路径暂缺，占位框替代 |
| v1.0.1 | 2026-09-25 | Hero 融合优化：底色改为 logo 边缘采样的冷调同源渐变（#FEFEFE→#ECEFF4）叠加品牌橙 7% 顶部微光；logo 横幅 780px 全宽、去圆角，左右各 5.5% 线性羽化（约 43px）消融矩形边界；解决「logo 与背景分离」反馈 |
| v1.0.2 | 2026-09-26 | 接入用户提供的干净界面截图（宽幅 1200×422，演示数据树+脱敏路径，经视觉核验无本机路径无真实数据），替换中英两页截图占位；.shot 由虚线占位框改为带阴影图片容器 |
