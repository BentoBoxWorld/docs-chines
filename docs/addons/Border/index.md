# Border

**Border** 可以在玩家无法通过的岛屿周围创建并显示边界。
边界可以是:

- 原版的世界边界
- 一个自定义边界,当玩家靠近时会显示(可以在配置中设置视觉效果)。

由 [tastybento](https://github.com/tastybento) 创建和维护。

{{ addon_description("Border") }}

## 安装

1. 重启服务器(启用插件并生成 `config.yml` 文件)
2. 将插件 jar 文件放入 `plugins/BentoBox/addons` 文件夹
3. 在 `config.yml` 中自定义设置(可选) 
4. 重启服务器以应用新设置

## 命令

!!! tip
    `[player_command]` 是一个根据你运行的游戏模式而不同的命令。
    游戏模式的 `config.yml` 文件包含允许你修改此值的设置。
    例如,在 BSkyBlock 中,默认的 `[player_command]` 是 `island`。

### border
**命令**: `/[player command] border`
**描述**: 打开/关闭边界。
**权限**: `[gamemode].border.toggle`。默认: `op`。 
**注意**: 自 Version 3.0.0 起需要权限。

### border type {...}  
**命令**: `/[player command] border type {barrier | vanilla}`
**描述**: 设置边界类型。
**权限**: `[gamemode].border.set-type`。默认: `true`。
**示例**: `/[player command] border type barrier`

!!! tip
    `[gamemode]` 是一个根据你运行的游戏模式而不同的前缀。
    前缀是游戏模式的小写名称,即如果你使用 BSkyBlock,前缀就是 `bskyblock`。
    类似地,如果你使用 AcidIsland,前缀就是 `acidisland`。

## 配置

`config.yml` 文件包含设置。
除非明确说明,否则默认值通常就是示例值。

### 禁用游戏模式 
你可以使用此设置禁用插件。
默认情况下,Border 将在 BentoBox 服务器上的所有游戏模式世界中运行。

你可以通过在新行的开头写上 `-` 并接上游戏模式的名称来禁用它。
示例禁用 BSkyBlock:

```yml
disabled-gamemodes:
  - BSkyBlock  
```

默认值:

```yml
disabled-gamemodes: []
```

### 返回传送
控制如果玩家设法穿过边界(例如在同一个世界传送),是否应将他们传送回他们的岛屿。

如果你希望玩家被传送回来,请设置为 `true`。

**警告**: 如果你将此值设置为 `false`,同时将 `use-barrier-blocks` 设置为 `false`,玩家将能够直接穿过边界。

```yml
return-teleport: true
```

!!! tip
    如果你想 **只用此插件来显示** 玩家的边界,请使用以下设置:
    ```yml
    use-barrier-blocks: false
    return-teleport: false 
    ```

### 使用屏障方块
仅适用于 **不** 使用原版边界类型的玩家。

- `true`: 边界将由屏障方块组成。
- `false`: 不会有基于屏障方块的边界。这意味着当离开岛屿时,玩家是否被传送回去取决于 `return-teleport` 设置。

```yml 
use-barrier-blocks: true
```

### 默认边界行为
如果玩家拥有适当的权限,他们可以使用命令打开和关闭边界。
此设置将默认值设置为打开或关闭;将其设置为 `true` 以默认打开。

```yml
show-by-default: true  
```

### 显示最大保护范围边界
仅适用于 **不** 使用原版边界类型的玩家。

设置为 `true` 以在最大保护范围显示屏障(🚫)粒子。
这对于像 Boxed 这样玩家的保护区域可以移动的游戏模式很有用。

请注意,这些 **不是屏障方块**,而是 _粒子_,所以"空气"只是 _看起来像_ 它们。

```yml
show-max-border: true
```

### 显示粒子
启用/禁用插件显示的所有类型的墙粒子(边界和最大保护范围粒子)。

如果你不想显示 **任何** 墙粒子,请设置为 `false`。

```
show-particles: true  
```

## 翻译

{{ translations(3896, ["cs", "it", "lv", "fr", "de", "hu", "id", "zh-TW", "ko", "pl", "ru", "es", "vi", "zh-CN", "hr", "ja", "pt", "ro", "tr", "uk"]) }}

## 来源
想要贡献?在 [GitHub](https://github.com/BentoBoxWorld/docs/blob/master/docs/addons/Border/) 上查看本文档的源代码。