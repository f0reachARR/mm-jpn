# PercentDamage（割合ダメージ）

## 説明

ターゲットの最大HPの割合のダメージを与えます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| amount | a | 与えるダメージ割合（例：0.1 = 10%） | 0.1 |
| ignoreArmor | ia, i | 防具を無視するか | false |
| preventknockback | pkb, pk | ノックバックを防止するか | false |
| preventimmunity | pi | ダメージ無敵tickを防止するか | false |
| damagecause | dc, cause | ダメージの原因 | entity_attack |

## 使用例

```yaml
  Skills:
  - percentdamage{amount=0.1} @target ~onTimer:20
```

## エイリアス
- [x] pd
