<!-- markdownlint-disable MD031 MD033 MD036 -->

# EveryoneWarp

玩家公共传送点  
[鸣谢](#鸣谢)

## 介绍

### Features

- 所有玩家都可以添加 Warp
- Warp 无法传送，纯生存服务器首选
- 独特的导航功能
- 玩家只能删除他们自己创建的 warp，OP 可以任意删除
- Warp 没有防重名机制

### Pictures

![0](readme/0.png)
![1](readme/1.png)  
![2](readme/2.png)  
![3](readme/3.png)  
![4](readme/4.png)  
![5](readme/5.png)  
![6](readme/6.png)

如果你想给这个插件提建议的话，欢迎在 github 提 issue！

## 安装方法

见[插件下载安装教程](../tutorial.md)  
老旧的 LL 版本加载`EveryoneWarp.lls.js`报错的，可以使用`EveryoneWarp_OldLXL.lls.js`

## 配置文件

插件没有配置文件

## 鸣谢

感谢 Tech Sky City 服务器腐竹的支持和玩家的试用与反馈！  
TSC 是一个 1.18.2 基岩版的生电服务器  
安装有 Trapdoor，FakePlayer 等插件  
服务器规则原汁原味，死亡掉落、没有传送指令……  
如果你有兴趣想加入他们，点击[这里](https://jq.qq.com/?_wv=1027&k=p2ke7c5F)

## 更新日志

- 0.1.1
  - 修复玩家退服时候导航未关闭
  - 修复`EveryoneWarp_OldLXL.lls.js`能同时启动两个导航
- 0.1.2
  - 修复指令权限
- 0.1.3
  - 修复错误的命名（`wrap`->`warp`）
  - 导航加入地狱、主世界维度坐标换算
- 0.1.4
  - 修复显示的日期少了一个月的 bug