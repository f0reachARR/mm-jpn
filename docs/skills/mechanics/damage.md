# Damage（ダメージ）

## 説明

ターゲットエンティティにダメージを与えます。

## 属性

### 非継承属性
| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| amount | a | 与えるダメージ量 | 1 |

### 継承属性
| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| ignoreArmor | ia, i | 防具を無視するか（エンチャントの補正は依然として適用される） | false |
| preventknockback | pkb, pk | ノックバックを防止するか | false |
| preventimmunity | pi | ダメージ後のターゲットの[ダメージ無敵tick]を0にするか | false |
| damagecause | dc, cause | このダメージメカニックのダメージ原因（1.17以上で使用可能） | entity_attack |
| ignoreenchantments | ignoreenchants, ie | エンチャント補正を無視するか（1.19以上で使用可能） | false |
| noanger | na | ダメージ時にエンティティを怒らせないか | false |
| ignoreinvulnerability | ignoreinvulnerable, ii | ダメージ前にターゲットの[ダメージ無敵tick]を0にするか | false |
| ignoreshield | is | ターゲットのシールドブロックを無視するか | false |
| damageshelmet | dh | ヘルメットにダメージを与えるか | false |
| ignoreeffects | ieff | エフェクトを無視するか | false |
| ignoreresistance | ir | 耐性を無視するか | false |
| poweraffectsdamage | pad | スキルのパワーがダメージに影響するか | true |
| tags | tag | ダメージに任意のタグを設定（カンマ区切り、大文字化される） | |
| rawtags | rtag | tags と同様だが大文字化されない | |
| damagetype | element, e | タグの一つになる | |
| triggerSkills | ts | ダメージメカニックが `onAttack` 関連トリガーを発火できるか | false |
| bonusdamage | | ボーナスダメージ（例：`FIRE 5,LIGHTNING 5`） | |
| bonusdamagemodifiers | bonusdamagemods | ボーナスダメージに乗じる倍率（例：`FIRE 2,LIGHTNING 2`） | |

[ダメージ無敵tick]: /skills/mechanics/setnodamageticks

### DamageCause 属性
この属性は MythicMobs 5.0 以降のビルドでのみ使用可能です。  
使用可能なダメージ原因は [Spigot JavaDocs](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html) を参照してください。

> `entity_attack`、`entity_sweep_attack`、`thorns`、`sonic_boom`、`entity_explosion`、`projectile` のみがエンティティダメージャーを返します（`<trigger.name>` が "Unknown" 以外を返せる）。

### element（属性）の使い方
damage メカニックには「element」を設定する機能があります：
```yaml
- damage{amount=10;element=FIRE} @target ~onUse
- damage{amount=10;element=ICE} @target ~onUse
```

element は任意の名前が使用でき、モブの `DamageModifiers` でそのダメージタイプへの耐性を調整できます：
```yaml
DamageModTest:
  Type: COW
  DamageModifiers:
  - LIGHTNING 0.1
  - FIRE 2.0
  - AIR 1.0
  - ICE 0.5
  Skills:
  - message{m="<skill.var.damage-type> で <skill.var.damage-amount> のダメージ"} @PIR{r=50} ~onDamaged
```

### tags（属性）の使い方
```yaml
- damage{amount=5;tags=WITCHCURSE,FIRE}
```
[DamageTag](/skills/conditions/damagetag) 条件と組み合わせて使用できます。  
タグは任意の名前が使用可能です（無効な文字を除く）。

## 使用例

```yaml
  Skills:
  - damage{amount=20;ignoreArmor=true} @target ~onTimer:20
```

```yaml
FreezeBlast:
  Skills:
  - effect:sound{s=block.fire.extinguish;v=1;p=0.5} @PIR{r=6}
  - effect:particles{p=explode;a=8;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
  - effect:particles{p=drip_water;a=10;vs=0.5;hs=0.5;s=0;y=1;repeat=5;repeatInterval=20} @PIR{r=6}
  - potion{t=SLOW;d=120;l=6} @PIR{r=6}
  - damage{a=120;pkb=true} @PIR{r=6}
```

**プレミアム使用例:**
```yaml
  Skills:
  - damage{amount=<caster.var.somevariable> * 0.5 + 1} @target ~onTimer:20
```
> `<caster.var.somevariable>` の値が 5 の場合、3.5 ダメージを与えます。

## エイリアス
- [x] d
