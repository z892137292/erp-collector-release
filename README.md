# ERP采集助手正式发布

当前正式版本：v0.12.30。默认图片上传文件夹、GitHub 加速下载与 HTTP 延迟测速，并修复大图重复打开。

[查看最新版 Release](https://github.com/z892137292/erp-collector-release/releases/latest) · [下载更新包](https://github.com/z892137292/erp-collector-release/releases/latest/download/Collector_Update.zip) · [下载升级说明书](https://github.com/z892137292/erp-collector-release/releases/latest/download/Upgrade_Guide.html)

## 升级

自动替换 / 重启故障尚未解决，本次建议手动覆盖：退出助手（包括托盘），备份原 resources，解压 Collector_Update.zip，将 payload 内 app 和 extension 覆盖到原 resources。重新打开原 ERP_Collector.exe，确认版本 v0.12.30。例如安装目录为 `D:\下载\ERP_Collector`，覆盖目标就是该目录内的 resources。

新电脑先使用 [v0.12.27 完整安装包](https://github.com/z892137292/erp-collector-release/releases/download/v0.12.27/Collector_Setup.exe)，再按上述步骤覆盖本版更新包。本次发布轻量更新包。

## 设置和图片

设置 → 图片附件 → 图片文件夹，可选择默认上传目录并保存；目录失效时回退系统图片文件夹。上传仍逐次选择图片并绑定当前订单，不会自动上传整个目录。

设置 → 版本与升级，提供可修改的 `https://gh-proxy.org/` 下载加速前缀，默认直连 GitHub；启用后加速下载更新包，失败或 SHA256 校验不符回退 GitHub。发布源、版本及校验值仍来自 GitHub。

点击“测速”，显示直连和加速的 HTTP 请求耗时（ms）、超时和错误。数值在本机实测，不是 ICMP ping，也不代表下载速度。

采购与委外订单都有上传图片、查看附件、缩略图、原图和下载。原图每次打开重新获取链接；加载失败重试一次。服务器接口须支持 biz_type=ODM；本包未包含服务器 PHP 或数据库变更。

每版升级与功能说明书同步放在软件设置和发布附件中。保留现有 ERP、登录、打印机与标签设置；Chrome 扩展沿用手动加载。

14 项本地检查、Windows 界面和窄窗口、安装启动、更新器文件替换 / 回滚检查通过。附件和网络使用测试数据，真实云盘、用户电脑的自动重启与打印输出仍需实机验证。
