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
