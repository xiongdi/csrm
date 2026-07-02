# CSRM

**Controller → Service → Repository → Mapper**

面向中小团队 + 中型项目的 Java 后端四层架构规范。

## 定位

填补传统 MVC（太简单）与 DDD/COLA（太复杂）之间的空白。

## 核心原则

- **四层各司其职**：C 处理请求参数和返回结果，S 处理业务逻辑，R 封装数据访问，M 负责底层 SQL
- **严禁跨层调用**：每一层只能调用紧邻的下一层
- **严禁同层调用**：同一层的类之间不互相注入
- **跨模块协调**：Service 可注入多个 Repository，这是唯一合法方式

## 技术栈

- Spring Boot
- MyBatis-Flex（Mapper 继承 `BaseMapper`，Repository 继承 `ServiceImpl`）

## 使用方式

本仓库是一个 [Antigravity Agent Skill](./SKILL.md)，将其放置到 `.agents/skills/csrm/` 目录下即可在 AI 辅助开发时自动遵循 CSRM 架构规范。

## License

[CC0 1.0 Universal](./LICENSE)