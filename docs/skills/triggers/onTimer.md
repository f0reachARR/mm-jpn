# onTimer（タイマートリガー）

## 概要

指定したティック数ごとに定期的にスキルを実行します。

**特殊な構文：** `~onTimer:<ティック数>`

- **ティック数は 0 にできません**。
- 20 ティック = 1 秒です。
- このトリガーはモブのスポーン時刻ではなく、**グローバルクロック**に基づきます。  
  例えば `~onTimer:1000` を設定した場合、最初の実行はモブのスポーン後 0 〜 1000 ティックの任意のタイミングになります。

> **警告：** このトリガーの乱用はサーバー・クライアントのパフォーマンス低下を招く可能性があります。  
> 大量のパーティクルエフェクトなどはクライアントラグやキックの原因になります。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は関連しません。

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onTimer)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onTimer:<ティック数>
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # 0.05秒（1ティック）ごとにメッセージを送信
    - message{m="TIMER every tick (0.05 seconds)"} @World ~onTimer:1
    # 2秒（40ティック）ごとにメッセージを送信
    - message{m="TIMER every 40 ticks (2 seconds)"} @World ~onTimer:40
```

```yml
周期攻撃ボス:
  Type: IRON_GOLEM
  Display: '&7鉄のゴーレムボス'
  Health: 500
  Skills:
    # 5秒ごとに周囲のプレイヤーにダメージを与える
    - damage{a=10} @PIR{r=8} ~onTimer:100
    # 10秒ごとに咆哮
    - speak{m="&7ガアアア！"} ~onTimer:200
    # 30秒ごとにHPを回復
    - heal{a=50} @self ~onTimer:600
    # 3秒ごとにパーティクルを表示
    - particle{p=SMOKE_LARGE;amount=5} @self ~onTimer:60
```

## ティック換算表

| ティック数 | 時間 |
|---|---|
| 1 | 0.05 秒 |
| 20 | 1 秒 |
| 40 | 2 秒 |
| 100 | 5 秒 |
| 200 | 10 秒 |
| 600 | 30 秒 |
| 1200 | 1 分 |
| 6000 | 5 分 |

## 関連情報

- シグナル受信時 → [`~onSignal`](onSignal.md)
