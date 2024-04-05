# 命令

所有的命令与其他游戏模式（如BSkyBlock）相同。

# Boxed 管理员命令（别名：/boxadmin）
| 命令 | 描述 | 权限 |
| --- | --- | --- |
| **/boxadmin** | 显示所有 Boxed 命令 | boxed.island |
| **/boxadmin add <owner> <player>** | 将玩家添加到所有者的团队中 |  |
| **/boxadmin biomes** | 生物群系插件管理员主命令。为玩家打开管理员 GUI |  |
| **/boxadmin challenges** | 访问 /boxadmin 挑战管理员命令 | boxed.admin.challenges |
| **/boxadmin deaths** | 编辑玩家死亡次数 |  |
| **/boxadmin delete** | 删除一个玩家的岛屿 | boxed.admin.delete |
| **/boxadmin disband <owner>** | 解散所有者的团队 | boxed.mod.bypassprotect |
| **/boxadmin getrank <player>** | 获取玩家在其岛屿上的等级 |  |
| **/boxadmin info <player>** | 获取你所在位置或玩家岛屿的信息 | boxed.mod.info |
| **/boxadmin kick <team player>** | 将一个玩家从团队中踢出 | boxed.mod.bypassexpel |
| **/boxadmin level <player>** | 为玩家计算岛屿等级 |  |
| **/boxadmin range** | 管理员岛屿范围命令 |  |
| **/boxadmin register <player>** | 将玩家注册到你所在的无主岛屿上 | boxed.admin.register |
| **/boxadmin reload** | 重载插件 | boxed.admin.reload |
| **/boxadmin reset** | commands.admin.resets.reset.description | boxed.admin.settingsreset |
| **/boxadmin bp** | 操作蓝图 |  |
| **/boxadmin bp copy [air]** | 复制由 pos1 和 pos2 设置的剪贴板，并可选复制空气方块 |  |
| **/boxadmin bp load <bp name>** | 将 bp 加载到剪贴板中 |  |
| **/boxadmin bp origin** | 将 bp 的原点设置为你的位置 |  |
| **/boxadmin bp paste** | 将剪贴板粘贴到你的位置 |  |
| **/boxadmin bp pos1** | 设置长方体剪贴板的第一个角 |  |
| **/boxadmin bp pos2** | 设置长方体剪贴板的第二个角 |  |
| **/boxadmin bp save <bp name>** | 保存已复制的剪贴板 |  |
| **/boxadmin setowner <player>** | 将岛屿所有权转移给玩家 | boxed.admin.register |
| **/boxadmin setrank <player> <rank>** | 设置玩家在其岛屿上的等级 |  |
| **/boxadmin setspawn** | commands.admin.setspawn.description | boxed.admin.setspawn |
| **/boxadmin top** | 显示前十名列表 |  |
| **/boxadmin tp <player>** | 传送到一个玩家的岛屿 | boxed.mod.tp |
| **/boxadmin tpend <player>** | 传送到一个玩家的岛屿 | boxed.mod.tp |
| **/boxadmin tpnether <player>** | 传送到一个玩家的岛屿 | boxed.mod.tp |
| **/boxadmin unregister <owner>** | 取消注册岛屿所有者，但保留岛屿方块 | boxed.admin.unregister |
| **/boxadmin why <player>** | 切换控制台保护调试报告 |  |

# Boxed 岛屿玩家命令（别名：/box 或 /boxed）
| 命令 | 描述 | 权限 |
| --- | --- | --- |
| **/box** | 主玩家命令 | boxed.island |
| **/box ban <player

>** | 禁止玩家进入你的岛屿 | boxed.island.ban |
| **/box banlist** | 列出被禁止的玩家 | boxed.island.ban |
| **/box biomes** | 生物群系插件主命令，打开生物群系更改 GUI |  |
| **/box challenges [Level]** | 允许玩家使用 /box challenges 命令 | boxed.challenges |
| **/box create** | 创建一个岛屿 | boxed.island.create |
| **/box go** | 传送你到你的岛屿 | boxed.island |
| **/box info <player>** | 显示你的岛屿或玩家岛屿的信息 | boxed.island.info |
| **/box language** | 选择语言 | boxed.island.language |
| **/box level [player]** | 计算你的岛屿等级或显示 [player] 的等级 |  |
| **/box reset** | 重启你的岛屿并移除旧的 | boxed.island.reset |
| **/box sethome** | 设置你的家传送点 | boxed.island.sethome |
| **/box setname <name>** | 为你的岛屿设置名称 | boxed.island.name |
| **/box settings** | 显示岛屿设置 | boxed.island.settings |
| **/box spawn** | 传送你到出生点 | boxed.island.home |
| **/box resetname** | 重置你的岛屿名称 | boxed.mod.resetname |
| **/box unban <player>** | 解禁一个玩家进入你的岛屿 | boxed.island.ban |
| **/box team** | 管理你的团队 | boxed.island.team |
| **/box team accept** | 接受邀请 | boxed.island.team |
| **/box team coop <player>** | 使一个玩家在你的岛屿上成为合作等级 | boxed.island.team.coop |
| **/box team demote <player>** | 在你的岛屿上降低一个玩家的等级 | boxed.island.team |
| **/box team leave** | 离开你的岛屿 | boxed.island.team |
| **/box team invite** | 邀请一个玩家加入你的岛屿 | boxed.island.team |
| **/box team kick <player>** | 从你的岛屿中移除一个成员 | boxed.island.expel |
| **/box team promote <player>** | 在你的岛屿上提升一个玩家的等级 | boxed.island.team |
| **/box team reject** | 拒绝邀请 | boxed.island.team |
| **/box team setowner <player>** | 将你的岛屿所有权转给一个成员 | boxed.island.team |
| **/box team trust <player>** | 在你的岛屿上给一个玩家信任等级 | boxed.island.team.trust |
| **/box top** | 显示十强 |  |
| **/box team uncoop <player>** | 移除一个玩家的合作等级 | boxed.island.team.coop |
| **/box team untrust <player>** | 移除一个玩家的信任等级 | boxed.island.team.trust |
| **/box warp <name>** | 传送到玩家的传送标志 |  |
| **/box warps** | 打开传送面板 |  |

## 岛屿设置（/box settings）
Boxed 的独特设置是确定谁可以通过投掷末影珍珠移动盒子。默认只有所有者可以。图标是堆肥桶。