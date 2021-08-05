# flower.augmentation

## Data augmentation

### flower.augmentation.flipping
```python
flower.augmentation.flipping(x, overall=True, axis=0)
```
#### Arguments
- x: channel-lastなセンサデータ, `shape=(window_size, channel)` or `shape=(batch_size, window_size, channel)`
- overall: Trueのとき、全ての軸を同時に反転させる。Falseのとき、各軸ごとに反転させる。
- axis: 軸

#### Returns
- x_new: flipしたx

### flower.augmentation.swapping
```python
flower.augmentation.swapping(x)
```
#### Arguments
- x: channel-lastな3軸 or 6軸センサデータ , `shape=(window_size, channel)` or `shape=(batch_size, window_size, channel)`

#### Returns
- x_new: swapしたx


## tf.funcion
`tf.data.Dataset.map()`で使う関数

### flower.augmentation.augment
```python
flower.augmentation.augment(x, y)
```

#### Arguments
- x: channel-lastなセンサデータ, `shape=(window_size, channel)`
- y: xに対応するラベル

#### Returns
- x, y

### flower.augmentation.augment_batch
```python
flower.augmentation.augment_batch(x, y)
```

#### Arguments
- x: channel-lastなセンサデータ, `shape=(batch_size, window_size, channel)`
- y: xに対応するラベル

#### Returns
- x, y: データ拡張したデータ, ラベル