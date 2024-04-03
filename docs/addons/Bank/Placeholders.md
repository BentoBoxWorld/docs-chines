# 介绍
请阅读[占位符页面](../../../BentoBox/Placeholders)。
# 占位符
## 通用占位符
这些占位符在所有当前可用的游戏模式中都可用([BSkyBlock](../../../gamemodes/BSkyBlock/Placeholders)、[AcidIsland](../../../gamemodes/AcidIsland/Placeholders)、[CaveBlock](../../../gamemodes/CaveBlock/Placeholders)、[SkyGrid](../../../gamemodes/SkyGrid/Placeholders)、[AOneBlock](../../../gamemodes/AOneBlock/Placeholders))。
可用占位符列表
| 占位符 | 描述 | Bank 版本 |
|-------------------------------------------------------|--------------------------------------------------------------------------------|-----------|
| %Bank_[gamemode]_island_balance% | 玩家岛屿余额,由 Vault 格式化 | 1.1.0 |
| %Bank_[gamemode]_visited_island_balance% | 玩家所站岛屿的余额,由 Vault 格式化| 1.1.0 |
| %Bank_[gamemode]_island_balance_number% | 玩家岛屿余额 - 无格式化。原始值。| 1.4.0 |
| %Bank_[gamemode]_visited_island_balance_number% | 玩家所站岛屿的余额 - 无格式化。原始值。| 1.4.0 |
| %Bank_[gamemode]_island_balance_formatted% | 玩家岛屿格式化后的余额,例如 1.5M | 1.1.1 |
| %Bank_[gamemode]_visited_island_balance_formatted% | 玩家所站岛屿格式化后的余额。例如 1.2k | 1.1.0 |
| %Bank_[gamemode]_top_value_#RANK#% | 排行榜上第#RANK#名的岛屿余额 | 1.1.0 |
| %Bank_[gamemode]_top_name_#RANK#% | 排行榜上第#RANK#名岛屿的所有者名字 | 1.1.0 |
注意:#RANK#是介于1和Bank的config.yml中number-of-ranks设置之间的数字。
## 使用示例
### 在 BSkyBlock 中显示前10名
1. %Bank_bskyblock_top_name_1% 的岛屿余额:%Bank_bskyblock_top_value_1%
2. %Bank_bskyblock_top_name_2% 的岛屿余额:%Bank_bskyblock_top_value_2%
3. %Bank_bskyblock_top_name_3% 的岛屿余额:%Bank_bskyblock_top_value_3%
4. %Bank_bskyblock_top_name_4% 的岛屿余额:%Bank_bskyblock_top_value_4%
5. %Bank_bskyblock_top_name_5% 的岛屿余额:%Bank_bskyblock_top_value_5%
6. %Bank_bskyblock_top_name_6% 的岛屿余额:%Bank_bskyblock_top_value_6%
7. %Bank_bskyblock_top_name_7% 的岛屿余额:%Bank_bskyblock_top_value_7%
8. %Bank_bskyblock_top_name_8% 的岛屿余额:%Bank_bskyblock_top_value_8%
9. %Bank_bskyblock_top_name_9% 的岛屿余额:%Bank_bskyblock_top_value_9%
10. %Bank_bskyblock_top_name_10% 的岛屿余额:%Bank_bskyblock_top_value_10%