# onSpawn（スポーントリガー）

## 概要

モブがスポーンしたときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は関連しません（スポーン時に攻撃者などは存在しないため）。

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onSpawn)
- [MythicRPG](https://git.lumine.io/mythiccraft/mythicrpg/-/wikis/Skills/Triggers/onSpawn)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onSpawn
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブがスポーンしたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=SPAWN} @World ~onSpawn
```

```yml
ボスモンスター:
  Type: WITHER
  Display: '&4&lウィザーボス'
  Health: 1000
  Skills:
    # スポーン時にアナウンスを表示
    - message{m="&4&l[!] ウィザーボスが降臨した！"} @World ~onSpawn
    # スポーン時にパーティクルを表示
    - particle{p=EXPLOSION_LARGE;amount=20;hs=2;vs=2} @self ~onSpawn
    # スポーン時にサウンドを再生
    - sound{s=entity.wither.spawn;v=2;pi=0.5} @World ~onSpawn
    # スポーン時にポーション効果を付与（バフ）
    - potion{t=INCREASE_DAMAGE;d=200;l=2} @self ~onSpawn
```

## 関連情報

- サーバー再起動後のロード時 → [`~onLoad`](onLoad.md)
- スポーンまたはロード時 → [`~onSpawnOrLoad`](onSpawnOrLoad.md)
- スポーナーから初めてスポーンしたとき → [`~onReady`](onReady.md)
- 死亡時 → [`~onDeath`](onDeath.md)
