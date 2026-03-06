# onShoot（射撃トリガー）

## 概要

モブがプロジェクタイル（飛び道具）を発射したときにスキルを実行します。  
例えば、スケルトンが弓で矢を放つとき、ガストやブレイズ、エンドラがファイアボールを放つときなどに発火します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスター自身を指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.bow-tension>` | 弓の引き絞り具合（テンション値） |

## エイリアス

- `~onBowShoot`
- `~onShootBow`

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onShoot)
- [MythicRPG](https://git.lumine.io/mythiccraft/mythicrpg/-/wikis/Skills/Triggers/onShoot)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onShoot
```

## 例

```yml
EXAMPLE_MOB:
  Type: SKELETON
  Skills:
    # スケルトンが弓から矢を射たとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=I SHOT AN ARROW} @World ~onShoot
```

```yml
エリートスナイパー:
  Type: SKELETON
  Display: '&7スナイパースケルトン'
  Health: 60
  Equipment:
    - BOW HAND
  Skills:
    # 射撃時にサウンドを再生
    - sound{s=entity.arrow.shoot;v=2} @self ~onShoot
    # 射撃時にパーティクルを表示（銃口炎演出）
    - particle{p=CRIT;amount=5;hs=0.1;vs=0.1} @self ~onShoot
    # 弓のテンションが高いときに特殊効果を発動
    - message{m="&7完全に引き絞った！"} @self ~onShoot ?varEquals{var=skill.bow-tension;value=1}
```

## 関連情報

- 矢がエンティティに命中したとき → [`~onBowHit`](onBowHit.md)
- 特殊飛び道具がエンティティに命中したとき → [`~onProjectileHit`](onProjectileHit.md)
