# CSRM

**Controller → Service → Repository → Mapper**

面向小型团队 + 中型项目的 Java 后端四层架构规范。

## 定位

填补传统 MVC（太简单）与 DDD/COLA（太复杂）之间的空白。

## 核心原则

- **四层各司其职**：C 处理请求参数和返回结果，S 处理业务逻辑，R 封装数据访问，M 负责底层 SQL
- **严禁跨层调用**：每一层只能调用紧邻的下一层
- **严禁同层调用**：同一层的类之间不互相注入
- **跨模块协调**：Service 可注入多个 Repository，这是唯一合法方式

## 技术栈

- Spring Boot
- MyBatis（核心仅依赖原生 MyBatis，推荐使用 MyBatis-Flex 或 MyBatis-Plus 作为效率提升扩展）

## 使用方式

本仓库提供了适配多种 AI 编码工具的规则文件，内容一致，格式各异。

将本仓库克隆到项目根目录，或将对应文件复制到你的项目中即可：

| 工具 | 规则文件 | 安装方式 |
|------|---------|---------|
| **Antigravity (agy)** | [`AGENTS.md`](./AGENTS.md) | 复制并保存为项目根目录的 `.agents/AGENTS.md`（项目全局规则） |
| **Claude Code (cc)** | [`CLAUDE.md`](./CLAUDE.md) | 复制并保存为项目根目录的 `CLAUDE.md` |
| **Codex (codex)** | [`AGENTS.md`](./AGENTS.md) | 复制并保存为项目根目录的 `AGENTS.md` |
| **OpenCode (oc)** | [`AGENTS.md`](./AGENTS.md) | 复制并保存为项目根目录的 `AGENTS.md`（oc 兼容 AGENTS.md） |
| **Cursor** | [`.cursor/rules/csrm.mdc`](./.cursor/rules/csrm.mdc) | 复制并保存为项目根目录的 `.cursor/rules/csrm.mdc`（Cursor 自动匹配） |

### 🤖 AI 助手自动安装（推荐）

你可以直接复制以下提示词发送给你的 AI 编码助手（如 Claude Code, Cursor 等），它会自动识别自己并完成下载与配置：

```markdown
请检查你当前运行的 AI 助手环境，并从开源仓库（https://github.com/xiongdi/csrm）自动下载对应的 CSRM 架构规范规则文件并配置到我当前的项目中：

1. 如果你是 Antigravity (agy)：从 `https://raw.githubusercontent.com/xiongdi/csrm/main/AGENTS.md` 下载并保存为项目根目录的 `.agents/AGENTS.md`（若文件夹不存在请自动创建）。
2. 如果你是 Claude Code (cc)：从 `https://raw.githubusercontent.com/xiongdi/csrm/main/CLAUDE.md` 下载并保存为项目根目录的 `CLAUDE.md`。
3. 如果你是 Codex 或 OpenCode (oc)：从 `https://raw.githubusercontent.com/xiongdi/csrm/main/AGENTS.md` 下载并保存为项目根目录的 `AGENTS.md`。
4. 如果你是 Cursor：从 `https://raw.githubusercontent.com/xiongdi/csrm/main/.cursor/rules/csrm.mdc` 下载并保存为项目根目录的 `.cursor/rules/csrm.mdc`（若文件夹不存在请自动创建）。

请使用你拥有的网络请求或终端工具（如 curl / wget / fetch / Python 脚本）获取文件内容，并在本地写入。完成安装后，向我确认。
```

## License

[CC0 1.0 Universal](./LICENSE)