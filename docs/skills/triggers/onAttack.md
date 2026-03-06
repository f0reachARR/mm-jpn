# onAttack（攻撃トリガー）

## 概要

モブがエンティティを攻撃したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は攻撃された（ダメージを受けた）エンティティを指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.damage-amount>` | ダメージ量 |
| `<skill.var.damage-type>` | ダメージの種類 |
| `<skill.var.damage-cause>` | ダメージの原因 |

## エイリアス

- `~onHit`

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onAttack)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onAttack
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Damage: 1
  Skills:
    # モブが何かを攻撃したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=ATTACK} @World ~onAttack
```

```yml
強化スケルトン:
  Type: SKELETON
  Display: '&c強化スケルトン'
  Health: 50
  Damage: 5
  Skills:
    # 攻撃時にダメージ量をチャットに表示
    - message{m="<trigger.name> に <skill.var.damage-amount> ダメージを与えた！"} @World ~onAttack
    # 攻撃時にパーティクルエフェクトを表示
    - particle{p=CRIT;amount=10} @trigger ~onAttack
```

## 関連情報

- ダメージを受けたとき → [`~onDamaged`](onDamaged.md)
- 矢が命中したとき → [`~onBowHit`](onBowHit.md)
