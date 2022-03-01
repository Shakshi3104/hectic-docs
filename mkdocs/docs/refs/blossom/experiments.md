# blossom.experiments

## Blossom

`Blossom` is a class for searching unseen models

#### Aliases

`blossom.Blossom`

`blossom.experiments.blossom.Blossom`

### Initializer
```python
blossom.experiments.blossom.Blossom(
    hypermodel: blossom.experiments.searchable_models.SearchableModel,
    output_dir="./outputs/",
    data_dir="./data/"
)
```

#### Arguments

- hypermodel: blossom.experiments.searchable_models.SearchableModel, 探索範囲を実装したクラス, `blossom.experiments.searchable_models.SearchableModel`を継承したクラスもしくは`keras_tuner.HyperModel`を継承したクラスのみ有効
- output_dir: 探索の過程や結果を保存するディレクトリパス
- data_dir: データセットがあるディレクトリパス

### Blossom.search()

```python
Blossom.search(
    project_name: str, 
    max_trials=10, 
    epochs=100, 
    batch=20, 
    augmentation=False,
    dataset_id=None, 
    small=False, 
    max_model_size=None, 
    search_epochs=None, 
    seed=0, 
    board=False
)
```

#### Arguments

- project_name: 探索のプロジェクト名, 探索の結果は`{outputs_dir}/{project_name}`に保存される
- max_trials: 試行回数, デフォルト 10
- epochs: エポック数, デフォルト 100
- batch: バッチサイズ, デフォルト 20
- augmentation: データ拡張するかどうか, デフォルト False
- dataset_id: 探索に使用するHASCデータセットのID, デフォルト None
- small: 被験者数の少ないデータセットを使うかどうか, デフォルト False
- max_model_size: 探索されるモデルの最大パラメータ数, 指定した値よりも大きいモデルは却下される, デフォルト None
- seed: ランダムシード
- board: TensorBoardを使うかどうか, デフォルト False

# blossom.experiments.searchable_models
## SearchableModel

`SearchableModel` is a base class for setting search space

### Initializer
```python
blossom.experiments.searchable_models.SearchableModel(
    input_shape=(256, 3), 
    classes=6, 
    learning_rate=1e-3
)
```

#### Arguments

- input_shape: 入力のshape
- classes: クラス数
- learning_rate: 学習率

### SearchableModel.build()
```python
SearchableModel.build(
    hp
)
```

`build()`に探索範囲を設定する

#### Arguments

- hp: keras_tunerのhp

## 実装済みSearchableModel

探索範囲の詳細については、[こちら](search_spaces.md)を参照してください。

- BlossomSearchModelA
- BlossomSearchModelB
- BlossomSearchModelC
- *BlossomSearchModelD*
- BlossomSearchModelE
- *BlossomSearchModelZ*

# blossom.experiments.searched_models

探索済みモデル

## MarNASNet

```python
blossom.experiments.searched_models.MarNASNet
```

- case `A`
- case `B`
- case `C`
- case `D`
- case `E`
- case `Z`

### build_model()

```python
MarNASNet.build_model(self, best_hyperparameter_json_file, input_shape=(256, 3), classes=6) -> tf.keras.Model
```

### blossom.experiments.searched_models.build_searched_model

```python
blossom.experiments.searched_models.build_searched_model(
    json_path: str, 
    search_space=1, 
    input_shape=(256, 3), 
    classes=6
) -> tf.keras.Model
```

#### Arguments

- json_path: 探索されたモデルのハイパーパラメータのJSONファイルのパス
- search_space: 探索空間のID
- input_shape: 入力shape
- classes: クラス数

#### Returns

- model: tf.keras.models.Model


## Bloom

`Bloom` is a class for running experiments with MarNASNets, like a `Flower`.

### Initializer

```python
blossom.experiments.searched_models.Bloom(
    model: blossom.experiments.searched_models.MarNASNet,
    best_hyperparameters_path: str,
    result_dir="./results/",
    weight_dir="./weights/",
    output_dir=None,
    data_dir="./data/"
)
```

#### Arguments

- model: blossom.experiments.searched_models.MarNASNet, 実験を実施するMarNASNet
- best_hyperparameters_path: 探索されたモデルのハイパーパラメータのJSONファイルのパス
- result_dir: 結果を保存するディレクトリパス
- weight_dir: モデルの重みを保存するディレクトリパス
- output_dir: 結果とモデルの重みを保存するディレクトリ、指定した場
- result_dirとweight_dirはoutput_dirを元に生成される
- data_dir: データセットがあるディレクトリパス

### Bloom.fit()

```python
Bloom.fit(
    epochs=100, 
    learning_rate=1e-3, 
    batch=20, 
    augmentation=False,
    datasets: SupportedDataset = SupportedDataset.HASC, seed=0, 
    multi_gpu=False, 
    valid=True,
    dataset_id=1, 
    callbacks=None, 
    small=False
)
```

#### Arguments
- epochs: エポック数, デフォルト 100
- learning_rate: 学習率, デフォルト 1e-3
- batch: バッチサイズ, デフォルト 20
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
