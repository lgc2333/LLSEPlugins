<!-- markdownlint-disable MD033 -->

# NbsPlayer

BDS 中的 NBS 音乐播放器！  
下载插件请去[Releases](https://github.com/lgc2333/LLSEPlugins/releases)

## 介绍

### 运作原理

1. 插件通过[NbsConvertor](NbsConvertor)将 nbs 文件转换成 json 格式存储在 `cache` 目录中
2. 读取 json 数据，通过`setInterval`设置循环执行函数获取当前时间来对时和播放，并且根据已播放时间根据 json 解析后的各数据生成`PlaySoundPacket`数据包发送给客户端

### 特点

- 支持 单音符/轨道/音色 的音高、音量等设置
- 支持超过两个八度限制的音符
- 支持自定义音色
  - 请将自定义音色的名称设置为`playsound`命令可以播放的声音 ID，例：`dig.stone`，支持资源包自定义的音色

### 缺点

- 播放效果不好，会有小卡顿（对不上拍）（脚本语言~~ / 调用 BDS 执行命令~~效率问题？）
  - Tip：`0.2.0`版本已换为向客户端发送数据包，卡顿问题有所改善
- 无法实现左右声道偏离（`playsound`局限）
- 稍微动一下视角声道就会偏（`playsound`局限）
- 插件没有经过深度测试，可能会有小 bug

### 截图

![1](readme/1.png)  
![2](readme/2.png)  
![3](readme/3.png)  
![4](readme/4.png)

### 演示

<https://www.bilibili.com/video/bv1gT41177sm>

<iframe src="//player.bilibili.com/player.html?aid=471512773&bvid=BV1gT41177sm&cid=789620051&page=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"> </iframe>

### 指令

#### `nbsplayer` - 打开插件菜单 / 播放指定音乐

- 格式：`nbsplayer [filename: text]`
- 参数：
  - `filename` - *（可选）*欲播放的文件名
- 权限：所有人
- 限制：只能由玩家以及`execute`命令执行

#### `nbsplay` - OP 播放指令

- 格式：`nbsplay <player: target> <filename: text> [forcePlay: Boolean]`
- 参数：
  - `player` - 欲执行操作的玩家
  - `filename` - 欲播放的文件名
  - `forcePlay` - *（可选）*是否强制让正在播放音乐的玩家播放此音乐
- 权限：管理员

#### `nbstop` - 停止播放

- 格式：`nbstop`
- 参数：无
- 权限：所有人
- 限制：只能由玩家以及`execute`命令执行

#### `nbsisplaying` - 查询玩家播放状态

- 格式：`nbsisplaying`
- 参数：无
- 权限：所有人
- 限制：只能由玩家以及`execute`命令执行

## 安装

请去 [Releases](https://github.com/lgc2333/LLSEPlugins/releases) 下载最新版插件附件，解压到 bds 的插件目录

## 配置

直接将 nbs 文件放置在插件数据目录即可，无需重启服务器~~，注意文件名不要有特殊字符、中文等，否则可能会出错~~（应该已修复）  
例图：  
![6](readme/6.png)

## 配置文件

插件没有配置文件

## 联系我

QQ：3076823485  
吹水群：[1105946125](https://jq.qq.com/?_wv=1027&k=Z3n1MpEp)  
邮箱：<lgc2333@126.com>

## 赞助

感谢大家的赞助！你们的赞助将是我继续创作的动力！

- [爱发电](https://afdian.net/@lgc2333)
- <details>
    <summary>赞助二维码（点击展开）</summary>

  ![讨饭](https://raw.githubusercontents.com/lgc2333/ShigureBotMenu/master/src/imgs/sponsor.png)

  </details>

## 更新日志

- 0.1.1
  - 修复 nbs 文件名不能为特殊符号或中文的问题
  - 修复无法播放最后一 tick 的音符的 bug
  - 加入音符数量显示
- 0.2.0
  - 换用向客户端发送数据包的方式播放音效
  - NbsConvertor 的运行超时限制为 10s
  - 加入歌曲列表为 0 时的提示，与页数小于 2 无法跳页的提示
  - `nbsplayer`命令加入可选参数`filename`，可以直接指定播放的文件名
  - 加入命令`nbsplay` `nbsisplaying`（[指令列表](#指令)）
