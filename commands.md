#本文列出了 SA-MP 所有内置于客户端的指令、samp.cfg 中的配置、 RCON 指令，以及这些指令的作用。
#全文将使用简体中文。有稍作修改。
#感谢 OPEN.MP 的文档，使我能够找到完整的指令与描述。

# 客户端内的指令
/quit（/q）
这条指令的作用不言而喻，退出游戏。也可以使用 /q，因为它是完全相同的指令，只是更短更快捷而已。

/save
/save 很可能是最常用的默认指令，也可能是最有用的指令。键入 /save 后，当前位置会保存到你的电脑用户文件目录下的 savedpositions.txt。在 Android 的 SA-MP 客户端，通常文件将会保存至 /storage/emulated/primary(取决于您的用户名，通常是 0 )/Android/data/( SA-MP 客户端 APK 的软件包名) /files/SAMP/savedpositions.txt。您也可以在脚本中使用它。

/rs
/rs（Raw Save）与 /save 类似，但它只将当前位置和朝向角度保存到电脑用户文件目录下的 rawpositions.txt。不会保存额外的信息，如等级和武器。

/interior
该指令与 /save 一样重要，它在聊天栏中显示你当前的内部情况。

/vw
该指令与 /save 一样重要，它在聊天栏中显示您当前的虚拟世界。

/fpslimit
该指令设置游戏的FPS上限。数值越高，游戏越流畅。如果在 GTA San Andreas 的 画面设置（Graphics Options）中关闭了帧数限制（Frame Limiter），则该指令无效。帧数限制可设置在 20 到 90 之间。
/pagesize
/pagesize 用于选择要显示的聊天行数。行数可从 10 行到 20 行。默认值为 10 。

/headmove
该指令将启用/禁用玩家的头部移动，但它是在本地处理的，因此其他玩家仍会看到你的头部移动。

/timestamp
该指令将显示或隐藏聊天框中所有信息旁边的时间。显示的时间是您电脑的时间，而非服务器时间。
开启后的效果：
[11:45:14]Player_1(0):test
/dl
DL 指调试标签。该指令可切换车辆上的调试标签，显示车辆 ID、模型、载具耐久值、是否预加载、与玩家的距离、拖车、可用座位、当前位置和生成位置。

/nametagstatus
该指令在 0.3x 中添加。启用后（默认情况下），玩家将在挂机的玩家标签旁看到一个小沙漏图标。这包括最小化游戏 、暂停菜单（Esc）、失去连接（游戏崩溃 / 连接超时）以及截图时冻结游戏超过 3 秒。

