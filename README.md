# 网络信息 𝕏（自托管版）

Surge 网络信息面板模块的自托管副本，核心逻辑与上游 [xream/scripts](https://github.com/xream/scripts)（GPL-3.0，作者 @keywos @xream）保持一致，脚本托管在本仓库，不受上游变动影响。

## 功能

- 国内 / 落地 IP、运营商、ASN、ORG、地理位置
- IPv6、入口落地对比、LAN IP、SSID
- 隐私打码、国旗显示
- 网络变化时自动查询并通知
- 提供 `https://net-lsp-x.com` 数据接口，参数与模块参数相同

## 安装

Surge 中打开：

```
https://raw.githubusercontent.com/fancha0/network-info-x/main/%E7%BD%91%E7%BB%9C%E4%BF%A1%E6%81%AF%20X.sgmodule
```

或一键安装链接：

```
surge:///install-module?url=https%3A%2F%2Fraw.githubusercontent.com%2Ffancha0%2Fnetwork-info-x%2Fmain%2F%25E7%25BD%2591%25E7%25BB%259C%25E4%25BF%25A1%25E6%2581%25AF%2520X.sgmodule
```

## 使用注意

1. **分流**：按所选 IP 来源配置对应域名分流，例如用 `spcn` 就加 `DOMAIN-SUFFIX,speedtest.cn` 走国内直连策略，落地源走代理
2. **MITM**：模块已声明 `net-lsp-x.com`，模块内部数据接口需要 MITM 生效
3. **参数**：安装时可在 Surge 的参数界面逐项调整，说明见模块文件内 `arguments-desc`

## 文件

| 文件 | 说明 |
|------|------|
| `网络信息 X.sgmodule` | 模块定义（脚本路径指向本仓库） |
| `net-lsp-x.js` | 核心脚本（上游副本） |

## 更新脚本

```sh
curl -fsSL -o net-lsp-x.js https://raw.githubusercontent.com/xream/scripts/main/surge/modules/network-info/net-lsp-x.js
```

## 许可

核心脚本遵循上游 [GPL-3.0](https://github.com/xream/scripts/blob/main/LICENSE) 许可，版权归原作者所有。
