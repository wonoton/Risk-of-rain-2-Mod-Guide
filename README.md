# 雨中冒险2不完全指北-Mod篇

## 简介

`Risk of Rain 2 Mod Guide` 本仓库是雨中冒险2食用不完全指北-Mod篇，希望广大与雨学家洗头愉快！ 

## 环境依赖

- 操作系统（BepInEx）
   - Windows 7, 8, 8.1 and 10 (x86 和 x64 均支持)
   - Linux 发行版 GCC 10 或更高版本，推荐 GNU/Linux 发行版 (x86 和 x64 均支持)、
   - macOS 10.13 High Sierra 或更高版本
- 支持的Unity
   - Unity 3 或更高版本

## 安装

- 框架及API安装
    - BepInExPack
       - 解压`bbepis-BepInExPack-X.X.X.zip`确保`winhttp.dll`与`Risk of Rain 2.exe`在同一目录下
    - R2API
       - 解压`tristanmcpherson-R2API-X.X.X.zip`至上一步骤中的`BepInEx`文件夹中
       - `monomod`文件夹中的文件需置于`BepInEx`文件夹中的`monomod`文件夹下
       - `plugins`文件夹中的文件需置于`BepInEx`文件夹中的`plugins`文件夹下
       - 若上述两个文件夹不存在可以尝试启动一遍游戏并退出或手动创建
- MOD安装
  - 解压mod文件.zip文件，将文件夹放置于`/BepInEx/Plugins/`文件夹下即可

## 文件夹释义

``` lua
BepInEx
├── plugins -- mod文件存放以及加载
├── config -- 如果mod支持修改配置，将会在此文件夹找到配置文件
├── patchers -- 部分高级mod需要在游戏运行时读取Mono.Cecil并修改.dll文件，mod有说明时将文件置于该文件夹
├── monomod -- MonoMod 补丁文件夹
└── core -- 核心文件夹，非升级框架不需要修改
```

## 框架及常用MOD介绍

- MOD下载地址：[https://thunderstore.io](https://thunderstore.io)

- R2API

   - ![](./document/resource/r2api/tristanmcpherson-R2API-2.4.29.png.128x128_q85.png) 
   - 下载地址：[https://thunderstore.io/package/tristanmcpherson/R2API](https://thunderstore.io/package/tristanmcpherson/R2API)
   - git地址：[https://github.com/risk-of-thunder/R2API](https://github.com/risk-of-thunder/R2API)
   > 提供其他mod运行所需api，需要依赖BepInEx框架，作为核心组件，在没有安装mod时不会对游戏产生任何影响。（默认去掉路人匹配以及棱镜试练）

- UnmoddedClients
   
   - ![](./document/resource/UnmoddedClients/vis-eyth-UnmoddedClients-1.1.4.png.128x128_q85.png)
   - 下载地址：[https://thunderstore.io/package/vis-eyth/UnmoddedClients](https://thunderstore.io/package/vis-eyth/UnmoddedClients)
   - git地址：[https://github.com/vis-eyth/UnmoddedClients](https://github.com/vis-eyth/UnmoddedClients)
   > 允许未安装mod但安装了框架的客户端加入你的主机，支持配置build_id，默认为steam的build_id，build_id不同将影响主机和客户端连接

- SteamBuildID
   
   - ![](./document/resource/SteamBuildID/baekhorangi-SteamBuildID-1.2.0.png.128x128_q85.jpg)
   - 下载地址：[https://thunderstore.io/package/baekhorangi/SteamBuildID](https://thunderstore.io/package/baekhorangi/SteamBuildID)
   > 主机：允许build_id不同的客户端加入游戏。客户端：允许加入build_id为“MOD”或者与自身相同的主机。

- ProperSave 游戏存档
   
   - ![](./document/resource/ProperSave/KingEnderBrine-ProperSave-2.1.1.png.128x128_q85.png)
   - 下载地址：[https://thunderstore.io/package/KingEnderBrine/ProperSave](https://thunderstore.io/package/KingEnderBrine/ProperSave)
   - git地址：[https://github.com/KingEnderBrine/-RoR2-ProperSave](https://github.com/KingEnderBrine/-RoR2-ProperSave)
   > 游戏将于每关开始时存档。同时只能存在一个存档，当所有玩家死亡时存档将被删除。多人游戏支持：人物选择界面将出现一个`load`按钮，当已有存档并且与存档内的玩家配置与当前已连接玩家相同时激活。

- TooManyFriends 修改最大游戏人数

   - ![](./document/resource/TooManyFriends/wildbook-TooManyFriends-1.0.0.png.128x128_q85.jpg)
   - 下载地址：[https://thunderstore.io/package/wildbook/TooManyFriends](https://thunderstore.io/package/wildbook/TooManyFriends)
   - git地址：[https://github.com/wildbook/R2Mods/tree/master/TooManyFriends](https://github.com/wildbook/R2Mods/tree/master/TooManyFriends)
   > 允许修改多人游戏最大人数，同时游戏人数可在`config/dev.wildbook.toomanyfriends`文件中修改，默认是16

- NoBossNoWait BOSS死亡时传送器立即充能

   - ![](./document/resource/NoBossNoWait/mistername-NoBossNoWait-1.1.3.png.128x128_q85.png)
   - 下载地址：[https://thunderstore.io/package/mistername/NoBossNoWait](https://thunderstore.io/package/mistername/NoBossNoWait)
   > BOSS死亡时传送器激励充能完毕

- ReviveAfterBoss BOSS死亡时复活所有死亡队友

   - ![](./document/resource/ReviveAfterBoss/_Simon-ReviveAfterBoss-1.0.0.png.128x128_q85.png)
   - 下载地址：[https://thunderstore.io/package/_Simon/ReviveAfterBoss](https://thunderstore.io/package/_Simon/ReviveAfterBoss)
   > BOSS死亡时复活所有已死亡，复活后当前关卡死亡将不会再次复活