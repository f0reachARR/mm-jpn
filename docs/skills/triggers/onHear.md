# onHear（聴覚トリガー）

## 概要

モブが音を聞いたときにスキルを実行します。  
この機能を使用するには、[モブの設定で Hearing（聴覚）を有効にする](/Mobs/Mobs#hearing) 必要があります。

`<skill.var.volume>` プレースホルダーを使用すると、音源からの距離を表す 1〜15 の浮動小数点値を取得できます。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は音を発生させたエンティティを指します。

> **[@origin](/Skills/Targeters/Origin) ターゲター**は音が発生した場所を指します。

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.volume>` | 音量（距離を表す 1〜15 の値） |
| `<skill.var.sound-type>` | 音の種類 |

## エイリアス

- `~onVibration`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Hearing:
    Enabled: true
  Skills:
    - <メカニック> ~onHear
```

## 例

```yml
ICanHearYou:
  Type: ZOMBIE
  Hearing:
    Enabled: true
  Skills:
  - message{m="I can hear you <trigger.name>! <skill.var.volume>? Way too loud!"} @trigger ~onHear
```

```yml
聴覚鋭いゾンビ:
  Type: ZOMBIE
  Display: '&7鋭い耳のゾンビ'
  Health: 80
  Hearing:
    Enabled: true
  Skills:
    # 音を聞いたとき、音源の方向を向く
    - lookAt @origin ~onHear
    # 音量が大きい（近い）場合、音源に向かって移動
    - skill{s=[
      - speak{m="&7音がする！"}
      - gotoLocation @origin
      ]} ~onHear ?varGreater{var=skill.var.volume;value=10}
    # 音の種類を表示
    - message{m="音の種類: <skill.var.sound-type>"} @self ~onHear
```

## 注意

- `Hearing.Enabled: true` をモブの設定に追加しないとこのトリガーは機能しません。
- `<skill.var.volume>` は音源から遠いほど小さな値（1に近づく）を、近いほど大きな値（15に近づく）を返します。
- サーバーのパフォーマンスを考慮して、聴覚の範囲設定に注意してください。

## 関連情報

- [モブの Hearing 設定](/Mobs/Mobs#hearing)
- テレポート時 → [`~onTeleport`](onTeleport.md)
