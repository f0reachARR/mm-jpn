# ArrowVolley（矢の一斉射撃）

## 説明

矢を一斉射撃します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| arrows | amount, a | 発射する矢の本数 | 20 |
| spread | s | 矢の広がり角度（度数） | 15 |
| velocity | v | 矢の速度 | 10 |
| fireTicks | ft, fire | 矢に付与する炎上tick数 | 0 |
| skill | onHitSkill | 矢がヒットしたときに実行するスキル | |
| type | t | 矢の種類 | ARROW |

## 使用例

```yaml
  Skills:
  - arrowvolley{arrows=30;spread=20;velocity=8;fireTicks=60} @target ~onTimer:20
```

## エイリアス
- [x] av
- [x] volleyofar
