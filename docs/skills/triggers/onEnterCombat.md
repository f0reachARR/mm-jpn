# onEnterCombat（戦闘開始トリガー）

## 概要

モブが戦闘状態に入ったときにスキルを実行します。

> **⚠️ [ThreatTables（脅威テーブル）](/Mobs/ThreatTables) の有効化が必要です。**

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスターを戦闘状態にさせたエンティティを指します。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Modules:
    ThreatTable: true
  Skills:
    - <メカニック> ~onEnterCombat
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Modules:
    ThreatTable: true
  Skills:
    # モブが戦闘状態に入ったとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=ENTERED COMBAT} @World ~onEnterCombat
```

```yml
エリートナイト:
  Type: ZOMBIE
  Display: '&c&lエリートナイト'
  Health: 300
  Modules:
    ThreatTable: true
  Skills:
    # 戦闘開始時に咆哮
    - speak{m="&c貴様、覚悟しろ！"} ~onEnterCombat
    # 戦闘開始時に戦闘バフを付与
    - potion{t=INCREASE_DAMAGE;d=600;l=1} @self ~onEnterCombat
    - potion{t=SPEED;d=600;l=1} @self ~onEnterCombat
    # 戦闘開始時にアナウンス
    - message{m="&c[!] エリートナイトが <trigger.name> と戦闘を開始した！"} @World ~onEnterCombat
```

## 注意

- このトリガーは ThreatTable を有効にしないと機能しません。
- `~onDropCombat` と組み合わせることで、戦闘状態の管理が可能です。

## 関連情報

- 戦闘離脱時 → [`~onDropCombat`](onDropCombat.md)
- ターゲット変更時 → [`~onChangeTarget`](onChangeTarget.md)
- [ThreatTables の設定](/Mobs/ThreatTables)
