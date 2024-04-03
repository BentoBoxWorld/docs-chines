# 岛屿保护、标志和等级

[TOC]

## 简介
玩家（甚至环境，如实体、活塞等）与岛屿的交互由一组**标志**控制，这些标志**确定*谁*或*什么*可以在岛上做什么**。这些标志主要由 BentoBox 处理和提供，但附加组件（例如 [Greenhouses](https://github.com/BentoBoxWorld/Greenhouses)）可以添加自己的标志。

在[此处](/en/latest/BentoBox/Flags)查看标志列表。

## 设置面板

**设置面板**是岛主可以编辑岛屿标志配置的 GUI。其他玩家，包括岛屿成员，只能查看它们。

可以使用以下命令打开此 GUI：`/[player_command] settings`（需要以下权限：`[gamemode].island.settings`）。

![设置面板的默认视图](https://user-images.githubusercontent.com/20014332/80591492-1689c100-8a1e-11ea-9a59-c55f35ab6ad9.png)

*设置面板的默认视图。*

管理员可以使用管理员设置命令更改玩家岛屿的设置：`/[admin_command] settings <player_name>`

### 保护选项卡

**保护选项卡**是打开设置面板时显示的选项卡。它包括**保护标志**。

**保护标志**是可以按[等级](#ranks)设置的标志。通过**左键**或**右键**单击标志的图标，岛主将在各个等级之间循环，以便根据玩家的等级允许或禁止标志所控制的交互。

![保护标志示例](https://user-images.githubusercontent.com/20014332/62974085-b31c1c80-be17-11e9-8b27-2fd4bf54ae87.png)

*保护标志示例。*

默认情况下，大多数保护标志设置为仅允许岛屿成员（或以上等级）进行交互。但是，有些最初也允许访客。请参阅[游戏模式的 config.yml]。

![默认情况下允许访客进行交互的保护标志示例](https://user-images.githubusercontent.com/20014332/62974359-553c0480-be18-11e9-8679-0033fd8bf8bd.png)

*默认情况下允许访客进行交互的保护标志示例。*

管理员可以使用管理员设置命令设置岛屿边界外的保护工作方式：`/[admin_command] settings`

### 设置选项卡

### 显示模式

从 [BentoBox 1.6.0](https://github.com/BentoBoxWorld/BentoBox/releases/tag/1.6.0) 开始，可以在设置面板中显示各种数量的标志，具体取决于**显示模式**。
它可以是 `BASIC`、`ADVANCED` 或 `EXPERT`。
可以通过单击设置面板右上角的金锭更改显示模式。

![更改显示模式](https://user-images.githubusercontent.com/20014332/80592558-f0652080-8a1f-11ea-9b7a-eaf3d585b753.png)

`BASIC` 是默认的显示模式，具有我们认为对管理岛屿至关重要的标志。

![基本保护标志](https://user-images.githubusercontent.com/20014332/80592424-b98f0a80-8a1f-11ea-94f5-3b2246b6ae61.png)

`ADVANCED` 具有更多标志，以允许进一步自定义岛屿。

![高级保护标志](https://user-images.githubusercontent.com/20014332/80592698-24d8dc80-8a20-11ea-93d5-3b1b8dbcd18d.png)

`EXPERT` 具有所有可用的标志。有太多标志以至于需要额外的页面。

![专家保护标志](https://user-images.githubusercontent.com/20014332/80592793-4df96d00-8a20-11ea-891e-8833578642e4.png)

### 隐藏标志

从 [BentoBox 1.4.0](https://github.com/BentoBoxWorld/BentoBox/releases/tag/1.4.0) 开始，管理员可以通过打开设置面板并在要隐藏的标志图标上++shift+左键++来隐藏 GUI 中的标志。
这将为图标应用"消失诅咒"附魔，并将导致相应的标志对玩家隐藏。
管理员可以通过重复相同的过程重新显示标志。

![默认标志](https://user-images.githubusercontent.com/20014332/80591609-45a03280-8a1e-11ea-9e37-4725d62cdb3c.png)

*玩家查看允许显示的所有基本标志。*

![消失诅咒](https://user-images.githubusercontent.com/20014332/80591692-6799b500-8a1e-11ea-9ab8-e076f47d2220.png)

*将"消失诅咒"应用于其中一个标志。*

![一堆隐藏的标志](https://user-images.githubusercontent.com/20014332/80591757-839d5680-8a1e-11ea-8864-83b09252a7b9.png)

*玩家查看基本标志，"活板门"标志被隐藏。*

## 等级

TODO.

* BANNED: -1（部分未使用）
* VISITOR: 0
* COOP: 200
* TRUSTED: 400
* MEMBER: 500
* SUB-OWNER: 900
* OWNER: 1000
* MOD: 5000（未使用）
* ADMIN: 10000（未使用）

## 绕过保护

## 管理员设置面板

### 世界设置

### 世界默认保护