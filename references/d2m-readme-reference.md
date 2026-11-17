# Drop2Markdown

> 隐私优先的 Markdown / Word / Excel / CSV 文档转换工具 — macOS 桌面版 · Windows 版 · Chrome 插件 · Web 版 · MCP Server

纯 Python 标准库引擎（零第三方运行时依赖），本地转换不上传，中文排版针对法律文书场景深度优化。

## 功能特性

- **四端可用**：macOS 桌面 App（拖放转换）、Windows 批处理工具链、Chrome 插件（网页转 MD）、Web 版（纯浏览器本地转换）
- **格式互转**：Markdown ⇄ Word（.docx）⇄ Excel（.xlsx）⇄ CSV，MD→HTML 预览
- **法律文书排版**：默认宋体正文 + 黑体标题 + Times New Roman 西文；公文预设（GB/T 9704-2012）；环境变量可覆盖字体
- **MCP Server**：接入 Claude / Cursor / WorkBuddy 等 AI 客户端，AI 直接调用转换能力
- **隐私设计**：本地处理、无遥测、stats.jsonl 只存本机；v1.3.3 起含 ZIP 炸弹防护、取件台令牌、20MB 输入限制等多重安全加固

## 快速开始（macOS 桌面版）

1. 下载 `Drop2Markdown-mac-vX.X.X.zip`（见 [Releases](../../releases)）并解压
2. 将 `Drop2Markdown.app` 拖入「应用程序」文件夹
3. 首次使用：系统设置 → 隐私与安全性 → 文件和文件夹 → 勾选「文档文件夹」
4. 拖放文件到 App 图标即完成转换

## 快速开始（Windows 版）

详见仓库 `win/Windows 使用说明.md`（需 Python 3.9+，含安装/发送到/运行/打包全工具链）

## 快速开始（Chrome 插件）

1. 下载 `Drop2Markdown-chrome-extension-vX.X.X.zip` 并解压
2. Chrome 打开 `chrome://extensions` → 开启「开发者模式」→「加载已解压的扩展程序」
3. 选解压目录即可；网页上点插件图标转 Markdown

## MCP 接入（AI 客户端）

```json
{
  "mcpServers": {
    "drop2markdown": {
      "command": "python3",
      "args": ["/path/to/mcp_server.py"]
    }
  }
}
独立部署时建议设置 `D2M_MCP_ALLOWED_ROOTS`（允许访问的目录白名单）。
```

## 版本

当前版本 v1.3.3 — 完整版本历史见 [CHANGELOG.md](CHANGELOG.md)

## 许可证

版权所有 © 2026 刘婧（Iris Liu），保留所有权利。
源代码供学习研究参考，商业使用请联系作者。第三方组件许可见 [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md)。

## 作者

Iris Liu — 资深法务 × 独立开发者，[中国软著/上线合规助手](../china-launch-copilot)出品人
