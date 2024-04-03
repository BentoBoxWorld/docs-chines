# 视频教程

[![视频缩略图](https://i.ytimg.com/vi/01MagYDuOCk/hqdefault.jpg?sqp=-oaymwEjCPYBEIoBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLCzVNO0ObSEMOOpYtUEtv4LjsMhBA)](https://www.youtube.com/watch?v=01MagYDuOCk)

# 简介

BentoBox 是一个强大但特定的插件，需要在服务器上安装和运行。我们 BentoBoxWorld 已经进行了长时间的讨论，以找到最适合 BentoBox 定义特性的最友好的安装方法。

与大多数 Spigot 插件相比，BentoBox 的安装将比简单地拖放到服务器的插件文件夹中花费更多的时间；但它将带来无数可能性，这一切都是值得的。

让我们开始吧！

***

# 下载 BentoBox

你可以在不同的网站上**免费**下载 BentoBox。官方版本可以在插件的 Spigot 页面或 [GitHub `Releases` 选项卡](https://github.com/BentoBoxWorld/bentobox/releases)中找到，而**未经测试的**开发版本可以从 [Jenkins](https://ci.codemc.org/job/BentoBoxWorld/job/BentoBox/) 下载。

# 设置 BentoBox

下载 BentoBox 后，你必须将其放入服务器的 `plugins` 文件夹中。与 ASkyBlock 不同，没有必需的依赖项：BentoBox 会自动挂钩到它找到的插件（如 Vault、PlaceholderAPI、Multiverse-Core 等），以扩展其能力。

启动服务器并等待所有插件完全启用。如果你连接到服务器，你会注意到 BentoBox 并没有做任何特别的事情。事实上，**BentoBox 本身不做任何事情**：它需要你添加 [Addons](https://github.com/BentoBoxWorld/bentobox/wiki/Addons)，这样它才能"学会"管理例如 Skyblock 游戏模式。

现在，关闭服务器。你可以查看 BentoBox 的 `config.yml` 文件。

# 安装附加组件

[Addons](/BentoBox/Addons) 是 BentoBox 的特色所在。但是，请注意，这些**不是插件**：如果你只是把它们放在 `plugins` 文件夹中，它们**不会启动**。

首先，你需要下载要添加到服务器的附加组件。官方附加组件可以在 [BentoBoxWorld 的仓库列表](https://github.com/BentoBoxWorld) 中找到，并可以从它们的 `Releases` 选项卡（或从 [Jenkins](https://ci.codemc.org/job/BentoBoxWorld/) 获取**未经测试的**开发版本）下载。我们将在某个时候建立一个网站，以便你以后可以更轻松地下载它们。

下载完所需的一切后，你只需将它们全部放入 `plugins\BentoBox\addons` 文件夹，启动服务器以创建配置文件和文件夹，最后再次关闭服务器，以便能够编辑所有内容而不会对服务器造成任何损害。

请注意，附加组件有时可能与你使用的 BentoBox 版本不兼容。官方附加组件**始终**会提供明确的支持版本声明。但是，请注意，它们通常无需更新即可支持更新的版本。

# 结论

你应该已经准备好了！
我们很高兴你使用我们的插件，我们希望你会像我们享受改进它一样享受使用它。