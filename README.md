# **MokinSoc - 一站式 QBCore 服务器套件**

https://img.shields.io/badge/License-GPL--3.0-orange.svg](LICENSE)

https://img.shields.io/badge/QBCore-2.2.4-brightgreen.svg](https://qbcore.org)

https://img.shields.io/discord/您的服务器ID?color=7289DA&label=Discord&logo=discord](https://discord.gg/您的邀请链接)

https://img.shields.io/badge/FiveM-Ready-blue.svg](https://fivem.net)

**English** | **中文**

这是一个完整的、经过精心配置和优化的 **QBCore 服务器文件集合**。您无需繁琐地逐个下载和配置资源，本仓库提供了一站式解决方案，助您快速搭建一个功能齐全的 FiveM 角色扮演服务器。


## **✨ 套件内容**

本仓库已为您集成并配置好以下内容：

*   **🧩 核心框架 (QBCore)**: 最新稳定版的 QBCore 框架，已预配置。
*   **🗃️ 数据库结构 (`qbcore.sql`)**: 完整的 MySQL 数据库初始化文件，一键导入即可创建所有所需表格。
*   **⚙️ 服务器配置 (`server.cfg`)**: 优化后的主配置文件，已包含所有必要的资源启动项 (`ensure`) 和参数设置。
*   **🎨 品牌标识 (`myLogo.png`)**: 为您服务器 txAdmin 控制台准备的专属Logo。
*   **📦 精选资源集合 (`resources/` 目录)**: 内置一系列经过测试、兼容且流行的脚本和资源（如：车辆、地图、脚本等），开箱即用。

## **🚀 极速部署指南**

您可以通过以下两种方式之一快速部署整个服务器：

### **方法一：通过 txAdmin 自动部署 (推荐)**

这是最快捷、最无痛的方式。txAdmin 会自动处理所有下载和配置工作。

1.  安装并运行最新版的 https://runtime.fivem.net/artifacts/fivem/build_server_windows/。
2.  在 txAdmin 初始化界面，选择 **“部署新服务器”** -> **“从 URL”**。
3.  粘贴此 **Recipe.yaml 文件的 Raw 地址**：
    `https://raw.githubusercontent.com/你的用户名/MokinSoc/main/recipe.yaml`
4.  跟随 txAdmin 的引导完成后续设置（如数据库配置、管理员账户创建）。
5.  等待部署完成，即可启动服务器！

### **方法二：手动安装 (适用于高级用户)**

如果您希望深入了解或进行自定义修改，请遵循此步骤：

1.  **克隆/下载仓库**:
    ```bash
    git clone https://github.com/你的用户名/MokinSoc.git
    # 或直接下载 ZIP 包并解压
    ```
2.  **设置数据库**:
    *   创建一個名为 `qbcore` 的空数据库。
    *   使用 MySQL 管理工具（如 phpMyAdmin, HeidiSQL）导入 `qbcore.sql` 文件。
3.  **配置连接**:
    *   打开 `server.cfg` 文件，找到 `set mysql_connection_string` 这一行。
    *   将其中的数据库账号、密码和地址修改为您自己的信息。
    *   ```lua
        set mysql_connection_string "mysql://root:你的密码@localhost:3306/qbcore"
        ```
4.  **放置资源**:
    *   将整个 `MokinSoc` 文件夹放入您的 FXServer 目录中。
    *   确保 `server.cfg` 中的 `resources` 路径指向正确。
5.  **启动服务器**:
    *   运行 `FXServer.exe`，在 txAdmin 中登录。
    *   直接启动服务器即可。

## **🔧 基本配置**

服务器启动后，您可能需要根据实际情况调整以下核心设置：

*   **服务器信息**: 在 `server.cfg` 中修改 `sets sv_hostname` 等参数来更改服务器名称和简介。
*   **经济系统**: 大部分经济相关的设置（物品价格、工资等）位于 `qb-core/shared/items.lua` 和各个职业脚本的 `config.lua` 中。
*   **身份识别**: 如需更换服务器 Logo，请用您自己的图片替换 `myLogo.png`。

## **❓ 常见问题 (FAQ)**

**Q: 部署后无法连接数据库？**  
A: 请确保已正确安装 MySQL，数据库已创建，并在 `server.cfg` 中填写了正确的连接字符串。

**Q: 如何添加新的资源？**  
A: 将新资源文件夹放入 `resources/` 目录，然后在 `server.cfg` 文件中添加一行 `ensure 你的资源名`。

**Q: 如何获取更新？**  
A: 我们建议您 Fork 本仓库。当有重大更新时，您可以通过 Git 拉取更新，但请注意**合并可能会覆盖您的自定义配置**，请务必做好备份。

## **📜 许可证**

本项目采用 **GPL-3.0** 许可证。这意味着您可以自由地使用、修改和分发，但如果您发布了修改后的版本，也必须开源。详情请参阅 LICENSE 文件。

## **💬 支持与社区**

如果您在使用中遇到问题或有好的建议：

1.  请先查阅本说明和 https://qbcore.org。
2.  您可以在本仓库的 https://github.com/你的用户名/MokinSoc/issues 页面提交 Bug 或功能请求。
3.  (可选) 加入我们的 Discord 社区获取实时帮助: [邀请链接]
