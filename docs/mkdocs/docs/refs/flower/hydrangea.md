# hydrangea

`hydrangea` is a sub-framework for `flower`. In `hydrangea`, Attention modules and models that can insert the Attention module have been implemented. The models with attention are based on [`tfgarden`](https://github.com/Shakshi3104/tfgarden).

## Models
`flower.hydrangea.models`

- `Li2018`
- `Li2018WithAttention`
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