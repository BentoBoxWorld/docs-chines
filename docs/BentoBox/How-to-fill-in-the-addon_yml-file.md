# 如何填写 addon.yml 文件？

## 这个文件是什么？

**addon.yml** 文件为 BSkyBlock 在尝试加载你的插件时提供了宝贵信息。该文件由一组属性组成，每个属性定义在新行上且不使用任何缩进。

如果没有这个文件或者没有正确填写，BSkyBlock 将不会加载你的插件，并将其标记为 `INVALID_DESCRIPTION`。

## 必填属性

### name

**描述：** 这个插件的名称。

**代码：**
```yaml
name: "MySuperAddon"
```

**注释：**
1. 必须由所有字母数字字符和下划线组成 (a-z,A-Z,0-9, \_)。
2. 不支持空格，空格会自动转换为下划线。
3. 它用于在整个 BSkyBlock 的 API 内部识别插件。
4. 当用户输入 `/bsadmin version YourSuperAddon` 时显示。

### main

**描述：** 指向扩展了 `BSAddon` 类的地址。

**代码：**
```yaml
main: fr.poslovitch.myaddon.MySuperAddon
```

**注释：**
1. 这必须包含完整的命名空间，包括类文件本身，就像 Bukkit 一样。因此，如果你的命名空间是 `fr.poslovitch.myaddon`，并且你的类文件称为 `MySuperAddon`，那么这应该是 `fr.poslovitch.myaddon.MySuperAddon`。

### version

**描述：** 你的插件版本。

**代码：**
```yaml
version: 1.0.0
```

**注释：**
1. 版本是一个任意字符串，然而最常见的格式是 MajorRelease.MinorRelease.FixRelease（例如：3.6.1）。
2. 当用户输入 `/bsadmin version YourSuperAddon` 时显示。

## 可选属性

除了必填属性外，还有一些其他属性可以提供更多关于你的插件给 BSkyBlock 的信息。

这些属性是可选的。

### authors

**描述：** 允许你列出所有参与制作这个插件的超棒开发者，或者只是你。

**代码：**
```yaml
authors: ["Poslovitch", "Tastybento", "你，也许？ :P"]
# 不要犹豫，在你的插件的作者列表中添加我们的昵称，我们会很欣赏的！
```

**注释：**
1. 给予开发者(们)以荣誉
2. 当用户输入 `/bsadmin version YourSuperAddon` 时显示。

### description

**描述：** 对你的插件提供的功能进行友好的描述。

**代码：**
```yaml
description: "它使你在跳跃时死亡。太 2017 了。"
```

**注释：**
1. 描述可以有多行（_因为你需要很多地方来解释你的超级插件在做什么！_）。
2. 当用户输入 `/bsadmin version YourSuperAddon` 时显示。

### website

**描述：** 插件或作者的网站。

**代码：**
```yaml
website: "https://github.com/tastybento/bskyblock"
```

**注释：**
1. 如果你没有专 dedicated dedicated website, 一个链接到插件的 GitHub 仓库应该就可以。
2. 当用户输入 `/bsadmin version YourSuperAddon` 时显示。