## 介绍

**将 BentoBox 世界设置为服务器默认世界** 可以避免生成 **默认的原版世界**。

!!! 警告
    在这个分步示例/教程中，我们考虑你正在为 `BSkyBlock` 执行此操作。
    其他游戏模式的过程相同，但要 **注意世界的名称**！

## 准备工作

1. 整个过程需要在服务器 **关闭** 的情况下执行。
2. 通过删除原版世界（`world`、`world_nether`、`world_the_end`）的文件夹来删除它们。

![要删除的世界](https://user-images.githubusercontent.com/20014332/62977233-bebf1180-be1e-11e9-9ec8-ddcfd3352b13.png)

*高亮显示的文件夹是默认世界的文件夹。它们必须被删除。*

## server.properties

打开 `server.properties` 文件。

找到以下行：
```properties
level-name=world
```

将 `world` 替换为 BentoBox 世界的名称。它通常是 `[gamemode]_world`，其中 `[gamemode]` 是小写的游戏模式名称（例如 `bskyblock` 或 `caveblock`）。但是，它可以在游戏模式的 `config.yml` 文件中修改，所以请确保它是正确的。

为了简单起见，我们将期望世界名称保持不变和通用，因此是 `bskyblock_world`。

该行现在应如下所示：
```properties
level-name=bskyblock_world
```

## bukkit.yml

打开 `bukkit.yml` 文件：我们需要告诉 Bukkit 默认世界使用自定义生成器，**否则它会弄乱世界生成**。请注意，如果你想使用原版下界或末地，请不要在此文件中列出它们。

我们要添加的配置部分可能在你的 `bukkit.yml` 文件中还不存在，因此你需要创建它。有关该部分的更多详细信息，请参阅官方的 [Bukkit Wiki](https://bukkit.fandom.com/wiki/Bukkit.yml)。

将以下部分添加到你的文件中。列出的名称 **必须** 是世界的名称：
```yaml
worlds:
  bskyblock_world:
    generator: BentoBox
  bskyblock_world_nether:
    generator: BentoBox
  bskyblock_world_the_end:
    generator: BentoBox
```

如果你打算使用原版下界或末地，请不要列出它们。只需列出主世界。例如：
```yaml
worlds:
  bskyblock_world:
    generator: BentoBox
```
