# onProjectileLand（特殊飛び道具着弾トリガー）

## 概要

モブの特殊飛び道具（トライデント、スノーボール、ウィザースカル、ラマのツバなど）がエンティティに命中せずにブロック（地面）に着弾したときにスキルを実行します。

## 対応飛び道具

[`~onProjectileHit` の対応飛び道具を参照](/Skills/Triggers/onProjectileHit#compatible-projectiles)

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

- `~onProjectile_Land`
- `~onTridentLand`

## 使い方

```yml
モブ名:
  Type: <対応モブタイプ>
  Skills:
    - <メカニック> ~onProjectileLand
```

## 例

```yml
YourAverageDrowned:
  Type: DROWNED
  Equipment:
  - TRIDENT HAND
  Skills:
  # トライデントがブロックに着弾したとき、現在のターゲットにメッセージ
  - message{m="Awww..."} @target ~onProjectileLand
```

```yml
着弾爆発ガスト:
  Type: GHAST
  Display: '&f爆発ガスト'
  Health: 150
  Skills:
    # ファイアボールが地面に着弾したとき
    - explosion{yield=3} @origin ~onProjectileLand
    - particle{p=EXPLOSION_LARGE;amount=5} @origin ~onProjectileLand
    - message{m="&f[ガスト] 惜しい！"} @self ~onProjectileLand
```

```yml
地雷スノーゴーレム:
  Type: SNOW_GOLEM
  Display: '&b地雷ゴーレム'
  Health: 20
  Skills:
    # スノーボールが地面に着弾したとき
    - particle{p=SNOWBALL;amount=30;hs=1;vs=0.5} @origin ~onProjectileLand
    # 着弾点周囲のエンティティを鈍化
    - potion{t=SLOW;d=40;l=1} @PlayersInRadius{r=3} ~onProjectileLand
```

## 注意

- このトリガーはエンティティに命中せずにブロックに着弾した場合にのみ発火します。
- エンティティに命中した場合は `~onProjectileHit` が発火します。

## 関連情報

- 特殊飛び道具がエンティティに命中したとき → [`~onProjectileHit`](onProjectileHit.md)
- 弓矢がエンティティに命中したとき → [`~onBowHit`](onBowHit.md)
- 射撃時 → [`~onShoot`](onShoot.md)