/mem
显示当前内存使用量。(不过通常只会显示 128 MB）。

/audiomsg
启用/禁用流式音频传输 URL 到客户端时显示的信息。下面为示例：
[Audio Stream]http://127.0.0.1/Audio.mp3

/fontsize
更改用户界面（聊天、对话框等）的字体大小。有效字体大小为 -3 至 5 。

/ctd
此指令在 SA-MP 0.3.7-RC2 添加。它可在客户端调试播放器摄像头目标。

/hudscalefix
此指令在 SA-MP 0.3.7 R3 添加。启用/禁用雷达比例修复，以便于游戏的雷达在宽屏分辨率下可以更好地缩放（即不再有“egg of finding”）。

/rcon
直接与服务器交互指令。该指令用于执行 RCON 指令。RCON 是内置的 SAMP 管理系统，RCON 是远程控制（Remote Control）的缩写。如需登录 RCON ，请输入/rcon login [密码]

# sa-mp.cfg 配置文件
#sa-mp.cfg 是一个客户端配置文件，允许您更改与 SA-MP 相关的设置。此文件位于你的 Windows 用户帐户下的“Documents\ GTA San Andreas User Files\ SAMP”文件夹中。可以使用文本编辑器（如 Windows 自带的记事本）编辑此文件。
pagesize
这允许玩家设置聊天窗口中显示的行数。可以设置为 10 到 20 行。默认为 10 行。可以使用客户端 /pagesize 指令在游戏中设置此选项。

fpslimit
当 GTA:SA 游戏菜单中的帧数限制（Frame Limiter）选项启用时，这允许玩家设置特定的 FPS 限制。可接受的值为 20 到 90 。SA-MP 设置的默认值为 50。可以使用客户端的 /fpslimit 指令在游戏中更改此选项。

disableheadmove
此选项控制玩家的头部是否朝他们注视的方向移动。1 表示禁用头部移动，0 表示启用。可以使用客户端的 /headmove 指令在游戏中切换此选项。

timestamp
这允许玩家在聊天消息旁边显示本地时间戳。1 启用时间戳，0 禁用时间戳。这可以在游戏中使用客户端的 /timestamp 指令切换。

ime
控制聊天窗口输入是否支持输入法文本编辑和语言切换。1 表示启用 IME，0 表示禁用。

multicore
切换 SA-MP 客户端运行时是否使用多个 CPU 核心。默认值为 1（确实使用多个 CPU 核心）。如果遇到鼠标问题，请设置为 0。

directmode
这允许有聊天文本绘制问题的玩家使用较慢的直接屏幕文本渲染模式。0 为禁用，1 为启用。

audiomsgoff
如果将此选项设置为 1，则当服务器播放流式音频时，聊天窗口中不会显示任何“Audio Stream：[URL]”消息。可以使用客户端 /audiomsg 指令在游戏中切换此选项。

audioproxyoff
如果此选项设置为 1，并且 Windows Internet 选项中设置了代理服务器，则在 SA-MP 中播放流式音频时将不会使用代理。

nonametagstatus
如果将此选项设置为 0，玩家在暂停游戏时将在其他玩家的姓名标签旁边看到一个沙漏图标。默认情况下启用该选项 (0)。可以使用客户端 /nametagstatus 指令在游戏中更改此选项。

fontface
允许您更改聊天、对话框（Dialog）和积分板（Scoreboard）的字体。例如 fontface="Comic Sans MS"。**未得到官方支持，并且可能会导致问题。**

fontweight
此选项切换您的聊天字体是否为粗体。0 = 粗体（默认）和 1 = 正常。

#RCON 指令
#这些是拥有 RCON 的服务器所有者以及管理员可以使用的功能：（你无需输入[]符号，只是为了突出显示。)

/rcon cmdlist - 以列表形式显示RCON指令。

/rcon varlist - 显示当前服务器设置的一些变量列表。

/rcon exit - 关闭服务器。

/rcon echo [text] - 在服务器控制台（不是游戏中的客户端控制台）中显示[text]。

/rcon hostname [name] - 更改主机名文本（例如：/rcon hostname Dedicated Server）。

/rcon gamemodetext [name] - 更改游戏模式文本（例如：/rcon gamemodetext Example gamemode）。

/rcon mapname [name] - 更改地图名称文本（例如：/rcon mapname San Andreas）。

/rcon exec [filename] - 执行包含服务器 cfg 的文件（例如：/rcon exec test.cfg）。

/rcon kick [ID] - 踢出指定 ID 的玩家（例如：/rcon kick 1）。

/rcon ban [ID] - 封禁指定 ID 的玩家（例如：/rcon ban 1）。

/rcon changemode [mode] - 该指令将把当前游戏模式改为指定的游戏模式（例如：如果你想玩 dm3：/rcon changemode dm3）。

/rcon gmx - 将在 server.cfg 中加载下一个游戏模式。

/rcon reloadbans - 重新加载存储禁止 IP 地址的 samp.ban。应在解除封禁和 IP地址 之后使用。

/rcon reloadlog - 清除 server_log.txt。对任何内容都没有影响。

/rcon say - 在客户端控制台向玩家显示一条信息（例如：/rcon say 123456；之后聊天栏将会显示 * Admin: 123456）。

/rcon players - 显示服务器中的玩家（昵称 IP地址 和 ping）。

/rcon banip [IP] - 封禁指定的一个 IP 。（例如：/rcon banip 19.19.8.1）

/rcon unbanip [IP] - 解除对指定 IP 的封禁（例如：/rcon unbanip 10.0.0.1）。

/rcon gravity - 更改重力（例如：/rcon gravity 0.008）。

/rcon weather [ID] - 更改天气（例如：/rcon weather 8）。

/rcon loadfs - 载入指定的过滤脚本（例如：/rcon loadfs scriptfs）。

/rcon weburl [server url] - 更改主列表/SA-MP 客户端中的服务器 URL。

/rcon unloadfs - 卸载指定的过滤脚本（例如：/rcon unloadfs scriptfs）。

/rcon reloadfs - 重新加载指定的过滤脚本（例如：/rcon reloadfs scriptfs）。

/rcon rcon_password [PASSWORD] - 更改 RCON 密码。

/rcon password [password] - 设置或重置服务器密码。
/rcon playertimeout [limit m/s] - 更改玩家不发送任何数据包时的超时时间（以毫秒(ms)为单位）。(默认值 1000）

/rcon language [language] - 更改服务器语言（例如：/rcon language Chinese）。显示在服务器的"Language"中。

#***以下指令仅适用于 0.3z R2 及以上版本。
/rcon messageslimit [count] - 更改客户端每秒向服务器发送的信息数量。(默认为 500）
/rcon ackslimit [count] - 更改 acks（Acknowledge character,即确认字符）的限制（默认为 1000）（自 0.3z R2-2 起，默认限制为 3000）
/rcon messageholelimit [count] - 更改消息洞的限制（0.3z R1 中也可用）（默认为 3000）
***messagehole***这是一种低级协议（RakNet），在 2014 年时被用来攻击 SA-MP 服务器。
基本上，客户端/玩家会发送大量伪造的数据包序列 ID，让服务器认为由于数据包丢失，网络上丢失了大量数据包/信息。
协议栈会尝试通过分配空间来恢复丢失的数据包，并等待客户端重新发送丢失的数据包。这将耗费大量资源，反复进行最终会导致服务器滞后甚至崩溃。
玩家可以报告的丢失信息数量没有硬性限制。每个丢失的数据包块都被视为一个 "漏洞"（hole）。在 0.3x R2 中 SA-MP 的开发者们曾尝试修复这个问题，但限制是硬编码的 1000；有时玩家会被错误地检测到试图对服务器进行 DoS，因为存在较大的信息漏洞。
现在，服务器可以指定丢失数据包漏洞的大小。但在大多数情况下，默认限制应该没有问题，大多数服务器的所有者们不必为此担心。***
