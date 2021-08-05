# flower.experiments

## Flower
`Flower` is a class for running experiments of this project.

#### Aliases
`flower.Flower`

`flower.experiments.Flower`

### Initializer
```python
flower.experiements.experiments.Flower(model: flower.utils.SupportedModel, module: flower.utils.SupportedSubmodule = None, concat_hcf=False, result_dir="./results/", weight_dir="./weights/", data_dir="./data")
```

#### Arguments
- model: flower.utils.SupportedModel, 実験を実施するモデル
- module: Optional(flower.utils.SupportedSubmodule), モデルに挿入するモジュール. Noneの場合は挿入しない
- concat_hcf: Hand-crafted featuresを結合するかどうか
- result_dir: 結果を保存するディレクトリパス
- weight_dir: モデルの重みを保存するディレクトリパス
- data_dir: データセットがあるディレクトリパス

### flower.fit()
```python
Flower.fit(epochs=100, learning_rate=1e-3, batch=20, augmentation=False, num_trials=1, datasets: SupportedDataset = flower.utils.SupportedDataset.HASC, shuffled=False, seed=0, multi_gpu=False)
```
#### Arguments
- epochs: エポック数, デフォルト 100
- learning_rate: 学習率, デフォルト 1e-3
- augmentation: データ拡張をするかどうか, デフォルト False
- num_trials: 試行回数, デフォルト 1
- datasets: SupportedDataset, 実験を実施するデータセット
- shuffled: データセットの被験者をシャッフルするかどうか, デフォルト False
- seed: ランダムのシード
- multi_gpu: マルチGPUで学習するかどうか, デフォルト False
 