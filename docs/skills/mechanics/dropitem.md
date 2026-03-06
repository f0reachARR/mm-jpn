# DropItem（アイテムドロップ）

## 説明

ターゲット位置にアイテムまたはドロップテーブルをドロップします。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| item | i | ドロップするアイテムまたはドロップテーブルの名前 | |
| amount | a | ドロップするアイテムの数量 | 1 |
| velocity | v | ドロップしたアイテムの速度 | 0 |
| usedroptable | udt | ドロップテーブルを使用するか | false |
| droptable | dt | 使用するドロップテーブル名 | |
| coloredname | cn | アイテム名に色を適用するか | false |

## 使用例

```yaml
  Skills:
  - dropitem{item=DIAMOND;amount=3} @targetlocation ~onDeath
```

```yaml
  Skills:
  - dropitem{droptable=MyDropTable;usedroptable=true} @targetlocation ~onDeath
```

## エイリアス
- [x] drop
- [x] di
