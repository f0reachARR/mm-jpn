# Hit（物理攻撃シミュレーション）

## 説明

モブからの物理的なヒットをシミュレートします。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| multiplier | m | \1の名前 | 1 |
| forcedDamage | fd, forced | If this attribute is set, the one specified will be the amount of flat damage that will be inflicted, without consideration for attribute modifiers and similar other modifiers |  |
| triggerSkills | ts | Whether the damage mechanic should also be able to trigger `onAttack` related triggers | true |
| scaleByAttackCooldown | sbac | するかどうか | false |

## エイリアス

- [x] physicalDamage
- [x] meleeHit
<!--TAGS-->
<!--tag:Damage-->
