# 🔥 FireMail - 花火邮箱助手

🌟 一款专为多种邮箱设计的批量收件工具，提供简单高效的邮件管理解决方案。

[![GitHub](https://img.shields.io/github/license/fengyuanluo/firemail)](https://github.com/fengyuanluo/firemail)

## 🖼️ 项目截图

![image](https://git.adust.f5.si/gh/fengyuanluo/tuchuang@main/20250410194654.png)

![image](https://git.adust.f5.si/gh/fengyuanluo/tuchuang@main/20250410194726.png)

![image](https://git.adust.f5.si/gh/fengyuanluo/tuchuang@main/20250410194744.png)

## 📋 项目功能

- 📥 **批量导入邮箱**：支持"邮箱----密码----客户端ID----RefreshToken"的批量导入格式
- 📊 **邮箱管理**：批量操作多个邮箱账户，支持单个或批量删除
- 📬 **自动收信**：对导入的邮箱进行自动收信操作，支持全部收信或选择性收信
- 👥 **多用户系统**：支持用户注册、登录，权限分级管理，管理员可管理所有用户
- 🔐 **安全管理**：数据存储在本地SQLite数据库，密码采用PBKDF2和SHA-256算法加密
- 🔍 **邮件搜索**：支持按关键词、发件人、主题等条件搜索邮件
- 📱 **响应式设计**：适配桌面和移动设备，提供良好的用户体验

## 📧 支持的邮箱类型

目前已支持以下类型的邮箱：

- **Microsoft Outlook**
- **Hotmail**
- **Gmail**
- **QQ邮箱**
- **IMAP协议邮箱**（通用支持）

## ✨ 项目特点

- 🚀 **批量管理**：支持多选、全选邮箱，进行批量删除、收信操作
- 🔄 **WebSocket实时通信**：及时反馈处理进度和结果，提供良好的交互体验
- 🧵 **多线程处理**：提高邮件收取效率，支持并行处理多个邮箱
- 🎨 **简洁界面**：基于Vue 3和Element Plus构建简约现代的用户界面
- 💻 **跨平台支持**：支持Windows和Linux平台，满足不同环境需求
- 🔧 **Docker支持**：可打包为Docker容器快速部署，提供多种部署方式

## 🏗️ 系统架构

FireMail采用前后端分离的架构设计，主要包含以下几个核心部分：

1. **前端界面**：基于Vue.js和Element Plus构建的用户界面
2. **后端API服务**：使用Flask框架实现的RESTful API
3. **WebSocket服务**：用于实时通信和进度反馈
4. **数据库**：SQLite关系型数据库用于数据存储
5. **邮件处理引擎**：处理邮件收取、解析和存储的核心模块

```
+-------------------+        +-------------------+
|                   |        |                   |
|   用户浏览器       |  HTTP  |   前端应用        |
|   (Browser)       |<------>|   (Vue.js)        |
|                   |        |                   |
+-------------------+        +---------^---------+
                                      |
                                      | WebSocket/HTTP
                                      |
+-------------------+        +---------v---------+
|                   |        |                   |
|   数据库          |<------>|   后端API服务      |
|   (SQLite)        |        |   (Flask)         |
|                   |        |                   |
+-------------------+        +---------^---------+
                                      |
                                      | 调用
                                      |
                             +---------v---------+
                             |                   |
                             |   邮件处理引擎     |
                             |   (Python)        |
                             |                   |
                             +-------------------+
                                      |
                                      | OAuth/IMAP
                                      |
                             +---------v---------+
                             |                   |
                             |   邮件服务器       |
                             |   (Outlook等)     |
                             |                   |
                             +-------------------+
```

## 🛠️ 技术栈

- **后端**：Python 3.10+, Flask, SQLite, WebSocket
- **前端**：Vue 3, Vite, Element Plus
- **其他**：OAuth 2.0, IMAP, Docker

## 📚 文档

详细的部署指南、使用说明和API文档请查看项目的`docs`文件夹：

- **部署指南**：[docs/部署指南.md](docs/部署指南.md)
- **用户指南**：[docs/用户指南.md](docs/用户指南.md)
- **API接口文档**：[docs/API接口文档.md](docs/API接口文档.md)
- **系统架构**：[docs/系统架构.md](docs/系统架构.md)

## 🔮 未来开发计划

### 📧 更多邮箱类型支持

- **Yahoo Mail**：雅虎邮箱
- **163邮箱**：网易163邮箱
- **Proton Mail**：注重隐私的加密邮箱
- **Zoho Mail**：企业邮箱解决方案

### 🎨 界面美化

- **深色模式**：提供暗黑主题支持
- **自定义主题**：允许用户自定义界面颜色
- **更多视觉效果**：添加过渡动画和交互反馈
- **移动端优化**：进一步优化移动设备体验
- **响应式布局增强**：适配更多屏幕尺寸

### 📤 发件功能支持

- **基础发信功能**：支持纯文本和HTML格式邮件发送
- **定时发送**：设置邮件在特定时间发送
- **群发功能**：支持一次向多个收件人发送邮件
- **邮件模板**：预设多种邮件模板，快速编辑发送
- **草稿保存**：自动保存未完成的邮件为草稿

### 📈 邮箱功能增强

- **邮件分类与标签**：智能分类和标签管理
- **邮件过滤规则**：自定义邮件过滤和自动处理规则
- **邮件提醒**：重要邮件的通知提醒
- **邮件归档**：长期存储和归档管理
- **数据分析**：邮件使用情况统计和可视化分析

## 📄 开源协议

本项目采用 [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0) 许可证进行开源。

## ⚠️ 免责声明

1. 本工具仅用于方便用户管理自己的邮箱账户，请勿用于非法用途。
2. 使用本工具过程中产生的任何数据安全问题、账户安全问题或违反相关服务条款的行为，均由用户自行承担责任。
3. 开发者不对使用本工具过程中可能出现的任何损失或风险负责。
4. 本工具与Microsoft、Google等邮箱服务提供商没有任何官方关联，使用时请遵守相关服务条款。
5. 邮箱账号和密码等敏感信息仅存储在本地SQLite数据库中，请确保服务器安全，防止数据泄露。
6. 使用本工具可能会受到邮箱服务提供商的API访问限制或策略变更的影响，如遇访问受限，请遵循相关提供商的政策调整使用方式。
7. 本工具不保证100%的兼容性和可用性，可能因第三方服务变更而需要更新。
8. 用户在使用过程中应遵守当地法律法规，不得用于侵犯他人隐私或其他非法活动。
9. 本软件按"原样"提供，不提供任何形式的保证，无论是明示的还是暗示的。

## 🔗 相关链接

- 项目地址：[https://github.com/fengyuanluo/firemail](https://github.com/fengyuanluo/firemail)
- 问题反馈：请在项目的Issues页面提交
- 文档目录：查看`/docs`文件夹获取更详细的使用指南、API文档和部署说明

---

💖 如果您喜欢这个项目，请给它一个Star！ 