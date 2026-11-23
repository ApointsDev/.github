# 锚点团队 · 项目与仓库

这里列出 ApointsDev 的 12 个仓库。查找代码时，可以先按项目定位仓库，再看它与其他仓库如何配合。私有仓库链接需要相应的 GitHub 访问权限。

**整体项目负责人：[@TristanChayne](https://github.com/TristanChayne)**，负责跨仓库技术协调。下表列出每个仓库的默认评审负责人，具体路径分工见各仓库的 `CODEOWNERS`。

## 产品与服务

| 项目 | GitHub 仓库 | 负责人 | 职责与仓库关系 |
| --- | --- | --- | --- |
| 锚客户端 | [AnchorClient](https://github.com/ApointsDev/AnchorClient) | [@ZhangChuqing](https://github.com/ZhangChuqing) | Android、iOS 和 Windows 界面。通过 AnchorScheduler 读写日程，也提供微信助手设置和 AMS 校园功能入口。 登录与注册的评审由 @beaut1fulb0y 负责，AMS 桥接由 @TristanChayne 负责。 |
| 日程系统与 Web 端 | [AnchorScheduler](https://github.com/ApointsDev/AnchorScheduler) | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | 包含 Web 前端和日程后端。为 AnchorClient 提供日程、待办等接口，为 AnchorWechatBot 提供 AI 助手能力；使用 CAF 统一登录。 |
| 微信助手网关 | [AnchorWechatBot](https://github.com/ApointsDev/AnchorWechatBot) | [@Metalxiaoxiao](https://github.com/Metalxiaoxiao) | 接收公众号和微信机器人的消息，转交给 AnchorScheduler 的 AI 助手，再将回复送回微信。 |
| AMS 校园助手 | [AMS-campus-assistant](https://github.com/ApointsDev/AMS-campus-assistant) | [@TristanChayne](https://github.com/TristanChayne) | 维护校园助手的应用、小程序、管理网页和服务。校园业务在此维护，锚客户端内的集成入口在 AnchorClient。 |
| 学习通同步服务 | [chaoxing-crawler-lite](https://github.com/ApointsDev/chaoxing-crawler-lite) | [@woxiangfangjia](https://github.com/woxiangfangjia) | 维护学习通数据采集和同步任务，供 AnchorScheduler 的学习通同步功能使用。 |

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
| 组织首页 | [.github](https://github.com/ApointsDev/.github) | [@TristanChayne](https://github.com/TristanChayne) | 存放本项目索引（profile/README.md），供成员查找仓库与维护联系人。 |

## 跨仓库问题从哪里查

- **微信助手没有回复**：先查 AnchorWechatBot 是否收到消息、能否回发，再查 AnchorScheduler 是否生成回复。客户端里的微信绑定或设置页面由 AnchorClient 维护。
- **学习通课表没有出现在客户端**：按 chaoxing-crawler-lite 的采集任务、AnchorScheduler 的同步入库、AnchorClient 的日程展示依次排查。
- **文档站内容有误**：公开正文改 docs，内部正文改 doc-private；两个站点的构建、样式或访问控制问题改 Docs-website。
