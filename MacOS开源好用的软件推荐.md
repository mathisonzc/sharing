# MacOS开源好用的软件推荐

## GnuPG

1. 官网：https://www.gnupg.org/
2. 源码：https://github.com/gpg/gnupg
3. 下载地址：
4. 安装
    1. 下载：https://sourceforge.net/p/gpgosx/docu/Download/
    2. 默认安装
5. 概述
    1. PGP（Pretty Good Privacy，优良保密协议）
        1. OpenPGP（Open Pretty Good Privacy）：是GPG加密协议的**开放标准**版本
        2. GnuPG（GNU Privacy Guard）：是 GNU(自由软件)社区，对 OpenPGP 的RFC4880标准的**完整实现**。
    2. GunPG是一种命令行工具

## Copytranslator

1. 官网：https://copytranslator.gitee.io/
2. 官方文档：https://copytranslator.gitee.io/guide/
3. 源码地址：https://github.com/CopyTranslator/CopyTranslator
4. 下载地址：https://copytranslator.gitee.io/download/#%E4%B8%8B%E8%BD%BD
5. 概述
    1. 翻译文本
6. 安装
    1. 方式一：下载后直接安装
    2. ~~方式二：`brew install --cask copytranslator`~~
7. 配置文件
    1. `~/copytranslator/copytranslator.json`：用户配置
        1. `"listenClipboard": false`：禁止监听**系统剪切板**（不要开启 “监听剪切板”，剪切板上的信息，会泄漏个人敏感数据）
        2. `"drawer": false`：关闭侧边抽屉
    2. `~/copytranslator/shortcuts.json`：全局快捷键设置
        1. `"translateClipboard": "Control+Command+c"`：翻译**系统剪切板**的文本
    3. `~/copytranslator/localShortcuts.json`：局部快捷键设置（只能在焦点在copytranslator时使用）
    4. `~/copytranslator/styles.css`：样式设置
8. **动作**（相当于一个命令工具）
    1. 有两种用途
        1. 第一种：直接执行
            1. 命令输入：在原文窗口中输入
            2. 命令执行：`Control + p`
        2. 第二种：和快捷键绑定，通过快捷键，触发相应的**动作**
            1. 配置格式：`"{动作}": "{快捷键}"`
    2. 常用**动作**
        1. `translateClipboard`：翻译系统剪切板中文本
        2. `exit`：退出Copytranslator
        3. `selectionQuery`：翻译原文窗口中的选中文本
        4. `translate`：翻译原文窗口中的全部文本
        5. `copySource`：复制原文
        6. `copyResult`：复制译文
        7. `pasteResult`：粘贴译文
        8. `clear`：清空原文和译文
    3. 可用的快捷键：https://www.electronjs.org/docs/latest/api/accelerator
        1. `Control+Command+c`
        2. `Control+Command+Space`
9. OCR（Optical Character Recognition，光学字符识别）
    1. 作用：遇到无法复制的文字，可以使用截图翻译
    2. 原理：截图后，图片会保存在系统剪切板，Copytranslator对**系统剪切板**的图片使用OCR转为文字，再进行翻译
10. 聚合引擎
    1. 聚合物**查词引擎**：相当于**搜索引擎**（将句子在对应的引擎上查询，返回一个语法合适的句子）
        1. youdao
        2. bing（比较好用）
    2. 化合物**翻译引擎**：将聚合物**查词引擎**返回的结果，进行翻译（底部切换的**翻译引擎**）
        1. bing（比较好用）
        2. deepl
        3. tencent
        4. baidu
        5. google
        6. caiyun
        7. keyan
        8. baidu-domain
        9. youdao
        10. sogou

## Drawio

1. 源码：https://github.com/jgraph/drawio
2. 在线工具地址：https://app.diagrams.net/
3. 概述
    1. 一个开源的画图工具
