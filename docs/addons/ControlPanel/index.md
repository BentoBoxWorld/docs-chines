**\# ControlPanel**

**ControlPanel** 可让你创建一个用作玩家快捷方式的 GUI。

由 \[BONNe\](https://github.com/BONNe) 创建和维护。

{{ addon\_description("ControlPanel") }}

**\## 安装**

1\. 将插件 jar 文件放入 BentoBox 插件的 addons 文件夹

2\. 重启服务器

3\. 使用管理员命令导入控制面板。

**\## 常见问题**

??? question "如何更改 ControlPanel?"

ControlPanel 将所有 GUI 存储在数据库中,但这并不意味着你需要编辑数据库文件。你仍然可以使用模板文件,但是,要查看更改,你需要导入文件: `/[admin_cmd] controlpanel import <filename>`。

??? question "我可以为不同的用户设置不同的面板吗?"

是的,ControlPanel 支持允许多个不同面板的选项。要为用户激活特定面板,你必须添加权限: `[gamemode].controlpanel.panel.[suffix]`,其中 suffix 是你的 ControlPanel 的 ID 名称。

??? question "你能添加 X 功能吗?"

请将其添加到\[此处\](https://github.com/BentoBoxWorld/ControlPanel/issues)的列表中。

**\## 翻译**

{{ translations(3135, \["cs", "de", "es", "fr", "lv", "zh-CN", "zh-TW", "ko", "pl", "ru", "id", \]) }}