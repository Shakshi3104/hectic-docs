# Quick start

このページでは`flower`フレームワークの使い方を紹介します。

## Dependencies
Hectic (flower & blossom)は、下記のパッケージが必要です。

- tensorflow >= 2.4
- tensorflow-addons
- [tfgarden](https://github.com/Shakshi3104/tfgarden): `pip install git+https://github.com/Shakshi3104/tfgarden.git`
- [sensorutils](https://github.com/haselab-dev/sensorutils): `pip install git+https://github.com/haselab-dev/sensorutils.git`
- numpy
- scipy
- pandas

## Flowerクラスの利用

`flower.Flower`クラスを使うことで、HASCデータセットなどの行動認識データセットに対するモデルの推定精度を検証する実験を行うことができます。モデルの指定は`SupportedModel`、データセットの指定は`SupportedDataset`を使います。

下記に示すコードはHASCデータセットにMobileNetを適用する最も簡単な例です。

```python
from flower import *

# Flowerクラスをインスタンス化
flower = Flower(SupportedModel.MobileNet)
# 学習 & 評価
flower.fit(epochs=10, learning_rate=1e-3, batch=128, datasets=SupportedDataset.HASC)
```

また、AttentionモジュールやRNNモジュールを挿入したモデルやHand-crafted featuresを結合したモデルの実験を行うこともできます。モジュールは`SupportedSubmodule`で指定できます。

下記に示すコードはWISDMデータセットに対してSEモジュールを挿入したMobileNetの実験とHand-crafted featuresを結合したMobileNetの実験を行う例です。

```python
from flower import *

# SEモジュールを挿入したMobileNetの実験
flower = Flower(SupportedModel.MobileNet, SupportedSubmodule.SENet)
flower.fit(epochs=10, learning_rate=1e-3, batch=128, datasets=SupportedDataset.WISDM)

# HCFを結合したMobileNetの実験
flower = Flower(SupportedModel.MobileNet, concat_hcf=True)
flower.fit(epochs=10, learning_rate=1e-3, batch=128, datasets=SupportedDataset.WISDM)
```

!!! Note
    `flower.Flower`でサポートしているモデル、サブモジュール、データセットは[こちら](refs/flower/options.md)で確認できます。