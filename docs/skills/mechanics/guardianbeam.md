# GuardianBeam（ガーディアンビーム）

## 説明

起点とターゲットの間にガーディアンビームを描画します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| duration | d | ビームの継続時間（tick単位） | 1 |

## 使用例

```yaml
  Skills:
  - guardianbeam{d=20} @target ~onTimer:5
```

## エイリアス
- [x] gbeam
- [x] effect:guardianbeam
- [x] e:guardianbeam
