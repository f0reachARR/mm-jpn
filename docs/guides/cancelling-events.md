# ガイド: イベントのキャンセル

このガイドでは、モブのデフォルト動作を完全に削除し、独自のカスタムスキルに置き換える方法を説明します。

## 概要

`cancelevent`メカニクスを使用すると、モブのデフォルトイベントをキャンセルし、代わりにカスタム動作を実行できます。

## 近接攻撃のキャンセル

デフォルトの近接攻撃をキャンセルして、カスタムスキルに置き換えます：

```yaml
CustomAttackMob:
  Type: ZOMBIE
  Display: '&cカスタム攻撃ゾンビ'
  Health: 100
  Options:
    PreventVanillaDamage: true  # バニラダメージを防ぐ
  Skills:
  - skill{s=CustomMeleeAttack} @trigger ~onAttack
```

```yaml
CustomMeleeAttack:
  Skills:
  - damage{amount=15;ignorearmor=true} @trigger   # カスタムダメージ
  - potioneffect{type=POISON;d=60;l=1} @trigger   # ポイズン効果
  - sound{s=entity.zombie.attack_iron_door} @trigger
```

## 死亡イベントのキャンセル

モブの死亡をキャンセルして、「復活」機能を実装します：

```yaml
RevivableBoss:
  Type: WITHER_SKELETON
  Display: '&5不死身のボス'
  Health: 500
  Options:
    ReviveHealth: 250  # 復活時のHP
  Skills:
  - skill{s=ReviveEffect} @self ~onDeath

ReviveEffect:
  Skills:
  - cancelevent{sync=true} @self  # 死亡をキャンセル
  - effect:particles{p=SPELL_WITCH;amount=50} @self
  - sound{s=entity.witch.celebrate;volume=2}
  - message{m="&5不死身のボスが復活した！"} @PlayersInRadius{r=50}
```

## スポーン時の動作キャンセル

モブが通常の動作を行わないようにします（例：攻撃しない観察者）：

```yaml
ObserverMob:
  Type: ZOMBIE
  Display: '&7観察者'
  Health: 1000
  Options:
    Invincible: true
    NoAI: false
    MovementSpeed: 0  # 移動しない
    PreventVanillaDamage: true  # ダメージを与えない
  AIGoalSelectors:
  - clear
  - lookatplayers
  AITargetSelectors:
  - clear
```

## 爆発のキャンセル（クリーパー）

クリーパーが爆発するのをキャンセルして、代わりにカスタムスキルを実行します：

```yaml
CustomCreeper:
  Type: CREEPER
  Display: '&aカスタムクリーパー'
  Health: 20
  Skills:
  - skill{s=CustomExplosion} @self ~onExplode
  - cancelevent{sync=true} @self ~onExplode

CustomExplosion:
  Skills:
  - fakeexplosion @self  # 見た目だけの爆発
  - damage{amount=30;ignorearmor=true} @PlayersInRadius{r=4}
  - throw{velocity=15;velocityY=8} @PlayersInRadius{r=4}
  - suicide @self  # 自分自身を削除
```
