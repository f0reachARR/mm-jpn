# BaseDamage（基本ダメージ割合ダメージ）

## 説明

モブのダメージステータスの割合をターゲットに与えます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| multiplier | m | モブのダメージステータスへの乗数 | 1 |
| ignoreArmor | ia, i | 防具を無視するか | false |
| preventknockback | pkb, pk | ノックバックを防止するか | false |
| preventimmunity | pi | ダメージ無敵tickを防止するか | false |
| damagecause | dc, cause | ダメージの原因 | entity_attack |

## 使用例

```yaml
  Skills:
  - basedamage{m=1.5} @target ~onTimer:20
```

## エイリアス
- [x] bd
