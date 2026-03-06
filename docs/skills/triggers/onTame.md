# onTame（テイムトリガー）

## 概要

プレイヤーがモブをテイム（手懐け）したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はモブをテイムしたプレイヤーを指します。

## 使い方

```yml
モブ名:
  Type: <テイム可能なモブタイプ>
  Skills:
    - <メカニック> ~onTame
```

## 例

```yml
EXAMPLE_MOB:
  Type: WOLF
  Skills:
    # プレイヤーがモブをテイムしたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=I GOT TAMED} @World ~onTame
```

```yml
神秘の狼:
  Type: WOLF
  Display: '&b神秘の狼'
  Health: 50
  Skills:
    # テイム成功時にテイムしたプレイヤーに特別メッセージ
    - message{m="&b[狼] 主人よ、どこまでもついていきます..."} @trigger ~onTame
    # テイム時にパーティクルを表示
    - particle{p=HEART;amount=10;hs=0.5;vs=0.5} @self ~onTame
    # テイム時に全体にアナウンス
    - message{m="&b<trigger.name> が神秘の狼をテイムした！"} @World ~onTame
    # テイムしたプレイヤーにバフを付与
    - potion{t=LUCK;d=600;l=1} @trigger ~onTame
```

## 注意

- テイム可能なモブ（Wolf、Cat、Parrot など）にのみ有効です。
- `@trigger` を使用することで、テイムしたプレイヤーを対象にスキルを実行できます。

## 関連情報

- 繁殖時 → [`~onBreed`](onBreed.md)
- インタラクト時 → [`~onInteract`](onInteract.md)
