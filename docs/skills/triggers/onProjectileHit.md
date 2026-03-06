# onProjectileHit（特殊飛び道具命中トリガー）

## 概要

モブの特殊飛び道具（トライデント、スノーボール、ウィザースカル、ラマのツバなど）がエンティティに命中したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は命中されたエンティティを指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.damage-amount>` | ダメージ量 |
| `<skill.var.damage-type>` | ダメージの種類 |
| `<skill.var.damage-cause>` | ダメージの原因 |

## 対応飛び道具

| キャスタータイプ | 飛び道具 |
|---|---|
| BLAZE | SMALL_FIREBALL（小ファイアボール） |
| ENDER_DRAGON | DRAGON_FIREBALL（ドラゴンファイアボール） |
| GHAST | FIREBALL（ファイアボール） |
| LLAMA | LLAMA_SPIT（ラマのツバ） |
| WITHER | WITHER_SKULL（ウィザースカル） |
| DROWNED | TRIDENT（トライデント） |
| SNOW_GOLEM | SNOWBALL（スノーボール） |

## エイリアス

- `~onProjectile_Hit`
- `~onTrident_Hit`
- `~onTridentHit`

## 使い方

```yml
モブ名:
  Type: <対応モブタイプ>
  Skills:
    - <メカニック> ~onProjectileHit
```

## 例

```yml
NotYourAverageDrowned:
  Type: DROWNED
  Equipment:
    - TRIDENT HAND
  Skills:
  # トライデントが命中したとき、ダメージを3倍に変更（同期実行）
  - modifyDamage{a=3;modifier=MULTIPLY;sync=true} ~onProjectileHit
```

```yml
強力なガスト:
  Type: GHAST
  Display: '&f強力なガスト'
  Health: 200
  Skills:
    # ファイアボール命中時にダメージを与える
    - damage{a=20} @trigger ~onProjectileHit
    # 命中時に燃焼効果を付与
    - setfire{d=5} @trigger ~onProjectileHit
    # 命中時にメッセージ
    - message{m="&f[ガスト] 炎の洗礼を！"} @World ~onProjectileHit
```

```yml
氷のスノーゴーレム:
  Type: SNOW_GOLEM
  Display: '&b氷のゴーレム'
  Health: 30
  Skills:
    # スノーボール命中時に鈍化効果を付与
    - potion{t=SLOW;d=60;l=2} @trigger ~onProjectileHit
    # 命中時にパーティクル
    - particle{p=SNOWBALL;amount=20;hs=0.3;vs=0.3} @trigger ~onProjectileHit
```

## 関連情報

- 弓矢がエンティティに命中したとき → [`~onBowHit`](onBowHit.md)
- 特殊飛び道具がブロックに着弾したとき → [`~onProjectileLand`](onProjectileLand.md)
- 射撃時 → [`~onShoot`](onShoot.md)
