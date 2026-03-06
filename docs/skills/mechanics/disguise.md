# Disguise（変装）

## 説明

キャスターの変装（ディスガイズ）を変更します。LibsDisguises プラグインが必要です。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| disguise | d | 変装の種類 | |
| skin | s | スキン名（プレイヤー変装の場合） | |
| name | n | 変装の表示名 | |
| unseeableRange | ur | 変装が見えなくなる範囲 | |
| showName | sn | 名前を表示するか | true |
| dynamicName | dn | 名前を動的に更新するか | false |

## 使用例

```yaml
  Skills:
  - disguise{d=Player;skin=Notch} @self ~onSpawn
  - disguise{d=CREEPER} @self ~onDamaged
```

## エイリアス
- [x] d
