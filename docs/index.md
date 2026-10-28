# AIDV Agent

基于 LangGraph 编排的确定性工作流车载智能体，通过语音、文字与触摸交互，协调车控、导航、媒体和生活服务任务。

**模型负责理解和提议，内核负责校验和执行。** 多步骤任务通过 Gate 等待用户选择或确认，通过 Patch 响应中途修改，并以持久化状态连接前端、语音与工具执行。

## 从这里开始

- **先理解系统**：阅读[系统架构](architecture.md)，了解交互、任务内核与资源服务的分工。
- **先运行项目**：阅读[项目概览与快速开始](modules/overview.md)，选择本地或 Docker 运行方式。
- **部署与验收**：阅读[部署、基础设施与验收](modules/deployment.md)，查配置、TLS、调试入口和验证流程。

模块页中的启动命令与代码路径面向应用源码仓库；本仓库用于构建文档站。

## 模块文档

| 章节 | 主要内容 |
| --- | --- |
| [项目概览与快速开始](modules/overview.md) | 项目能力、环境准备、本地与 Docker 启动、常用配置。 |
| [系统架构总览](modules/system-architecture.md) | 服务平面、拓扑、内核组合根与端到端链路的详细说明。 |
| [内核包 DAG 与分层契约](modules/kernel-dag.md) | 包依赖方向、内核相位、纯逻辑与 I/O 边界。 |
| [工作流生命周期与 Gate 机制](modules/workflow-lifecycle.md) | 任务推进、用户选择与确认、多阶段 Gate 和状态版本。 |
| [多域工具编排与 Patch 机制](modules/tool-orchestration.md) | 工具准入、领域适配、跨域交接与计划局部修改。 |
| [状态存储与数据流](modules/state-storage.md) | 持久化、图执行状态、接口载荷与前端数据消费。 |
| [HMI 前端与调试台](modules/hmi-frontend.md) | 浏览器与 Pad 页面、同源代理、交互卡片与只读调试。 |
| [agent_api 后端服务](modules/agent-api.md) | 任务 API、请求与响应契约、错误处理和内核装配。 |
| [语音会话服务](modules/omni-session.md) | WebSocket 会话、音频管道、打断、播报与语音后端适配。 |
| [LLM 规划与模型集成](modules/llm-integration.md) | 规划子图、提示词、模型传输、编译与校验。 |
| [部署、基础设施与验收](modules/deployment.md) | 服务启动、端口、凭据与 TLS、离线回归和真实服务探针。 |
| [扩展与定制](modules/extensibility.md) | 新增领域、工具、Gate、Provider 与相应契约约束。 |

## 公开文档与示例边界

- 配置仅展示变量名、源码默认值或占位符。回环地址、通配绑定地址及本地 / Docker 默认端口不表示实际部署；内部主机和端口使用 `<internal-svc>`、`<port>` 占位。
- TLS 仅说明配置项和项目相对默认目录，不公开实际部署的证书绝对路径、证书正文、私钥、凭据值或本机凭据文件位置。
- 源码组件名、API 契约字段与第三方接口品牌用于解释实现，不作为客户名单或合作关系声明；示例不使用客户账号、真实订单或精确位置数据，脱敏改写的片段会单独说明。
- 状态字段描述应用对象与接口载荷，不公开底层 SQL、物理表结构或列名。
