# onPrime（起爆準備トリガー）

## 概要

クリーパーが起爆準備状態になったときにスキルを実行します。  
例えば、火打ち石と打ち金（Flint and Steel）で点火されたときなどに発火します。

モブタイプは **CREEPER** である必要があります。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスター自身を指します。

## 使い方

```yml
モブ名:
  Type: CREEPER
  Skills:
    - <メカニック> ~onPrime
```

## 例

```yml
EXAMPLE_MOB:
  Type: CREEPER
  Skills:
    # クリーパーが起爆準備したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m="OOO I'M GONNA EXPLODE"} @World ~onPrime
```

```yml
爆発クリーパー:
  Type: CREEPER
  Display: '&c爆発クリーパー'
  Health: 20
  Skills:
    # 起爆準備時に警告音を再生
    - sound{s=entity.creeper.primed;v=3} @World ~onPrime
    # 起爆準備時に周囲に警告メッセージ
    - message{m="&c[!] 爆発まであと少し！逃げろ！"} @PIR{r=20} ~onPrime
    # 起爆準備時にパーティクルを表示
    - particle{p=SMOKE_LARGE;amount=20;hs=0.5;vs=1} @self ~onPrime
```

## 注意

- このトリガーはクリーパー（CREEPER）タイプのモブにのみ機能します。
- 実際の爆発は `~onExplode` で検知できます。

## 関連情報

- 爆発時 → [`~onExplode`](onExplode.md)
- 帯電時 → [`~onCreeperCharge`](onCreeperCharge.md)
