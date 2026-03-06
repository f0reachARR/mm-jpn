# onDamaged（被ダメージトリガー）

## 概要

モブがダメージを受けたときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はダメージを与えたエンティティを指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.damage-amount>` | 受けたダメージ量 |
| `<skill.var.damage-type>` | ダメージの種類 |
| `<skill.var.damage-cause>` | ダメージの原因 |

## エイリアス

- `~onHurt`

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onDamaged)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onDamaged
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブがダメージを受けたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=DAMAGED} @World ~onDamaged
```

```yml
タフなゾンビ:
  Type: ZOMBIE
  Display: '&2タフなゾンビ'
  Health: 200
  Skills:
    # 受けたダメージをチャットに表示
    - message{m="<skill.var.damage-amount> ダメージを受けた！攻撃者: <trigger.name>"} @World ~onDamaged
    # ダメージを受けたとき、攻撃者にポーション効果を付与
    - potion{t=POISON;d=60;l=1} @trigger ~onDamaged
    # HP が 50% 以下のとき、再生効果を発動
    - potion{t=REGENERATION;d=100;l=2} @self ~onDamaged ?health{h=<50%}
```

## 関連情報

- モブが攻撃したとき → [`~onAttack`](onAttack.md)
- モブが死亡したとき → [`~onDeath`](onDeath.md)
