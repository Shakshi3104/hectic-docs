# flower.augmentation

## Data augmentation per instance
input_shape = (window_size, 3)のデータに対するデータ拡張

### flower.augmentation.flipping
```python
flower.augmentation.flipping(x, overall=True)
```
#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(window_size, 3)`
- overall: Trueのとき、全ての軸を同時に反転させる。Falseのとき、各軸ごとに反転させる。

#### Returns
- x_new: flipしたx

### flower.augmentation.swapping
```python
flower.augmentation.swapping(x)
```
#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(window_size, 3)`

#### Returns
- x_new: swapしたx


## Data augmentation per batch
input_shape = (batch_size, window_size, 3)のデータに対するデータ拡張

### flower.augmentation.flipping_batch
```python
flower.augmentation.flipping_batch(x, overall=True)
```
#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(batch_size, window_size, 3)`
- overall: Trueのとき、全ての軸を同時に反転させる。Falseのとき、各軸ごとに反転させる。

#### Returns
- x_new: flipしたx

### flower.augmentation.swapping_batch
```python
flower.augmentation.swapping_batch(x)
```
#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(batch_size, window_size, 3)`

#### Returns
- x_new: swapしたx

## tf.funcion
`tf.data.Dataset.map()`で使う関数

### flower.augmentation.augment
```python
flower.augmentation.augment(x, y)
```

#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(window_size, 3)`
- y: xに対応するラベル

#### Returns
- x, y

### flower.augmentation.augment_batch
```python
flower.augmentation.augment_batch(x, y)
```

#### Arguments
- x: channel-lastな3軸センサデータ, `shape=(batch_size, window_size, 3)`
- y: xに対応するラベル

#### Returns
- x, y: データ拡張したデータ, ラベル