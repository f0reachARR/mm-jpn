# ダメージ修飾子 (Damage Modifiers)

DamageModifiers機能を使用すると、さまざまなダメージ原因からモブが受けるダメージを変更できます。

## 構文

```yaml
internal_mobname:
  Type: <mobtype>
  DamageModifiers:
  - <DamageCause> <multiplier>
```

数値が`1`の場合はデフォルトのダメージです。`0`は免疫（ダメージなし）を意味します。
`1.5`のような1より大きい数値は通常より50%多いダメージを意味します。

## 利用可能なダメージ原因

| ダメージ原因 | 説明 |
|-----------|------|
| CONTACT | サボテンなどとの接触ダメージ |
| ENTITY_ATTACK | 他のエンティティからの近接攻撃 |
| ENTITY_SWEEP_ATTACK | エンティティのスウィープ攻撃 |
| PROJECTILE | 矢などの発射物 |
| SUFFOCATION | ブロック内に埋まったときのダメージ |
| FALL | 落下ダメージ |
| FIRE | 火のダメージ |
| FIRE_TICK | 燃焼中のダメージ |
| MELTING | 光により溶けるダメージ（スノーゴーレム） |
| LAVA | 溶岩ダメージ |
| DROWNING | 溺死ダメージ |
| BLOCK_EXPLOSION | ブロックの爆発（TNTなど）によるダメージ |
| ENTITY_EXPLOSION | エンティティの爆発（クリーパーなど）によるダメージ |
| VOID | 虚空に落ちたときのダメージ |
| LIGHTNING | 雷によるダメージ |
| SUICIDE | 自殺コマンドによるダメージ |
| STARVATION | 飢餓ダメージ |
| POISON | ポーション効果によるダメージ |
| MAGIC | ポーションスプラッシュなどの魔法ダメージ |
| WITHER | ウィザー効果によるダメージ |
| FALLING_BLOCK | 落下ブロックによるダメージ |
| THORNS | トゲエンチャントによるダメージ |
| DRAGON_BREATH | エンダードラゴンの炎によるダメージ |
| CUSTOM | カスタムダメージ |
| FLY_INTO_WALL | 高速で壁に衝突したときのダメージ（イーライトラ） |
| HOT_FLOOR | マグマブロックによるダメージ |
| CRAMMING | 多数のエンティティによる圧迫ダメージ |
| DRYOUT | 水が必要なエンティティの乾燥ダメージ |
| FREEZE | 粉雪による凍結ダメージ |
| SONIC_BOOM | ウォーデンのソニックブームによるダメージ |
| WORLD_BORDER | ワールドボーダーによるダメージ |

## 例

```yaml
ArmoredZombie:
  Type: zombie
  DamageModifiers:
  - ENTITY_ATTACK 0     # 近接攻撃に免疫
  - PROJECTILE 1.25     # 矢には25%余計なダメージ
  - MAGIC 1.75          # 魔法には75%余計なダメージ
  - FIRE 0              # 火に免疫
```

```yaml
FireElemental:
  Type: blaze
  DamageModifiers:
  - FIRE 0              # 火に完全免疫
  - FIRE_TICK 0         # 燃焼に完全免疫
  - LAVA 0              # 溶岩に完全免疫
  - DROWNING 2.0        # 水に2倍のダメージ
```
