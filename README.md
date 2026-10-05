# ERP采集助手正式发布

当前正式版本：v0.12.28。新增委外图片附件，在线更新仅使用 GitHub，优化页面并附升级与功能说明书。

[查看最新版 Release](https://github.com/z892137292/erp-collector-release/releases/latest) · [下载更新包](https://github.com/z892137292/erp-collector-release/releases/latest/download/Collector_Update.zip) · [下载升级说明书](https://github.com/z892137292/erp-collector-release/releases/latest/download/Upgrade_Guide.html)

已有 v0.12.27：设置 → 检查在线更新。

更早版本：在“自定义 / GitHub”中填写固定入口后检查更新，或下载 Collector_Update.zip 进行本地更新。

```
https://github.com/z892137292/erp-collector-release/releases/latest/download/manifest.json
```

新电脑暂时先使用 [v0.12.27 完整安装包](https://github.com/z892137292/erp-collector-release/releases/download/v0.12.27/Collector_Setup.exe)，打开后在线升级至 v0.12.28；免安装可使用 v0.12.27 的便携包后更新。本次先发布轻量更新包。

委外与采购订单都提供“上传图片”和“查看附件”，支持缩略图、原图预览和独立下载。附件接口须支持委外业务类型 biz_type=ODM；本包未包含服务器 PHP 或数据库升级。

软件设置中可直接查看升级说明；每次有版本变化，发布说明与包内功能说明都应同步更新。Chrome 扩展沿用手动加载，本次未修改扩展。

Windows 构建、界面附件操作、窄窗口、更新替换和重启、失败回滚与配置保留检查通过；附件检查使用本地测试数据，真实 ERP、云盘与打印机输出需实机确认。
