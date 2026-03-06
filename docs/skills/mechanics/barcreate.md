# BarCreate（ボスバー作成）

## 説明

キャストしているモブにカスタムボスバーを作成します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| name | n | ボスバーの識別名 | |
| display | title, d, t | ボスバーに表示するテキスト | |
| value | v | ボスバーの初期値（0〜1） | 1 |
| color | c | ボスバーの色（`PINK`、`BLUE`、`RED`、`GREEN`、`YELLOW`、`PURPLE`、`WHITE`） | PURPLE |
| style | s | ボスバーのスタイル（`SOLID`、`SEGMENTED_6`、`SEGMENTED_10`、`SEGMENTED_12`、`SEGMENTED_20`） | SOLID |
| range | r | ボスバーが表示される範囲 | 0（全体） |

## 使用例

```yaml
  Skills:
  - barcreate{name=mybar;display="ボスバー";value=1;color=RED;style=SOLID} @self ~onSpawn
```

## エイリアス
- [x] bossbarcreate
- [x] createbar
