# onBowHit（弓矢命中トリガー）

## 概要

モブが発射したプロジェクタイル（矢など）がエンティティに命中したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は命中されたエンティティを指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.damage-amount>` | ダメージ量 |
| `<skill.var.damage-type>` | ダメージの種類 |
| `<skill.var.damage-cause>` | ダメージの原因 |

## エイリアス

- `~onBow_Hit`
- `~onArrowHit`

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onBowHit)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Equipment:
    - BOW HAND
  Skills:
    - <メカニック> ~onBowHit
```

## 例

```yml
NotYourAverageSkeleton:
  Type: SKELETON
  Equipment:
    - BOW HAND
  Skills:
  # 矢が命中したとき、ダメージを3倍に変更（同期実行）
  - modifyDamage{a=3;modifier=MULTIPLY;sync=true} ~onBowHit
```

```yml
毒矢スケルトン:
  Type: SKELETON
  Display: '&2毒矢スケルトン'
  Health: 50
  Equipment:
    - BOW HAND
  Skills:
    # 矢命中時に毒ポーション効果を付与
    - potion{t=POISON;d=100;l=1} @trigger ~onBowHit
    # 矢命中時にメッセージ
    - message{m="&2<trigger.name> を毒矢で射った！"} @World ~onBowHit
    # ダメージ量を表示
    - message{m="ダメージ: <skill.var.damage-amount>"} @self ~onBowHit
```

## 関連情報

- 射撃時 → [`~onShoot`](onShoot.md)
- 特殊飛び道具がエンティティに命中したとき → [`~onProjectileHit`](onProjectileHit.md)
- 特殊飛び道具がブロックに着弾したとき → [`~onProjectileLand`](onProjectileLand.md)
