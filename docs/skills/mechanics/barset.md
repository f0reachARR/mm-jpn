# BarSet（ボスバー更新）

## 説明

キャストしているモブのカスタムボスバーを変更します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| name | n | 変更するボスバーの識別名 | |
| display | title, d, t | 新しい表示テキスト | |
| value | v | 新しい値（0〜1） | |
| color | c | 新しい色 | |
| style | s | 新しいスタイル | |
| progress | p | ボスバーの進行度（0〜1） | |

## 使用例

```yaml
  Skills:
  - barset{name=mybar;value=<caster.hp>/<caster.mhp>} @self ~onTimer:5
```

## エイリアス
- [x] bossbarset
- [x] setbar
