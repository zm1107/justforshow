# 做个样子 JustForShow 官方网站

#官网 #网站仓库 #JustForShow

<div align="center">

<img src="assets/img/web_logo.png" width="420" alt="做个样子 JustForShow">

**大文件做样，结构全保留**

批量提取数据文件的表头与前 N 行样例，1:1 镜像目录结构，秒级生成轻量测试数据集

`Windows 10 / 11` · `.xlsx / .xls / .csv` · `公测期全功能免费` · `完全本地运行`

[官网 justforshow.weibaba.fun](https://justforshow.weibaba.fun) · [从微软商店下载](https://apps.microsoft.com/detail/9P30MRGVSPJV) · [隐私政策](https://justforshow.weibaba.fun/privacy/)

</div>

## 产品简介

做个样子（JustForShow）批量提取数据文件的表头与前 N 行样例，目标目录 1:1 镜像源目录结构（含空文件夹），秒级生成轻量测试数据集：

- Excel：`.xlsx`、`.xls`（多 Sheet 全保留，名称与顺序不变）
- 文本：`.csv`（自动识别并保持编码、分隔符与换行符）
- 大文件流式读取头部数据，几十 GB 文件不卡死；实时进度、逐文件日志、体积缩减汇总

当前为公测期：全功能免费，无任何限制。功能与版本口径以应用仓库 `README.md` 为权威，本仓库不另行维护产品文档。

## 关于本仓库

本仓库托管做个样子 JustForShow 官方网站（justforshow.weibaba.fun）源码，遵循发布规范 9.3 的网站仓库结构：

```
index.html               中文主站
en/index.html            英文版
privacy/index.html       隐私政策（内容 = 应用仓库 PRIVACY.md，不增删事实）
assets/style.css         全站唯一样式（品牌橙 #E8833A · 白卡片风格 · 系统字体栈）
assets/img/              web_logo.png（页首 logo）、og.png（og:image，同图）
favicon.ico|.png、apple-touch-icon.png   由应用源图标脚本化派生
robots.txt、sitemap.xml、_headers、.well-known/security.txt
docs/site-design.md      站点需求与设计文档（含版本表，口径变更先回写此文档）
```

- 纯静态、零追踪：无统计/分析、无任何外部资源请求、无 Cookie、无表单、无服务端代码、全站无 JS。
- 产品口径（功能、格式、下载渠道、隐私政策）以应用仓库为权威；本仓库不编辑、不新增产品事实。
- Cloudflare Pages 静态托管：生产分支 `main`，仓库根即站点根，无构建命令。

## 反馈与联系

- 反馈邮箱：[feed@weibaba.fun](mailto:feed@weibaba.fun)
- 安全问题：见 [.well-known/security.txt](.well-known/security.txt)
