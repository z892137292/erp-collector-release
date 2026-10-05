# ERP采集助手正式发布

当前正式版本：v0.12.32。独立增加业务标签、按账号恢复布局和到货日／周查询。保留原采集核心、登录、扫码、打印与上传接口。

[查看最新版 Release](https://github.com/z892137292/erp-collector-release/releases/latest) · [下载更新包](https://github.com/z892137292/erp-collector-release/releases/latest/download/Collector_Update.zip) · [下载升级说明书](https://github.com/z892137292/erp-collector-release/releases/latest/download/Upgrade_Guide.html)

## 升级

先下载 Server_Arrivals_Update.zip，按其中 README 将新增 collector_arrivals.php 部署到原 sync.php、common.php 和 erp_tokens.json 同目录；不覆盖原接口。到货页及恢复的订单详情需要此只读接口。

v0.12.31 可使用在线更新；v0.12.30 或更早版本首次请手动覆盖：退出助手（包括托盘），备份原 resources，解压 Collector_Update.zip，将 payload 内 app 和 extension 覆盖到原 resources。重新打开原 ERP_Collector.exe，确认版本 v0.12.32。例如安装目录为 `D:\下载\ERP_Collector`，覆盖目标就是该目录内的 resources。

新电脑先使用 [v0.12.27 完整安装包](https://github.com/z892137292/erp-collector-release/releases/download/v0.12.27/Collector_Setup.exe)，再按上述步骤覆盖本版更新包。本次发布轻量更新包。

## 设置和图片

设置 → 图片附件 → 图片文件夹，可选择默认上传目录并保存；目录失效时回退系统图片文件夹。上传仍逐次选择图片并绑定当前订单，不会自动上传整个目录。

设置 → 版本与升级，提供可修改的 `https://gh-proxy.org/` 下载加速前缀，默认直连 GitHub；启用后加速下载更新包，失败或 SHA256 校验不符回退 GitHub。发布源、版本及校验值仍来自 GitHub。

点击“测速”，显示直连和加速的 HTTP 请求耗时（ms）、超时和错误。数值在本机实测，不是 ICMP ping，也不代表下载速度。

采购与委外订单都有上传图片、查看附件、缩略图、原图和下载。原图每次打开重新获取链接；加载失败重试一次。服务器接口须支持 biz_type=ODM；独立到货服务器补丁不替换原上传接口，不执行生产数据库结构变更。

每版升级与功能说明书同步放在软件设置和发布附件中。保留现有 ERP、登录、打印机与标签设置；Chrome 扩展沿用手动加载。

24 项本地检查、完整 Windows 构建、界面和窄窗口、安装启动、更新器文件替换 / 回滚检查通过。实际主程序启动函数的中文 / 空格目录覆盖重启、调用进程真正退出后继续更新、退出交接失败保留原程序检查通过。附件和网络使用测试数据，真实云盘、用户电脑的自动重启与打印输出仍需实机验证。

## 业务标签与到货

标签按业务和订单命名；同一业务去重，不同订单可分别打开。切换保留筛选和滚动，按账号恢复标签，右键关闭或刷新，上传时关闭提示；最多 20 个标签共用一个渲染界面与原采集连接。

到货页按实际批次时间查询今天、本周和自选日期，支持采购／委外、关键词、分页和服务器历史；统计不受最近 50 张订单限制。旧表没有可靠的完整批次标识，订单进度显示“待核实”，不会将没有采集到记录判作未到货。原 ERP 跳转只使用当前扩展已识别的同源详情链接；缺少链接时复制订单号。

PHP/MySQL 隔离数据库授权、日期、全范围计数、分页、重复物料行和业务隔离检查通过。十多个外部网页的稳定性、真实服务器部署及打印仍需实机验收。本版暂不加入完整浏览器、复杂报表和手机号物流。
