# Schiphalast-Chart-File

用于 Schiphalast 的谱面格式

A chart file for game Schiphalst.

## Introduction

谱面后缀为 `.sch`, 本质为 `zip` 文件格式。

此内文件结构如下：
```
- TestChart
  |- 难度名.json - 谱面文件
  |- music.ogg  - 音源
```

## Chart

存储Note及歌曲信息的文件为 `chart.json`，格式如下：
```
{
	"version": 1.5,
	"BPMP1": [
		260, 520
	],
	"BPMP2": [
		260, 520
	],
	"notesP1": [{
			"type": "n",
			"time": "920",
			"BPM": "0",
			"yPos": "-2"
		},
		{
			"type": "t",
			"time": "1840",
			"BPM": "1",
			"yPos": "0"
		},
		{
			"type": "f",
			"time": "2760",
			"BPM": "1",
			"yPos": "0"
		},
		{
			"type": "fr",
			"time": "3690",
			"BPM": "1",
			"yPos": "0",
			"rs": "2"
			"rd": "114"
		}
	],
	"notesP2": [{
		"type": "h",
		"time": "930",
		"Len": "1860",
		"BPM": "0",
		"yPos": "0"
	}，
	{
		"type": "p", // task标记
		"time": "930",
		"eType": "h", // 被标记对象
		"wTime": "1000" // task本体和被标记间间隔
		"Len": "1860",
		"BPM": "0",
		"yPos": "0"
	}，
	{
		"type": "l", //link
		"time": "114514",
		"endY": "1860", // 对面的目标Y
		"eTime": "2000", // 结束时间
		"BPM": "0",
		"yPos": "0"
	}]
}
```
