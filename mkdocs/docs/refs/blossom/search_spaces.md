# 実装済みの探索範囲

| ID | *ConvOps* | *KernelSize* | *SkipOps* | *#Layers* | *#Filters* | *#Blocks* | *SERatio* |
| :-: | :------- | :----------- | :-------- | :-------- | :--------- | :-------- | :-------- |
| A | Conv, SepConv, MBConv | 2 - 5 | none, pool, identity | 2 - 5 | 16, 32, 64, 128 (固定) | 4 (固定) | 0.0, 0.25 |
| B | Conv, SepConv, MBConv | 2 - 5 | none, pool, identity | 2 - 5 | 32 - 128 (4 steps) | 4 (固定) | 0.0, 0.25 |
| C | Conv, SepConv, MBConv | 2 - 5 | none, pool, identity | 2 - 5 | 32 - 192 (4 steps) | 4 (固定) | 0.0, 0.25 |
| D | Conv, SepConv, MBConv | 2 - 5 | none, pool, identity | 2 - 5 | 0.75, 1.0, 1.25 (相対) | 4 (固定) | 0.0, 0.25 |
| E | Conv, SepConv, MBConv, ExtremeInception | 2 - 5 | none, pool, identity | 2 - 5 | 32 - 320 (4 steps) | 3 - 5 | 0.0, 0.25 |
| Z | Conv, MBConv | 2 - 5 | none, identity | 2 - 5 |  0.75, 1.0, 1.25 (相対) | 4 (固定) | 0.25 (固定) |

