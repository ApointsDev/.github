# AnchorLink锚点团队 工作安排

这里列出 ApointsDev 的 12 个仓库。查找代码时，可以先按项目定位仓库，再看它与其他仓库如何配合。私有仓库链接需要相应的 GitHub 访问权限。

**整体项目负责人：[@Metalxiaoxiao](https://github.com/metalxiaoxiao)**，负责跨仓库技术协调。下表列出每个仓库的默认评审负责人，具体路径分工见各仓库的 `CODEOWNERS`。

## 产品与服务

| 项目 | GitHub 仓库 | 负责人 | 职责与仓库关系 |
| --- | --- | --- | --- |
| 锚客户端 | [AnchorClient](https://github.com/ApointsDev/AnchorClient) | [@Metalxiaoxiao](https://github.com/metalxiaoxiao) [@TristanChayne](https://github.com/TristanChayne) | Android、iOS 和 Windows 界面。通过 AnchorScheduler 读写日程，也提供微信助手设置和 AMS 校园功能入口，AMS 桥接和UX设计由 @TristanChayne 负责。 |
| 日程系统与 Web 端 | [AnchorScheduler](https://github.com/ApointsDev/AnchorScheduler) | [@TristanChayne](https://github.com/TristanChayne)、[@qy321666](https://github.com/qy321666)、[@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | 包含 Web 前端和日程后端。为 AnchorClient 提供日程、待办等接口，为 AnchorWechatBot 提供 AI 助手能力；使用 CAF 统一登录。 |
| 微信助手网关 | [AnchorWechatBot](https://github.com/ApointsDev/AnchorWechatBot) | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | 接收公众号和微信机器人的消息，转交给 AnchorScheduler 的 AI 助手，再将回复送回微信。 |
| AMS 校园助手 | [AMS-campus-assistant](https://github.com/ApointsDev/AMS-campus-assistant) | [@TristanChayne](https://github.com/TristanChayne) | 维护校园助手的应用、小程序、管理网页和服务。校园业务在此维护，AnchorCat客户端内的集成入口在 AnchorClient。 |
| 学习通同步服务 | [chaoxing-crawler-lite](https://github.com/ApointsDev/chaoxing-crawler-lite) | [@woxiangfangjia](https://github.com/woxiangfangjia) | 维护学习通数据采集和同步任务，供 AnchorScheduler 的学习通同步功能使用。 |

## 日程客户端与校园助手的平台分工

AnchorScheduler 由 [@Metalxiaoxiao](https://github.com/Metalxiaoxiao)、[@TristanChayne](https://github.com/TristanChayne)、[@qy321666](https://github.com/qy321666) 共同开发。[@TristanChayne](https://github.com/TristanChayne) 与 [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) 共同协调日程产品的桌面端和移动端开发。各平台日常开发与评审按下表分工。

| 项目与平台 | 开发负责人 | 代码位置 |
| --- | --- | --- |
| AnchorCat客户端 · iOS | [@TristanChayne](https://github.com/TristanChayne) 主责 | `AnchorClient/ios/` |
| AnchorCat客户端 · Android | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) 主责 | `AnchorClient/android/` |
| AnchorCat客户端 · 鸿蒙 | [@qy321666](https://github.com/qy321666) | 独立源码目录待落地 |
| AnchorCat客户端 · 桌面端 | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao)、[@qy321666](https://github.com/qy321666) | `AnchorClient/desktop/`、`AnchorClient/src/features/desktopShell/` |
| AMS 校园助手 · 桌面端 | [@TristanChayne](https://github.com/TristanChayne) [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | `AMS-campus-assistant`，独立桌面源码目录待落地 |

## 账号与团队协作

| 项目 | GitHub 仓库 | 负责人 | 职责与仓库关系 |
| --- | --- | --- | --- |
| 统一认证与授权 | [CAFServer](https://github.com/ApointsDev/CAFServer) | [@woxiangfangjia](https://github.com/woxiangfangjia) | 负责登录、令牌和应用授权。日程系统在这里接入统一身份；授权流程或协议变更在此维护。 |
| 用户中心 | [UserCenter](https://github.com/ApointsDev/UserCenter) | [@qy321666](https://github.com/qy321666) | 维护面向用户的登录回调、个人资料和已授权应用页面。用户中心界面问题在此处理，认证协议问题由 CAFServer 维护。 |
| 反馈工单台 | [AnchorDesk](https://github.com/ApointsDev/AnchorDesk) | [@TristanChayne](https://github.com/TristanChayne) | 承接 AnchorClient 用户反馈和内部反馈，供团队认领、处理和审批工单。 |

## 文档与组织

| 项目 | GitHub 仓库 | 负责人 | 职责与仓库关系 |
| --- | --- | --- | --- |
| 公开开发文档 | [docs](https://github.com/ApointsDev/docs) | [@woxiangfangjia](https://github.com/woxiangfangjia) | 存放公开的接入指南、接口说明和示例，作为 Docs-website 的公开内容源。 |
| 内部文档 | [doc-private](https://github.com/ApointsDev/doc-private) | [@qy321666](https://github.com/qy321666) | 存放面向团队的 Markdown 文档，作为 Docs-website 的内部内容源。 |
| 文档站程序 | [Docs-website](https://github.com/ApointsDev/Docs-website) | [@qy321666](https://github.com/qy321666) | 分别构建 docs 与 doc-private，维护主题、导航和内部区访问控制。 |
| 组织首页 | [.github](https://github.com/ApointsDev/.github) | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | 存放本项目索引（profile/README.md），供成员查找仓库与维护联系人。 |
