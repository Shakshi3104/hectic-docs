# flower.features

## hand-crafted features
### flower.features.intensity
```python
flower.features.intensity(x, axis=1)
```
動きの激しさ (intensity)

#### Arguments
- x: センサデータ
- axis: 軸

#### Returns
- features

### flower.features.zcr
```python
flower.features.zcr(x, axis=1)
```
ゼロ交差率 (zero-crossing rate)

#### Arguments
- x: センサデータ
- axis: 軸

#### Returns
- features

## extracting features
### flower.features.extracting_features
```python
flower.features.etracting_features(x, axis=1)
```

flowerで使用する特徴量を抽出する関数

#### extracted features
- max
- min
- mean
- standard deviation
- 1st quartiles
- median
- 3rd quartiles
- interquartile range
- max of absolute value
- min of absolute value
- mean of absolute value
- standard deviation of absolute value
- rms
- initial value in the frame
- final value in the frame
- intensity
- skewness
- kurtosis
- zero-crossing rate
- max of power spectrum
- standard deviation of power spectrum
- 1st quartiles of power spectrum
- median of power spectrum
- 3rd quartiles of power spectrum
- interquartile range of power spectrum

#### Arguments
- x: センサデータ
- axis: 軸

#### Returns
- features

## tf.function
`tf.data.Dataset.map()`で使う関数

### flower.features.raw_and_extract

```
flower.features.raw_and_extract(x, y)
```

生データと特徴量を返す

#### Arguments

- x: channel-lastなセンサデータ, `shape=(batch_size, window_size, channel)`
- y: xに対応するラベル

#### Returns

- (x, f), y: (生データ, 特徴量), ラベル

### flower.features.extract
```python
flower.features.extract(x, y)
```

特徴量を返す

#### Arguments

- x: channel-lastなセンサデータ, `shape=(batch_size, window_size, channel)`
- y: xに対応するラベル

#### Returns
- f, y: 特徴量, ラベル

### flower.features.augemt_raw_and_extract

```
flower.features.augment_raw_and_extract(x, y)
```

データ拡張した生データと特徴量を返す

#### Arguments

- x: channel-lastなセンサデータ, `shape=(batch_size, window_size, channel)`
- y: xに対応するラベル

#### Returns

- (x, f), y: (生データ, 特徴量), ラベル

### flower.features.augment_extract

```python
flower.features.augment_extract(x, y)
```

データ拡張したデータに対する特徴量を返す

#### Arguments

- x: channel-lastなセンサデータ, `shape=(batch_size, window_size, channel)`
- y: xに対応するラベル