# GiveItem（アイテム付与）

## 説明

アイテムをターゲットに付与します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| item | i | 付与するアイテムの名前（MythicMobs アイテムまたはバニラマテリアル） | |
| amount | a | アイテムの数量 | 1 |
| dropifInventoryFull | drop, dif | インベントリが満杯の場合にドロップするか | false |

## 使用例

```yaml
  Skills:
  - giveitem{item=DIAMOND;amount=5} @trigger ~onInteract
```

```yaml
  Skills:
  - giveitem{item=MyCustomSword;amount=1;drop=true} @trigger ~onDeath
```

## エイリアス
- [x] give
- [x] gi
