# Schiphalast-Chart-File 2.0

用于 Schiphalast 的谱面格式

A chart file for game Schiphalast.

## Introduction

每一首**曲目**一般有四个**谱面**，按文件夹分类

文件夹结构如下：
```
- TestChart
  |- 难度名.sc - 谱面文件
  |- music.ogg  - 音源
  |- sb_难度名.sb - 故事板文件
```

## Chart

存储Note及歌曲信息的文件为 `难度名.sc`，

### 文件头部：

```
-ChartStart-
谱师名
Level
Difficulty
MusicID
-InfoEnd-
```

### 各Note

```
ID#Type#Time#Position#Side
```

#### Type
普通判定类：Normal, Touch, Flick

特殊判定类：Hold, Link, Task(P), Rotate

取Type名的首字母小写作为类型参数值

#### Time

整数，单位毫秒（ms）

#### Position

浮点数，标记具体位置（原参数posY）

#### Side

-1:左边玩家（1P)
1:右边玩家（2P)

#### 特殊判定类参数

在普通Note后按顺序添加参数

```
ID#h#Time#Position#Side#Duration
```

```
ID#l#Time#Position#Side#Duration#OppositePosition
Duration: 飞到对面所需时间
```

```
ID#p#Time#Position#Side#LinkedNote
LinkedNote: 被联系起来的NoteID
```

```
ID#r#Time#Position#Side#Duration#Target
```
## 播放

流速： BPM/60 （units/sec）
