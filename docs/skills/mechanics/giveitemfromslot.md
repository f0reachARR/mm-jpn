# GiveItemFromSlot（スロットからアイテム付与）

## 説明

キャスターの指定スロットのアイテムをターゲットに付与します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| slot | s | アイテムを取得するスロット番号 | 0 |
| amount | a | 付与するアイテムの数量 | 1 |
| dropifInventoryFull | drop, dif | インベントリが満杯の場合にドロップするか | false |

## 使用例

```yaml
  Skills:
  - giveitemfromslot{slot=0;amount=1} @trigger ~onInteract
```

## エイリアス
- [x] gifs
- [x] giveitemslot
