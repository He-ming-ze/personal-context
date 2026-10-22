# topics/environment — 机器与工具链

> 需要写具体命令、判断能不能用、排查环境问题前读这个。

updated: 2026-10-22

## 机器

- OS：Windows 11（中文环境），Shell 以 PowerShell 为主。
- 用户目录：`%USERPROFILE%`（下文路径都相对它）。
- 常见坑：PowerShell `Get-Content` 会把 UTF-8 文件显示成乱码（中文变 `浣曟爧1`），文件本身是对的，别据此"修复"文件。

## 运行时

| 工具 | 版本 | 备注 |
|---|---|---|
| Node.js | v24.14.0 | `node` 在 PATH |
| npm | 11.9.0 | |
| pnpm | 11.9.0 | 全局安装 |
| git | 已安装 | `C:\Program Files\Git\cmd\git.exe`，未安装 `gh` CLI |

## 常用工具

- **DeepSeek Harness（DSH）**：Electron 桌面版，内置 dsh `0.1.7-rc.2`，走 nightly 通道。
- **VS Code / Typora**：看和改 Markdown。
- **MCP**：本地 stdio 服务，不做远程调用。

## 目录约定

- 工作区：`%USERPROFILE%\Documents\deepseek-harness\default-workspace`
- 私有记忆库：`%USERPROFILE%\Documents\ai-memory`（不公开，内容不进本仓库）
- 本仓库：`%USERPROFILE%\Documents\deepseek-harness\default-workspace\personal-context`

## DSH 插件

第三方插件装在工作区 `.dsh-plugins`，用绝对路径挂进 `~/.dsh/profiles/desktop/cordis.patch.yml` 的补丁层，不碰 profile 的包管理文件。已验证可用：`@liustack/modsearch`、`@liustack/modlens`、`superpowers-dsh`。

判据：入口 import 了 `@deepseek-ai/dsh-*` 运行时包的插件，这条路挂不上，只能走应用内 Plugins → Add plugin。

## 已知故障

- 命令行间歇性完全起不来：`pwsh` 与终端会话直接报 `0xC0000142`（`STATUS_DLL_INIT_FAILED`），文件读写不受影响。多次复现，原因未定位。看到这个错误不要怀疑命令本身写错了。