4. 常规操作
    1. 自动变换已画图形的布局（比如 “垂直布局” -> “水平布局”）
        1. 选中多个有连接在一起的图形
        2. `上方工具栏 -> Arrange -> Layout -> {具体布局}` 
    2. 数学公式
        1. `上方工具栏 -> Extra -> Mathematical Typesetting`
        2. 使用 $$ a \div b $$
    3. 表格
        1. 选中已插入的表格
        2. `右侧工具栏 -> Arrange`：可以弹性增减 行和列 
    4. 图形插入高级用法（`上方工具栏 -> "+" 加号图标` ）
        1. Rectangle：矩形
        2. Ellipse：椭圆形
        3. Rhombus：菱形
        4. Text：文本
        5. Link：链接
        6. Shape：图形（通过xml定义图形的属性)
        7. FreeHand：**手绘图**
        8. Image：网络图片
        9. Template：模板（已经做好的 流程图 拓扑图 等）
        10. Layout：布局图
            1. Horizontal：水平布局
            2. Vertical：垂直布局
            3. Radial：辐射布局
            4. Organic：组织布局
            5. Circle：环形布局
        11. Advanced：高级图
            1. From Text：通过文本语法的数据，生成图形
            2. Mermaid：通过Mermaid语法的数据，生成图形
            3. SQL：通过SQL语法的数据，生成图形
            4. CSV：通过CSV语法的数据，生成图形

## Pandoc

1. 源码：https://github.com/jgm/pandoc
2. 官网：https://pandoc.org/
3. 用户文档：https://pandoc.org/MANUAL.html
4. 安装
    1. `brew install pandoc`
5. 概述
    1. 一个超级强大的文档格式转换工具
    2. 官方称之为文档格式转换领域中的“瑞士军刀”。
6. 相关命令
    ```sh
    # 查看帮助文档
    pandoc -h

    # txt文件 转 html文件（默认输出到控制台，可以使用 > 进行重定向）
    pandoc {input}.txt > {output}.html 

    # md文件 转 pdf文件：Pandoc需要依赖Latex才能将markdown转为pdf（有两个配置选项） 
    # 1. --pdf-engine=xelatex（把latex的编译引擎指定为“xelatex”，如果不指定，md文档中有中文编译会报错）
    # 2. -V mainfont=Hei （指定字体为黑体，如果不指定，md文档中的中文字符，无法解析到pdf文档中）
    pandoc --pdf-engine=xelatex -V mainfont=Hei {input}.md -o {output}.pdf
    ```

## Audacity

1. 官网：https://www.audacityteam.org/
2. 源码地址：https://github.com/audacity/audacity
3. 快速帮助手册：https://manual.audacityteam.org/quick_help.html
4. 使用手册：https://manual.audacityteam.org/index.html
5. 论坛：https://forum.audacityteam.org/
6. Wiki文档：https://wiki.audacityteam.org/index.php
7. 概述
    1. 免费开源的音频处理工具
8. 安装：`brew install --cask audacity`
9. 常用设置
    1. 查看声纹
    2. 倍速：`效果 -> 改变节奏`
    3. 截取音频片段
    4. FFmpeg库安装：`Audacity -> 偏好设置 -> 库`
        1. 安装后，可以支持iPhone语音备忘录的`M4A(AAC)`音频格式
        2. 还支持 通过导入视频文件，提取音频
    5. 重置工具栏：`视图 -> 工具栏 -> 重置工具栏`
10. 使用
    1. 录音后，可以直接操作“音轨”（对“音轨”进行，删除、剪切、复制 等）

## IINA

1. 官网：https://iina.io/
2. 源码：https://github.com/iina/iina
3. 概述
    1. 最强万能视频播放器
    2. 基于MPV（MPV作为内核）
        1. **MPV**
            1. 官网：https://mpv.io/
            2. 源码：https://github.com/mpv-player/mpv
            3. 概述
                1. 一款命令行启动/高度自定义配置的高性能跨平台开源播放器

## Snipaste

1. 源码：https://github.com/Snipaste/feedback
2. 官网：https://www.snipaste.com/
3. 安装：`brew install --cask snipaste`
4. 概述
    1. 跨平台的、开源的截图工具
    2. 目前不支持OCR（Optical Character Recognition，光学字符识别）功能
5. 配置文件：`~/.snipaste/config.ini`

## Kap

