# onChangeTarget（ターゲット変更トリガー）

## 概要

モブのターゲットが変わったときにスキルを実行します。

> **⚠️ [ThreatTables（脅威テーブル）](/Mobs/ThreatTables) の有効化が必要です。**

## エイリアス

- `~onTargetChange`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Modules:
    ThreatTable: true
  Skills:
    - <メカニック> ~onChangeTarget
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Modules:
    ThreatTable: true
  Skills:
    # モブのターゲットが変わったとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=Target Changed} @World ~onChangeTarget
```

```yml
タクティカルゾンビ:
  Type: ZOMBIE
  Display: '&aタクティシャン'
  Health: 250
  Modules:
    ThreatTable: true
  Skills:
    # ターゲット変更時にメッセージ
    - speak{m="&a新しいターゲットを発見！"} ~onChangeTarget
    # ターゲット変更時に新ターゲットに向けて突進
    - dash{d=1;v=1.5} @target ~onChangeTarget
```

## 注意

- このトリガーは ThreatTable を有効にしないと機能しません。
- ThreatTableによって脅威値が変動し、最大脅威のエンティティへターゲットが切り替わった際に発火します。

## 関連情報

- 戦闘開始時 → [`~onEnterCombat`](onEnterCombat.md)
- 戦闘離脱時 → [`~onDropCombat`](onDropCombat.md)
- [ThreatTables の設定](/Mobs/ThreatTables)
