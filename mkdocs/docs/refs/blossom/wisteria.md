# wisteria

`wisteria` is a sub-framework. In `wisteria`, hand-kneaded models  for building the lightweight model have been implemented.

## Models

`blossom.wisteria.models`

- `PyramidEfficientNetB0`: EfficientNet B0にPyramidNetっぽいフィルタ数の増やし方を適用したモデル
- `PyramidEfficientNetSmallA0`: Pyramid-EfficientNet B0にEfficientNet small-A0と同じブロックの削除を適用したモデル
- `PyramidEfficientNetSmallB0`: Pyramid-EfficientNet B0にEfficientNet small-B0と同じレイヤーの削除を適用したモデル
- `EfficientNetSmallA0`: EfficientNet B0のMBConvブロックの後ろ3ブロックを削除したモデル
- `EfficientNetSmallB0`: EfficientNet B0の各MBConvブロックの層を1層にしたモデル