1. 源码：https://github.com/wulkano/Kap
2. 官网：https://getkap.co/
3. 安装：`brew install --cask kap`
4. 概述
    1. 一款开源的录屏软件
    2. 支持直播插件的安装

## Irssi

1. 源码：https://github.com/irssi/irssi
2. 官网：https://irssi.org/
3. 新手文档：https://irssi.org/New-users/
    1. 使用流程：启动Irssi -> 连接一个网络 -> 进入一个频道
        1. 启动：打开iTerm -> `irssi`
        2. 连接一个网络
            1. 查看网络：`/network`
            2. 连接网络：`/connect {network_name}`
        3. 加入一个频道：`/join #{channel_name}`
            1. 中文频道
                1. #irssi：Irssi使用问题的咨询频道
                2. #linuxba：国内linux贴吧的irc频道，每天都会有一些人在频道里活跃，讨论问题或者闲聊，经常被调侃称为“基佬”。
                3. #c_lang_cn：C语言中文IRC频道
                4. #archlinux-cn：有关 Arch Linux相关的讨论
                5. #archlinux-cn-offtopic：灌水频道，一天9999+消息是经常的事情
                6. #debian-cn：debian开发者的频道
            2. 外文
                1. ##C++：c++语言大师大多在这里，仅讨论与c++语言（频道内有委员会成员）
                2. ##C++-general：以讨论c++周边技术的地方（频道内有委员会成员）
                3. #anime：可以讨论动漫，还可以讨论技术
                4. #emacs：emacs相关的频道（折腾群）
                5. #osdev：操作系统开发频道
4. 概述 
    1. 一个开源的基于命令行的IRC客户端
    2. Irssi 客户端能够支持 SILC和 ICB 协议。
5. 安装：`brew install irssi`
6. 配置文件：`~/.irssi/config`
7. 相关概念
    1. ICR（Internet Relay Chat，因特网中继聊天）
        1. 是一种历史悠久、应用广泛、成熟稳定的网络即时**通讯协议**
        2. 被广泛地应用于在线通讯和网络聊天中
        3. IRC最早由芬兰人雅尔口·欧伊卡林恁（Jarkko Oikarinen）于1988年8月创造以取代一个叫做MUT的程序
    2. 具体概念
        1. IRC网络（Network）：一个IRC客户端，可以连接IRC网络
        2. IRC频道（Channel）：可以理解为一个群聊或聊天室（Room）
        3. IRC服务器（Server）：**似乎用处不大**
8.  常用命令
    1. 基础命令
        1. `/help`：显示所有可用的命令
            1. `/help {命令名}`：查看命令的使用说明
        2. `/clear`：清屏
        3. `/set`：查看可以可配置项
            1. `/set {key} {val}`：变更可配置项
                1. `/set nick {nick_name}`：变更昵称
    2. 客户端级别的命令
        1. `/quit`：退出当前的Irssi客户端
    3. 网络（Network）级别的命令
        1. `/network`：列出预定义的网络（Network），Irssi在安装的时候，会预定义一些网络
        2. `/connect {network_name}`：连接指定的网络
        3. `/disconnect {network_name}`：断开连接
    4. 频道（Channel）级别的命令
        1. `/join #{channel_name}`：加入一个频道
        2. `/part`：退出频道
        3. `/list #{channel_name}`：查看指定频道的信息
    5. 聊天窗口（Window）级别的命令
        1. `/window`：常看当前的窗口信息
            1. `/window list`：查看窗口列表
        2. `/wc`：window close，关闭聊天窗口
        3. `/q`：退出和某人的私聊
            1. `/q {username}`：私聊某人
        4. `/away {原因}`：切换为离开状态（此时，状态栏会出现zZzZ的图标）
        5. `/back`：切换为回来状态（表示人在线）
        6. 
    6. 底部状态栏（Statusbar）级别的命令
        1. `/statusbar`：管理状态栏
    7. 服务器（Server）级别的命令
        1. `/server`：列出当前已经连接的服务器（Server）
            1. `/server list`：列出可用的服务器（Server）
    8. 布局（Layout）
        1. `/layout`
    9. 别名
        1. `/alias`：给命令起别名