# flower.datasets

## Dataset via `tf.data`

### flower.datasets.datasets.load_hasc
```python
flower.datasets.datasets.load_hasc(batch=20, augmentation=False, extraction=False, shuffled_id=None, valid=True, hcf_only=False, data_dir="./data/", drop_remainder=True)
```
HASCデータセットを`tf.data`形式で読み込む。

Reference:

- [HASC Challenge: gathering large scale human activity corpus for the real-world activity understandings](https://dl.acm.org/doi/10.1145/1959826.1959853)

#### Argments
- batch: バッチサイズ
- augmentation: データ拡張をするかどうか
- extraction: 特徴量抽出をするかどうか
- shuffled_id: シャッフルデータセットID
- valid: 検証用データを使用するかどうか。Trueのとき、データセットをtrain:valid:testで分割する。Falseのとき、データセットをtrain(train+valid):testで分割する
- hcf_only: 特徴量のみを返す
- data_dir: データセットのディレクトリ
- drop_remainder:  バッチサイズ以下のバッチを捨てるかどうか

#### Returns
- train_ds: tf.data.Dataset, 学習データセット
- valid_ds: tf.data.Dataset, 検証データセット, valid=Falseのときはtest_dsと同じもの
- test_ds: tf.data.Dataset, テストデータセット

### flower.datasets.datasets.load_uci
```python
flower.datasets.datasets.load_uci(batch=20, augmentation=False, extraction=False, shuffled_id=None, valid=True, hcf_only=False, data_dir="./data/", drop_remainder=True)
```
UCIデータセットを`tf.data`形式で読み込む。

Reference:

- [A Public Domain Dataset for Human Activity Recognition Using Smartphones](https://www.mdpi.com/1424-8220/20/8/2200)
- Dataset link: https://archive.ics.uci.edu/ml/machine-learning-databases/00240/UCI%20HAR%20Dataset.zip

#### Argments
- batch: バッチサイズ
- augmentation: データ拡張をするかどうか
- extraction: 特徴量抽出をするかどうか
- shuffled_id: シャッフルデータセットID
- valid: 検証用データを使用するかどうか。Trueのとき、データセットをtrain:valid:testで分割する。Falseのとき、データセットをtrain(train+valid):testで分割する
- hcf_only: 特徴量のみを返す
- data_dir: データセットのディレクトリ
- drop_remainder:  バッチサイズ以下のバッチを捨てるかどうか

#### Returns
- train_ds: tf.data.Dataset, 学習データセット
- valid_ds: tf.data.Dataset, 検証データセット, valid=Falseのときはtest_dsと同じもの
- test_ds: tf.data.Dataset, テストデータセット

### flower.datasets.datasets.load_wisdm
```python
flower.datasets.datasets.load_wisdm(batch=20, augmentation=False, extraction=False, shuffled_id=None, valid=True, hcf_only=False, data_dir="./data/", drop_remainder=True)
```

WISDMデータセットを`tf.data`形式で読み込む。

Reference:

- [Activity Recognition using Cell Phone Accelerometers](https://dl.acm.org/doi/10.1145/1964897.1964918)
- Dataset link: https://www.cis.fordham.edu/wisdm/includes/datasets/latest/WISDM_ar_latest.tar.gz

#### Argments
- batch: バッチサイズ
- augmentation: データ拡張をするかどうか
- extraction: 特徴量抽出をするかどうか
- shuffled_id: シャッフルデータセットID
- valid: 検証用データを使用するかどうか。Trueのとき、データセットをtrain:valid:testで分割する。Falseのとき、データセットをtrain(train+valid):testで分割する
- hcf_only: 特徴量のみを返す
- data_dir: データセットのディレクトリ
- drop_remainder:  バッチサイズ以下のバッチを捨てるかどうか

#### Returns
- train_ds: tf.data.Dataset, 学習データセット
- valid_ds: tf.data.Dataset, 検証データセット, valid=Falseのときはtest_dsと同じもの
- test_ds: tf.data.Dataset, テストデータセット

## Dataset via numpy
### flower.datasets.load_hasc_from_pkl
```python
flower.datasets.load.load_hasc_from_pkl(window_size=256, data_dir="./data/")
```
HASCデータセットをpickleから読み込む。pickleファイルがない場合は、sensorutilsで生データから読み込み、pickleで書き出す。

#### Arguments
- window_size: ウィンドウサイズ
- data_dir: データセットのあるディレクトリ

#### Returns
- x_train: np.ndarray, xの学習データ
- y_train: np.ndarray, yの学習データ
- x_valid: np.ndarray, xの検証データ
- y_valid: np.ndarray, yの検証データ
- x_test: np.ndarray, xのテストデータ
- y_test: np.ndarray, yのテストデータ


### flower.datasets.load_uci_from_pkl
```python
flower.datasets.load.load_uci_from_pkl(data_dir="./data/")
```
UCIデータセットをpickleから読み込む。pickleファイルがない場合は、sensorutilsで生データから読み込み、pickleで書き出す。

#### Arguments
- data_dir: データセットのあるディレクトリ

#### Returns
- x_train: np.ndarray, xの学習データ
- y_train: np.ndarray, yの学習データ
- x_valid: np.ndarray, xの検証データ
- y_valid: np.ndarray, yの検証データ
- x_test: np.ndarray, xのテストデータ
- y_test: np.ndarray, yのテストデータ


### flower.datasets.load_wisdm_from_pkl
```python
flower.datasets.load.load_wisdm_from_pkl(window_size=256, data_dir="./data/")
```
WISDMデータセットをpickleから読み込む。pickleファイルがない場合は、sensorutilsで生データから読み込み、pickleで書き出す。

#### Arguments
- window_size: ウィンドウサイズ
- data_dir: データセットのあるディレクトリ

#### Returns
- x_train: np.ndarray, xの学習データ
- y_train: np.ndarray, yの学習データ
- x_valid: np.ndarray, xの検証データ
- y_valid: np.ndarray, yの検証データ
- x_test: np.ndarray, xのテストデータ
- y_test: np.ndarray, yのテストデータ

## Generate random subjects dataset
### flower.datasets.shuffle.generate_shuffled_hasc
### flower.datasets.shuffle.generate_shuffled_uci
### flower.datasets.shuffle.generate_shuffled_wisdm