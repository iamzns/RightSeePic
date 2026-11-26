# GitHub Pages + jsDelivr 图片仓库说明

## 一、GitHub 仓库

开启 GitHub Pages 网站，上传图片。

## 二、使用 jsDelivr 加速访问

例如：

```text
https://cdn.jsdmirror.com/gh/iamzns/RightSeePic@master/images/test.jpg
```

各 CDN 域名实测结果（截图表格转写）：

| 域名 | 电信 | 联通 | 移动 | 综合 |
| --- | --- | --- | --- | --- |
| cdn.jsdmirror.com | 200，100～190ms | 200，100～400ms（1 个冷节点 3.3s） | 200，60～160ms | 三网全通且最快 |
| jsdelivr.b-cdn.net | 200，1.0～2.5s | 200，0.8～1.0s | 200，0.6～1.3s | 三网全通，偏慢 |
| gcore.jsdelivr.net | 200，1.0～2.7s | 200，0.5～1.2s | 200，1.5～2.1s | 三网全通，偏慢 |
| testingcf.jsdelivr.net | 200，0.7～6.2s | 200，0.8～1.9s | 200，0.65～2.9s | 三网通但不稳 |
| cdn.jsdelivr.net（官方） | 200/301 混合 | 200/301 混合 | 连接重置 ECONNRESET | 移动不可用 |
| fastly.jsdelivr.net | 301 → raw.githubusercontent | 301 + 1 节点失败 | 301 → raw.githubusercontent | 不可用 |
| jsd.onmicrosoft.cn | 301 → raw.githubusercontent | 301 → raw.githubusercontent | 301 → raw.githubusercontent | 不可用 |
| 4everland | 域名不解析（NXDOMAIN） | 同左 | 同左 | 全网已死 |
| test1.jsdelivr.net | 失败 | 失败 | 失败 | 全网失败 |
| raw.githubusercontent.com（跳转目标） | 时通时断（1/3） | 2/3 通 | 全部失败 | 不可靠 |
