# flower.experiments

## Flower
`Flower` is a class for running experiments of this project.

#### Aliases
`flower.Flower`

`flower.experiments.Flower`

### Initializer
```python
flower.experiements.flower.Flower(
  model: flower.options.FlowerModel, 
  module: flower.options.SupportedSubmodule = None,
  concat_hcf=False, 
  result_dir="./results/", 
  weight_dir="./weights/", 
  output_dir=None
  data_dir="./data"
)
```

#### Arguments
- model: flower.utils.SupportedModel, 実験を実施するモデル
- module: Optional(flower.utils.SupportedSubmodule), モデルに挿入するモジュール. Noneの場合は挿入しない
- concat_hcf: Hand-crafted featuresを結合するかどうか
- result_dir: 結果を保存するディレクトリパス
- weight_dir: モデルの重みを保存するディレクトリパス
- output_dir: 結果とモデルの重みを保存するディレクトリ、指定した場合`result_dir`と`weight_dir`は`output_dir`を元に生成される
- data_dir: データセットがあるディレクトリパス

### flower.fit()
```python
Flower.fit(
  epochs=100, 
  learning_rate=1e-3, 
  batch=20, 
  augmentation=False, 
  num_trials=1, 
  datasets: SupportedDataset = flower.utils.SupportedDataset.HASC, 
  shuffled=False, 
  seed=0, 
  multi_gpu=False, 
  valid=True, 
  dataset_id=None, 
  callbacks=None, 
  small=False
)
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
- valid: 検証用データを使うかどうか、Trueの場合、valid_dsとtest_dsは同じもの
- dataset_id: データセットID
- callbacks: Kerasのcallbackのリスト
- small: Trueの場合、HASCデータセットの実験で被験者数が少ない方を使用する

## Leaf

`Leaf` is a class for running experiments of Multi-layer perceptron with Hand-crafted features.

#### Aliases

`flower.Leaf`

`flower.experiments.Leaf`

### Initializer

```python
flower.experiements.leaf.Leaf(
  result_dir="./results/", 
  weight_dir="./weights/", 
  output_dir=None
  data_dir="./data"
)
```

## Bouquet

`Bouquet` is a class for running experiments of all `SupportedModel`.

#### Aliases

`flower.Bouquet`

`flower.experiments.Bouquet`

### Initializer

```python
flower.experiements.leaf.Leaf(
  module: flower.options.SupportedSubmodule = None,
  concat_hcf=False, 
  result_dir="./results/", 
  weight_dir="./weights/", 
  output_dir=None
  data_dir="./data",
  models: [flower.options.FlowerModel] = None
)
```

#### Arguments

- module: Optional(flower.utils.SupportedSubmodule), モデルに挿入するモジュール. Noneの場合は挿入しない
- concat_hcf: Hand-crafted featuresを結合するかどうか
- result_dir: 結果を保存するディレクトリパス
- weight_dir: モデルの重みを保存するディレクトリパス
- output_dir: 結果とモデルの重みを保存するディレクトリ、指定した場合`result_dir`と`weight_dir`は`output_dir`を元に生成される
- data_dir: データセットがあるディレクトリパス
- models: 実験を行うモデルのリスト、`flower.options.FlowerModel`を継承したモデルの指定であれば利用可能、`None`のときは`flower.options.SupportedModel.all_cases()`を使う