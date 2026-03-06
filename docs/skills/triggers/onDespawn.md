# onDespawn（デスポーントリガー）

## 概要

モブがデスポーン（消滅）したときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスター自身を指します。

## エイリアス

- `~onDespawned`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onDespawn
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブがデスポーンしたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=DESPAWNED} @World ~onDespawn
```

```yml
幽霊モブ:
  Type: PHANTOM
  Display: '&7幽霊'
  Health: 30
  Skills:
    # デスポーン時にメッセージを表示
    - message{m="&7幽霊が消えていった..."} @World ~onDespawn
    # デスポーン時にパーティクルを演出
    - particle{p=SMOKE_LARGE;amount=30;hs=1;vs=1} @self ~onDespawn
```

## 注意

- `~onDespawn` はモブが自然にデスポーンするときに発火します。
- モブが死亡した場合は `~onDeath` が発火します（`~onDespawn` は発火しません）。
- `/mm m remove` などのコマンドでモブを削除した場合にも発火する可能性があります。

## 関連情報

- 死亡時 → [`~onDeath`](onDeath.md)
- スポーン時 → [`~onSpawn`](onSpawn.md)
