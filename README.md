# 中药制剂全流程区块链溯源演示

## 已完成内容

已根据你的表格创建了一套**简单可用的溯源网页**：

- `index.html`：全流程总览（鉴定 → 炮制 → 调剂 → 制剂）
- `herbs/` 目录：6味药材各自的鉴定页面（产地、公司、批号、显微特征 + SHA-256哈希）
- `process/` 目录：3味需要炮制药材的炮制工艺页面

每个页面都：
- 移动端友好（扫码后直接在手机浏览器打开）
- 纯文字显示（产地、批号、特征、工艺等）
- 自动计算数据的 SHA-256 哈希，模拟“上链存证”

## 如何使用（最简单流程）

### 1. 部署网页（免费）

推荐以下任一方式：

**方式A：GitHub Pages（推荐）**
1. 新建一个 GitHub 仓库
2. 把整个 `tcm-traceability` 文件夹内容上传
3. 仓库 Settings → Pages → 选择 main 分支，保存
4. 几分钟后得到网址，例如：`https://你的用户名.github.io/仓库名/`

**方式B：Netlify / Vercel**
- 直接拖拽整个文件夹上传，立即得到免费域名

**方式C：本地临时测试**
- 用手机和电脑在同一WiFi，用 `python -m http.server 8000` 或任何本地服务器，手机访问电脑IP即可扫码测试

### 2. 生成二维码

用免费工具生成二维码（链接指向你的网页）：

- 全流程总览：指向 `index.html` 的完整URL
- 人参鉴定：指向 `herbs/renshen.html` 的完整URL
- 麸炒白术鉴定：`herbs/baizhu.html`
- 蜜制五味子鉴定：`herbs/wuweizi.html`
- 茯苓：`herbs/fuling.html`
- 麦冬：`herbs/maidong.html`
- 炙甘草：`herbs/gancao.html`
- 炮制页面同理

推荐二维码生成网站（免费、无需登录）：
- https://qrtool.cn
- https://cli.im
- https://www.qr-code-generator.com

生成后下载PNG，打印贴在包装或展示板上即可。

### 3. 真正“上区块链”（可选，进阶）

当前哈希只是在浏览器本地计算，演示用。

真正不可篡改可以：
1. 把页面显示的 SHA-256 哈希复制下来
2. 去免费区块链存证平台提交（例如：
   - 以太坊测试网 / 币安智能链测试网（用MetaMask）
   - 国内一些“区块链存证”服务
   - 或使用 IPFS 上传整页内容，得到CID
3. 把交易哈希或IPFS链接再写回网页，形成闭环

## 文件结构

```
tcm-traceability/
├── index.html              # 全流程总览
├── README.md
├── herbs/
│   ├── renshen.html        # 人参鉴定
│   ├── baizhu.html         # 麸炒白术鉴定
│   ├── wuweizi.html        # 蜜制五味子鉴定
│   ├── fuling.html         # 茯苓鉴定
│   ├── maidong.html        # 麦冬鉴定
│   └── gancao.html         # 炙甘草鉴定
└── process/
    ├── baizhu-paozhi.html  # 麸炒白术炮制
    ├── wuweizi-paozhi.html # 蜜制五味子炮制
    └── gancao-paozhi.html  # 炙甘草炮制
```

## 注意事项

- 这是**演示/教学用**系统，不是正式的企业级区块链溯源平台。
- 正式生产环境建议对接正规中药追溯系统（如“一物一码”平台、省级追溯平台等）。

有问题随时问！
