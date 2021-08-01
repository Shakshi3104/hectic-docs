# hydrangea

`hydrangea` is a sub-framework for `flower`. In `hydrangea`, Attention modules and models that can insert the Attention module have been implemented. The models with attention are based on [`tfgarden`](https://github.com/Shakshi3104/tfgarden). See `tfgarden` for reference papers of models other than Li2018.

## Models
`flower.hydrangea.models`

- `Li2018`
- `Li2018WithAttention`
    - Reference: [Comparison of Feature Learning Methods for Human Activity Recognition Using Wearable Sensors](https://www.mdpi.com/1424-8220/18/2/679) (Sensors, Vol.18, No. 679, 2019)
- `VGG16WithAttention`
- `InceptionV3WithAttention`
- `ResNet18WithAttention`
- `PyramidNet18WithAttention`
- `XceptionWithAttention`
- `DenseNet121WithAttention`
- `MobileNetWithAttention`
- `MobileNetV2WithAttention`
- `MobileNetV3SmallWithAttention`
- `NASNetMobileWithAttention`
- `MnasNetWithAttention`
- `EfficientNetB0WithAttention`
- `EfficientNet_lite0WithAttention`

## Attention
`flower.hydrangea.attention`

- `SqueezeAndExcite`
- `SelectiveKernel`
- `ConvBlockAttention`

### flower.hydrangea.attention.SqueezeAndExcite

```python
SqueezeAndExcite(filters, se_ratio=0.25, block_name="")
```
Reference:

- [Squeeze-and-Excitation Networks](https://arxiv.org/abs/1709.01507) (CVPR 2015)

#### Arguments
- filters: 出力フィルタサイズ
- se_ratio: 入力フィルタを絞る比率, 0 < se_ratio <= 1
- block_name: ブロック名

### flower.hydrangea.attention.SelectiveKernel

```python
SelectiveKernel(filters, block_name="")
```
Reference:

- [Selective Kernel Networks](https://arxiv.org/abs/1903.06586) (CVPR 2019)

#### Arguments
- filters: 出力フィルタサイズ
- block_name: ブロック名

### flower.hydrangea.attention.ConvBlockAttention

```python
ConvBlockAttention(filters, ratio=0.125, block_name="")
```

Reference:

- [CBAM: Convolutinal Block Attention Module](https://arxiv.org/abs/1807.06521) (ECCV 2018)

#### Arguments
- filters: 出力フィルタサイズ
- ratio: 入力フィルタを絞る比率, 0 < ratio <= 1
- block_name: ブロック名

### flower.hydrangea.attention.ChannelAttention

```python
ChannelAttention(filters, ratio=0.125, block_name="")
```

#### Arguments
- filters: 出力フィルタサイズ
- ratio: 入力フィルタを絞る比率, 0 < ratio <= 1
- block_name: ブロック名

### flower.hydrangea.attention.SpatialAttention

```python
SpatialAttention(block_name="")
```

#### Arguments
- block_name: ブロック名

