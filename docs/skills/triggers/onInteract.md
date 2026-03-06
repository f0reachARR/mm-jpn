# onInteract（インタラクトトリガー）

## 概要

プレイヤーがモブを右クリックしたときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスターと交流したプレイヤーを指します。

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onInteract)
- [MythicRPG](https://git.lumine.io/mythiccraft/mythicrpg/-/wikis/Skills/Triggers/onInteract)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onInteract
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # プレイヤーがモブを右クリックしたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=INTERACTED} @World ~onInteract
```

```yml
NPCヴィレッジャー:
  Type: VILLAGER
  Display: '&e商人ジョン'
  Health: 20
  Options:
    Invincible: true
    PreventOtherDrops: true
  Skills:
    # 右クリック時にプレイヤーに挨拶
    - message{m="&e[商人] いらっしゃい、<trigger.name> さん！"} @trigger ~onInteract
    # 右クリック時にメニューを開く（MythicCrucible との連携）
    - skill{s=商人メニューを開く} @trigger ~onInteract
```

```yml
シグナル送信モブ:
  Type: CHICKEN
  Skills:
    # 右クリックされたとき、周囲64ブロック内の全MythicMobエンティティにシグナルを送信
    - signal{s=MOO_FOR_ME} @EIR{r=64} ~onInteract
```

## 関連情報

- シグナル受信時 → [`~onSignal`](onSignal.md)
- 取引時 → [`~onTrade`](onTrade.md)
