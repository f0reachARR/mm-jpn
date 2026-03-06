# onExplode（爆発トリガー）

## 概要

モブが爆発したときにスキルを実行します。

`mobGriefing` ゲームルールが `true` に設定されている必要があります。  
基本的に、実際に爆発するモブはクリーパーとTNTのみであるため、このトリガーはそれらにのみ有効です。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は関連しません。

## 使い方

```yml
モブ名:
  Type: CREEPER
  Skills:
    - <メカニック> ~onExplode
```

## 例

```yml
EXAMPLE_MOB:
  Type: CREEPER
  Skills:
    # モブが爆発したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=EXPLODE} @World ~onExplode
```

```yml
スーパークリーパー:
  Type: CREEPER
  Display: '&c&lスーパークリーパー'
  Health: 30
  Skills:
    # 爆発時に大きなサウンドを再生
    - sound{s=entity.generic.explode;v=5;pi=0.5} @World ~onExplode
    # 爆発時にアナウンス
    - message{m="&c&l[!] スーパークリーパーが爆発した！"} @World ~onExplode
    # 爆発時にファイアワークを打ち上げ（演出）
    - firework{} @self ~onExplode
```

## 注意

- `mobGriefing` が `false` の場合、爆発イベント自体が発火しないため、このトリガーも機能しません。
- クリーパーの点火（起爆準備）を検知するには `~onPrime` を使用してください。
- クリーパーが帯電するときは `~onCreeperCharge` を使用してください。

## 関連情報

- クリーパーが起爆準備をしたとき → [`~onPrime`](onPrime.md)
- クリーパーが帯電したとき → [`~onCreeperCharge`](onCreeperCharge.md)
