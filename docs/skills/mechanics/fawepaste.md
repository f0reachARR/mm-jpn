# FawePaste（FAWEスケマティック貼り付け）

## 説明

FAWE（Fast Async World Edit）を使用してスケマティックを貼り付けます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| schematic | s, schem | 貼り付けるスケマティックファイル名 | |
| origin | o | 貼り付けの基点（`target`、`caster`、`origin`） | target |
| ignoreair | ia | 空気ブロックを無視するか | false |
| rotate | r | 回転角度（度数） | 0 |
| flipx | fx | X軸で反転するか | false |
| flipy | fy | Y軸で反転するか | false |
| flipz | fz | Z軸で反転するか | false |
| pasteoptions | po | 貼り付けオプション | |

## 使用例

```yaml
  Skills:
  - fawepaste{schematic=mybuilding;ignoreair=true} @targetlocation ~onInteract
```

## エイリアス
- [x] pasteschematic
- [x] wepaste
