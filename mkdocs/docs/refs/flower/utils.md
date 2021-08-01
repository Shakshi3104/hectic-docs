# flower.utils

## SupportedModel

```python
flower.utils.SupportedModel
```

- case `SimpleCNN`
- case `VGG16`
- case `InceptionV3`
- case `ResNet18`
- case `PyramidNet18`
- case `Xception`
- case `DenseNet121`
- case `MobileNet`
- case `MobileNetV2`
- case `MobileNetV3Small`
- case `NASNetMobile`
- case `MnasNet`
- case `EfficientNetB0`
- case `EfficientNetLite0`


#### Aliases
`flower.SupportedModel`

### build_model()
```python
SupportedModel.build_model(input_shape=(256, 3), classes=6, submodule: SupportedSubmodule = None, concat_hcf=False, num_features=3 * 25) -> tf.keras.models.Model
```
モデルをビルドする

#### Arguments
- input_shape: モデルのinput shape, デフォルト (256, 3)
- classes: 出力クラス数, デフォルト 6
- submodule: Optional(flower.utils.SupportedSubmodule), 挿入するサブモジュール
- concat_hcf: Hand-crafted featuresを結合するかどうか
- num_features: 結合するHCFの数, concat_hcf=Trueのときに有効

#### Returns
- model: tf.keras.models.Model

## SupportedSubmodule
```python
flower.utils.SupportedSubmodule
```


Attention modules

- case `SENet`
- case `SKNet`
- case `CBAM`

RNN modules

- case `GRU`
- case `LSTM`
- case `bi-LSTM`


#### Aliases
`flower.SupportedSubmodule`

### module()
```python
SupportedSubmodule.module() -> flower.hydrangea.attention.BaseAttention
```
Attentionモジュールをビルドする (`SupportedModel.build_model()`内で利用される)

#### Returns
- module: flower.hydrangea.attention.BaseAttention

## SupportedDataset
```python
flower.utils.SupportedDataset
```

- case `HASC`
- case `WISDM`
- case `UCI`
- case `All`

#### Aliases
`flower.SupportedDataset`