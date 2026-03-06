# DisguiseModify（変装変更）

## 説明

キャスターに既に適用されている変装を変更します。LibsDisguises プラグインが必要です。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| skin | s | 新しいスキン名 | |
| name | n | 新しい表示名 | |

## 使用例

```yaml
  Skills:
  - disguisemodify{skin=Steve;name="NewName"} @self ~onTimer:100
```

## エイリアス
- [x] dm
- [x] modifydisguise
