# Firework（花火）

## 説明

ターゲットに花火エフェクトを作成します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| type | t | 花火の種類（下記一覧参照） | BALL |
| power | p, duration, d | 花火ロケットの飛行時間 | 2 |
| flicker | f | 爆発エフェクトにちらつきを追加するか | false |
| trail | tr | 花火ロケットにトレイルエフェクトを追加するか | false |
| colors | color, c | 花火爆発の色（RGB または HEX 形式） | #FFFFFF |
| fadecolors | fcolors, fc | 花火爆発のフェードカラー（RGB または HEX 形式） | #FFFFFF |

### type 属性の値
- `BALL`
- `BALL_LARGE`
- `BURST`
- `CREEPER`
- `STAR`

## 使用例

```yaml
  Skills:
  - effect:firework{t=BALL;d=1;f=true;tr=true} @self ~onInteract
```

## エイリアス
- [x] fireworks
- [x] effect:firework
- [x] effect:fireworks
- [x] e:firework
