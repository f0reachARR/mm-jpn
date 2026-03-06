# onBreed（繁殖トリガー）

## 概要

モブが別のモブと繁殖したときにスキルを実行します。

> このトリガーでは [`@Father`](/Skills/Targeters/Father) と [`@Mother`](/Skills/Targeters/Mother) ターゲターが使用できます。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスターを繁殖させたプレイヤーを指します。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onBreed
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブが繁殖したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m="LET'S GET THIS BREAD"} @World ~onBreed
```

```yml
ファームチキン:
  Type: CHICKEN
  Display: '&aファームチキン'
  Health: 10
  Skills:
    # 繁殖時にメッセージ
    - message{m="&a新しいチキンが誕生した！"} @World ~onBreed
    # 繁殖させたプレイヤーに報酬
    - giveitem{i=GOLDEN_EGG;amount=1} @trigger ~onBreed
    # パーティクル演出
    - particle{p=HEART;amount=5} @self ~onBreed
```

## 関連情報

- テイム時 → [`~onTame`](onTame.md)
- [`@Father` ターゲター](/Skills/Targeters/Father)
- [`@Mother` ターゲター](/Skills/Targeters/Mother)
