# onTrade（取引トリガー）

## 概要

ヴィレッジャーがプレイヤーと取引（トレード）を完了したときにスキルを実行します。

> **⚠️ Paperサーバーが必要です。**

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はヴィレッジャーと取引したプレイヤーを指します。

## 使い方

```yml
モブ名:
  Type: VILLAGER
  Skills:
    - <メカニック> ~onTrade
```

## 例

```yml
EXAMPLE_MOB:
  Type: VILLAGER
  Skills:
    # ヴィレッジャーがプレイヤーと取引したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=TRADED} @World ~onTrade
```

```yml
魔法商人:
  Type: VILLAGER
  Display: '&d魔法商人'
  Health: 30
  Options:
    Invincible: true
  Skills:
    # 取引完了時に取引者にメッセージ
    - message{m="&d[商人] ありがとうございます、<trigger.name> 様！またのご利用をお待ちしております。"} @trigger ~onTrade
    # 取引完了時にパーティクル演出
    - particle{p=VILLAGER_HAPPY;amount=10;hs=0.5;vs=0.5} @self ~onTrade
    # 取引回数をカウントし、5回ごとに特別報酬
    - skill{s=取引報酬} @trigger ~onTrade
```

## 注意

- このトリガーは **Paperサーバー** でのみ機能します（Spigotでは動作しません）。
- ヴィレッジャー（VILLAGER）タイプのモブにのみ有効です。
- `@trigger` を使用することで、取引したプレイヤーを対象にできます。

## 関連情報

- インタラクト時 → [`~onInteract`](onInteract.md)
- テイム時 → [`~onTame`](onTame.md)
