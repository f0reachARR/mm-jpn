# onPlayerKill（プレイヤーキルトリガー）

## 概要

モブがプレイヤーを倒したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は倒されたプレイヤーを指します。

## エイリアス

- `~onKillPlayer`

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onKillPlayer)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onPlayerKill
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブがプレイヤーを倒したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=PLAYER KILLED} @World ~onPlayerKill
```

```yml
強力なドラゴン:
  Type: ENDER_DRAGON
  Display: '&5&l邪悪なドラゴン'
  Health: 3000
  Skills:
    # プレイヤーを倒したときにアナウンス
    - message{m="&5&l[!] ドラゴンが <trigger.name> を倒した！"} @World ~onPlayerKill
    # プレイヤーを倒したとき、HPを少し回復
    - heal{a=100} @self ~onPlayerKill
    # 倒されたプレイヤーをデスポット（リスポーン地点）に送る
    - command{c="spawnpoint <trigger.name>"} @self ~onPlayerKill
```

## 関連情報

- 死亡時 → [`~onDeath`](onDeath.md)
- 攻撃時 → [`~onAttack`](onAttack.md)
