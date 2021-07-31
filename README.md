# Schiphalast-Chart-File

用于 Schiphalast 的谱面格式

A chart file for game Schiphalst.

## Introduction

谱面后缀为 `.sch`, 本质为 `zip` 文件格式。

此内文件结构如下：
```
- TestChart.sch
  |- chart.json - 谱面文件
  |- image.png  - 封面
  |- album.png  - 背景（可选）
  |- music.mp3  - 音乐文件
```

## Chart

存储Note及歌曲信息的文件为 `chart.json`，格式如下：
```
{
	"chartID": "001",
	"chartName": "Test Chart",
	"authorName": "Function_X_Y",
	"charterName": "Function_X_Y",
	"chartLevel": 114514,
	"chartDifficulty": "Schiphalast",
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
		"endT": "1860",
		"BPM": "0",
		"yPos": "0"
	}]
}
```
