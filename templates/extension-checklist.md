# 浏览器插件上架清单（Edge 先行策略）

> 沉淀自 Drop2Markdown Chrome 插件上架实践

## 为什么 Edge 先行

| 商店 | 开发者费 | 审核速度 | 生态 |
|---|---|---|---|
| **Edge Add-ons** | 免费 | 快（当天~3 天） | 必应生态，竞争小 |
| **Chrome Web Store** | $5（一次性） | 1~7 天 | 最大，必上 |

**策略**：Edge 先上练手走完一遍审核流程 → 材料复用上 Chrome，心理成本最低。

## 通用准备材料

- [ ] 插件 zip 包（版本号、manifest、隐私文档三处一致）
- [ ] 商店截图 3-5 张（1280×800，展示核心功能界面）
- [ ] 图标 128×128（商店展示用）
- [ ] 简短描述（一句话）+ 详细描述（功能列表）
- [ ] **隐私政策页面 URL**（收集任何数据都必须有；纯本地处理也建议放一份「不收集数据」声明）
- [ ] 开发者账号（Edge：微软账号免费注册；Chrome：Google 账号 + $5 验证费）

## Edge Add-ons 上架步骤

1. https://partner.microsoft.com/dashboard/microsoftedge 注册开发者（免费）
2. 「Create new extension」→ 上传 zip
3. 填商店信息：描述、截图、分类（选 Developer Tools / Productivity）、隐私政策 URL
4. 提交审核 → 通常当天~3 天过审
5. 过审后商店链接生效，后台自带安装量统计（**这是最准的下载统计来源**）

## Chrome Web Store 上架步骤

1. https://chrome.google.com/webstore/devconsole 注册，付 $5 验证费（信用卡/借记卡）
2. 「New item」→ 上传 zip
3. 商店资料从 Edge 复制（描述/截图可复用，注意 Chrome 要求至少 1 张 1280×800 截图）
4. **隐私声明填报**：CWS 问卷逐项勾选权限用途（如 host 权限为什么需要、是否收集浏览历史）——与 manifest 权限一一对应，乱勾会被拒
5. 提交 → 1~7 天审核；被拒会给出原因（最常见：权限用途描述不清、截图与实际不符）

## 常见被拒原因与规避

| 被拒原因 | 规避 |
|---|---|
| 权限过多 | manifest 最小权限原则，用不到的权限删掉再提交 |
| host_permissions 全域 `<all_urls>` | 尽量收窄到实际需要的域名；确实需要全站的，隐私声明写清用途 |
| 隐私政策缺失/不含数据说明 | 用 `privacy-policy-skeleton.md` 起草，URL 可访问 |
| 截图与功能不符 | 用真实界面截图，勿用概念图 |
| 描述堆砌关键词 | 正常描述功能，别堆 SEO 词 |

## 版本更新纪律

- 每次更新：改 manifest version → 重打 zip → 两商店分别提交（审核相互独立）
- 商店版本与官网 version.json 保持同步，避免用户升级混乱
