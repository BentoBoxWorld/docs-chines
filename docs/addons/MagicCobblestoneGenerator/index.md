# 魔法圆石发生器

**魔法圆石发生器**将平凡无聊的圆石发生器变成了一个棒极了的、可配置的方块来源！

由[BONNe](https://github.com/BONNe)创建和维护。

{{ addon_description("MagicCobblestoneGenerator") }}

## 安装

1. 将插件jar文件放入BentoBox插件的addons文件夹中
2. 重启服务器
3. 运行`/[admincmd] generator`命令来配置插件

## 配置

默认情况下，插件试图从模板文件中导入所有数据，以简化首次设置。许多插件设置在Admin GUI中公开，然而，有些设置不是。
最新的配置选项及其详细解释可以在[这里](https://github.com/BentoBoxWorld/MagicCobblestoneGenerator/blob/develop/src/main/resources/config.yml)找到。

模板文件主要是为那些不喜欢使用游戏内编辑GUI的用户准备的。然而，模板文件在每次更改时不会自动导入。需要通过命令或Admin GUI导入。

??? question "模板文件结构"
    ```
    # 开始所有生成器等级的列表。
    tiers:
      # 生成器的唯一ID。用于内部存储和访问每个生成器数据。
      generator_unique_id: 
        # 用户的显示名称。支持颜色代码。
        # 默认值: 生成器唯一ID去掉下划线
        name: "Something fancy"
        # 说明文字信息。支持颜色代码。
        # 可以通过用[]替换一切来定义为空。
        # 默认值: []
        description: -|
          第一行说明信息
          &2第二行说明信息
        # GUI中使用的图标。数字在末尾允许指定项目的堆叠大小。
        # 默认值: Paper.
        icon: "PAPER:1"
        # 生成器类型: COBBLESTONE, STONE 或 BASALT。自解释。
        # 默认值: COBBLESTONE
        type: COBBLESTONE
        # 指示生成器是否为默认生成器。默认生成器忽略要求部分。
        # 对每种生成器类型只能有一个默认生成器。
        # 默认值: false
        default: false
        # 用户选择激活的生成器。
        # 优先级指示如果多个生成器满足要求，
        # 将使用哪个生成器。
        # 默认值: 1
        priority: 1
        # 这里可以定义几个要求。
        requirements:
          # 可以定义生成器工作所需的最小岛屿等级。需要等级插件。
          # 默认值: 0
          island-level: 10
          # 列出用户选择此生成器所需的权限列表。
          # 默认值: []
          required-permissions: []
          # 列出生成器工作所需的生物群系列表。
          # 空意味着没有限制生物群系生成器工作。
          # 默认值: []。
          required-biomes: []
          # 购买此生成器的费用。需要Vault和任何经济插件。
          # 通过在生成器视图GUI中点击购买图标来实现。
          # 默认值: 0
          purchase-cost: 5.0
        # 激活当前生成器等级的费用。需要Vault和任何经济插件。
        # 只有在生成器之间主动切换时才会支付。
        # 默认值: 0。
        activation-cost: 0.0
        # 材料及其几率。请使用实际的方块。
        # 几率支持任何正数，包括双精度值。
        # 最终所有内容将被规范化。
        # 默认值: []
        blocks:
          FIRST_BLOCK_NAME_ID: NUMBER
          SECOND_BLOCK_NAME_ID: NUMBER
        # 在

方块生成时有机会掉落的宝藏。
        # 仅在生成时，而非方块破坏时。
        # 默认值: []
        treasure:
          # 从0到1的几率。0 - 不可能获得宝藏。
          # 默认值: 0
          chance: 0.001
          # 可以掉落的材料。适用于与方块部分相同的规则。
          # 默认值: []
          material:
            FIRST_BLOCK_NAME_ID: NUMBER
            SECOND_BLOCK_NAME_ID: NUMBER
          # 掉落项目的最大数量。
          # 将从1到定义的数量之间。
          # 默认值: 1
          amount: 1
    
    # 开始所有套餐的列表
    bundles:
      # 套餐id
      bundle_unique_id:
        # 用户的显示名称
        name: "Something fancy"
        # 说明文字信息。支持颜色代码。
        # 可以通过用[]替换一切来定义为空。
        # 默认值: []
        description: -|
          第一行说明信息
          &2第二行说明信息
        # GUI中使用的图标。数字在末尾允许指定项目的堆叠大小。
        # 默认值: Paper.
        icon: "PAPER:1"
        # 套餐将工作有访问权限的生成器列表。
        generators:
          - generator_id_1
          - generator_id_2
    ```

## 命令

!!! 小贴士
    `[player_command]` 和 `[admin_command]` 是根据你运行的游戏模式而不同的命令。
    游戏模式的`config.yml`文件包含允许你修改这些值的选项。
    例如，在BSkyBlock上，默认的`[player_command]`是`island`，默认的`[admin_command]`是`bsbadmin`。
    注意，这个插件允许在插件`config.yml`文件中更改玩家命令别名。

=== "玩家命令"
    - `/[player_command] generator`：访问生成器选择GUI。
    - `/[player_command] generator view <generator>`：访问特定生成器的详细视图。
    - `/[player_command] generator activate <generator> [false]`：允许激活（或停用）特定生成器。
    - `/[player_command] generator buy <generator>`：允许购买特定生成器。

=== "管理员命令"
    - `/[admin_command] generator`：访问插件的管理员GUI
    - `/[admin_command] generator import`：导入默认模板文件 - `/plugins/BentoBox/addons/MagicCobblestoneGenerator/generatorTemplate.yml`。
    - `/[admin_command] generator database import <file>`：能够导入导出的数据库<file>。
    - `/[admin_command] generator database export <file>`：能够将数据库导出到保存在`/plugins/BentoBox/addons/MagicCobblestoneGenerator/`文件夹中的<file>。
    - `/[admin_command] generator why <player>`：一个调试命令，允许为每个玩家找到生成器问题。

## 权限

!!! 小贴士
    `[gamemode]` 是一个根据你运行的游戏模式而不同的前缀。
    前缀是游戏模式的小写名称，即如果你使用BSkyBlock，前缀是`bskyblock`。
    类似地，如果你使用AcidIsland，前缀是`acidisland`。

=== "玩家权限"
    - `[gamemode].stone-generator` - 让玩家使用`/[player_command] generator`命令及其子命令。
    - `[gamemode].stone-generator.active-generators.3` - 设置岛屿所有者可以拥有的最大活跃生成器数量。3可以被任何正整数替换。这只是一个例子。
    - `[gamemode].stone-generator.max-range.30` - 设置生成器继续

工作的最大距离。30可以被任何正整数替换。这只是一个例子。
    - `[gamemode].stone-generator.bundle.[bundle_id]` - 指定将用于用户拥有的岛屿的套餐。

=== "管理员权限"
    - `[gamemode].admin.stone-generator` - 让玩家使用`/[admin_command] generator`命令及其子命令。
    - `[gamemode].admin.stone-generator.why` - 让玩家使用调试命令`/[admin_command] why generator <player>`。
    - `[gamemode].admin.stone-generator.database` - 让玩家使用`/[admin_command] generator database`命令及其子命令。
    
??? question "缺少什么？"
    你可以在这个插件的[addon.yml](https://github.com/BentoBoxWorld/MagicCobblestoneGenerator/blob/develop/src/main/resources/addon.yml)文件中找到权限的综合列表。  
    如果下面的列表确实缺少了什么，请告诉我们！


## 占位符

{{ placeholders_source(source="MagicCobblestoneGenerator") }}


## 常见问题解答

??? question "你能添加功能X吗？"
    请在[这里](https://github.com/BentoBoxWorld/MagicCobblestoneGenerator/issues)添加。

??? question "如何添加新的生成器等级？"
    目前，插件支持3种添加新生成器的方式：
    
    - 通过使用游戏内GUI，可通过`/[admin] generator`命令访问。
    - 通过向模板文件添加生成器。
    - 通过向导出的数据库文件添加生成器。

??? question "我在模板/数据库文件中添加了生成器，但它在游戏中不显示。"
    为了更容易地配置多个游戏模式，生成器存储在内部数据库中。编辑模板或数据库文件后，您需要将它们导入到内存中。您可以通过点击Admin GUI中的`导入模板`或`导入数据库`按钮来完成。

??? question "我有一个生成器显示在Admin GUI中，但玩家看不到它。"
    最有可能是由于“部署”状态。为了避免在管理员添加它们时玩家开始激活生成器的问题，生成器是未部署的，没有人可以使用它们。您可以通过编辑Admin GUI中的生成器并点击编辑生成器GUI中的开关来激活它们。

??? question "什么是宝藏？"
    宝藏是在生成方块时掉落的东西。它允许为每个生成器提供额外的自定义。

??? question "什么是套餐？"
    套餐是一项功能，允许为每个岛屿提供更多的自定义体验。如果岛屿分配了套餐，那么该岛屿上的玩家将只能使用该套餐中的生成器。

??? question "我可以禁用在生成器描述中显示所需权限吗？"
    是的，插件为显示每个生成器提供了许多自定义选项。它位于locales文件中：