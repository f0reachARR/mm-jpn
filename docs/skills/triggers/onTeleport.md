# onTeleport（テレポートトリガー）

## 概要

モブがテレポートしたときにスキルを実行します。  
エンダーマンが自然にテレポートする動作などで発火します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は関連しません。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onTeleport
```

## 例

```yml
EXAMPLE_MOB:
  Type: ENDERMAN
  Skills:
    # モブがテレポートしたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=TELEPORT} @World ~onTeleport
```

```yml
神秘のエンダーマン:
  Type: ENDERMAN
  Display: '&5神秘のエンダーマン'
  Health: 80
  Skills:
    # テレポート時にパーティクルを表示
    - particle{p=PORTAL;amount=30;hs=0.5;vs=1} @self ~onTeleport
    # テレポート時にサウンドを再生
    - sound{s=entity.enderman.teleport;v=2} @self ~onTeleport
    # テレポート時に近くのプレイヤーにポーション効果を付与
    - potion{t=BLINDNESS;d=40;l=1} @PIR{r=5} ~onTeleport
```

## 注意

- このトリガーはエンダーマンやその他テレポート能力を持つモブに特に有用です。
- `teleport` メカニックによるテレポートでもこのトリガーが発火します。

## 関連情報

- スポーン時 → [`~onSpawn`](onSpawn.md)
