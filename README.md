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

### 标识块：

以下标识块必须存在

**文件头部**
```
-ChartInfoStart-
谱师名
Level
Difficulty
MusicID
-ChartInfoEnd-
```

**BPM组标识**
逻辑同上一个版本，这里是列表，下面Note中的BPM是对应的上面列表中的元素
```
-BPMStart-
P1:114,514
P2:1919,810
-BPMEnd-
```

**谱面开始标识**
```
-NotesStart-
各Note
-NotesEnd-
```

### 各Note

```
ID#Type#BPMIndex#Time#Position#Side
```

#### Type
普通判定类：Normal, Touch, Flick

(n,t,f)

特殊判定类：Hold, Link, Task(P), Rotate

(h,l,p,r)

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
ID#h#BPMIndex#Time#Position#Side#Duration
```

```
ID#l#BPMIndex#Time#Position#Side#Duration#OppositePosition
Duration: 飞到对面所需时间
```

```
ID#p#BPMIndex#Time#Position#Side#LinkedNote
LinkedNote: 被联系起来的NoteID
```

```
ID#r#BPMIndex#Time#Position#Side#Duration#Target
```
## 播放

流速： BPM/60 （units/sec）
