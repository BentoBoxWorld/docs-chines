# AcidIsland 管理员命令

| 命令 | 描述 | 权限 |
| --- | --- | --- |
| `/acid` | 管理员命令 | `acidisland.island` |
| `/acid add <owner> <player>` | 将玩家添加到所有者的团队 | `acidisland.mod.register` |
| `/acid challenges <player>` | 访问挑战管理员命令 | `acidisland.admin.challenges` |
| `/acid deaths` | 编辑玩家的死亡次数 |  |
| `/acid deaths reset <player>` | 重置玩家的死亡次数 |  |
| `/acid deaths set <player> <deaths>` | 设置玩家的死亡次数 |  |
| `/acid delete` | 删除一个玩家的岛屿 | `acidisland.admin.delete` |
| `/acid disband <owner>` | 解散所有者的团队 |  |
| `/acid getrank <player>` | 获取玩家在其岛屿上的等级 |  |
| `/acid info <player>` | 获取你所在位置或玩家岛屿的信息 | `acidisland.mod.info` |
| `/acid kick <team player>` | 将玩家从团队中踢出 | `acidisland.island.expel` |
| `/acid range` | AcidIsland 范围命令 |  |
| `/acid range display` | 显示/隐藏岛屿范围指示器 |  |
| `/acid range reset <player>` | 将岛屿保护范围重置为世界默认值 |  |
| `/acid range set <player> <range>` | 设置岛屿保护范围 |  |
| `/acid register <player>` | 注册玩家到你所在的无主岛屿 | `acidisland.admin.register` |
| `/acid reload` | 重新加载插件 | `acidisland.admin.reload` |
| `/acid reset` | 重置命令 | `acidisland.mod.resethome` |
| `/acid blueprint` | 操纵方案 |  |
| `/acid blueprint copy [air]` | 复制由 pos1 和 pos2 设置的剪贴板，可选空气块 |  |
| `/acid blueprint load <blueprint name>` | 将方案加载到剪贴板 |  |
| `/acid blueprint origin` | 将方案的原点设置为你的位置 |  |
| `/acid blueprint paste` | 将剪贴板粘贴到你的位置 |  |
| `/acid blueprint pos1` | 设置立方体剪贴板的第一个角落 |  |
| `/acid blueprint pos2` | 设置立方体剪贴板的第二个角落 |  |
| `/acid blueprint save <blueprint name>` | 保存复制的剪贴板 |  |
| `/acid setrank <player> <rank>` | 设置玩家在其岛屿上的等级 |  |
| `/acid tp <player>` | 传送到玩家的岛屿 | `acidisland.mod.tp` |
| `/acid tpnether <player>` | 传送到玩家的下界岛屿 | `acidisland.mod.tp` |
| `/acid tpend <player>` | 传送到玩家的末地岛屿 | `acidisland.mod.tp` |
| `/acid unregister <owner>` | 将所有者从岛屿上注销，但保留岛屿方块 | `acidisland.admin.unregister` |
| `/acid version` | 显示 BentoBox 和插件版本 | `acidisland.mod.info` |
| `/acid why <player>` | 切换调试开/关，了解某事不工作的原因 |  |

# AcidIsland 玩家命令

| 命令 | 描述 | 权限 |
| --- | --- | --- |
| `/ai` | 将玩家传送到他们的 AcidIsland | `acidisland.island` |
| `/ai about` | 关于这个插件 | `acidisland.island` |
| `/ai ban <player

>` | 禁止玩家进入你的岛屿 | `acidisland.island.ban` |
| `/ai banlist` | 列出被禁止的玩家 | `acidisland.island.ban` |
| `/ai coop <player>` | 使玩家在你的岛屿上成为合作伙伴等级 | `acidisland.island.team.coop` |
| `/ai create` | 创建一个岛屿 | `acidisland.island.create` |
| `/ai go` | 传送到你的岛屿 | `acidisland.island.home` |
| `/ai info [player]` | 计算你的岛屿等级或显示 [player] 的等级 | `acidisland.island.info` |
| `/ai language` | 选择语言 | `acidisland.island.language` |
| `/ai reset` | 重启你的岛屿并移除旧的 | `acidisland.island.reset` |
| `/ai resetname` | 重置你的岛屿名称 | `acidisland.mod.resetname` |
| `/ai sethome` | 设置你的家传送点 | `acidisland.island.home` |
| `/ai setname <name>` | 为你的岛屿设置一个名称 | `acidisland.island.name` |
| `/ai settings` | 显示 AcidIsland 设置菜单 | `acidisland.island.settings` |
| `/ai team` | 显示团队命令 | `acidisland.island.team` |
| `/ai team accept` | 接受邀请 | `acidisland.island.team` |
| `/ai team coop <player>` | 使玩家在你的岛屿上成为合作伙伴等级 | `acidisland.island.team.coop` |
| `/ai team demote <player>` | 在你的岛屿上将玩家降级 | `acidisland.island.team` |
| `/ai team invite` | 邀请玩家加入你的岛屿 | `acidisland.island.team` |
| `/ai team kick <player>` | 从你的岛屿中移除一个成员 | `acidisland.island.expel` |
| `/ai team leave` | 离开你的岛屿 | `acidisland.island.team` |
| `/ai team promote <player>` | 在你的岛屿上将玩家提升一个等级 | `acidisland.island.team` |
| `/ai team reject` | 拒绝邀请 | `acidisland.mod.team.team` |
| `/ai team setowner <player>` | 将你的岛屿所有权转让给一名成员 | `acidisland.admin.register` |
| `/ai team trust <player>` | 在你的岛屿上给予玩家受信任的等级 | `acidisland.island.team.trust` |
| `/ai team uncoop <player>` | 移除玩家的合作伙伴等级 | `acidisland.island.team` |
| `/ai team untrust <player>` | 移除玩家的受信任等级 | `acidisland.island.team.trust` |
| `/ai trust <player>` | 在你的岛屿上给予玩家受信任的等级 | `acidisland.island.team.trust` |
| `/ai unban <player>` | 解禁你的岛屿上的玩家 | `acidisland.island.ban` |
| `/ai untrust <player>` | 移除玩家的受信任等级 | `acidisland.island.team.trust` |
| `/ai warp <name>` | 传送到玩家的传送标志 | `acidisland.island.home` |
| `/ai warps` | 打开传送点面板 | `acidisland.island.home` |