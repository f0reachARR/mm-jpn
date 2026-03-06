# Equip（装備）

## 説明

キャストしているモブにアイテムを装備させます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| mainhand | mh, hand, m | メインハンドに装備するアイテム | |
| offhand | oh | オフハンドに装備するアイテム | |
| helmet | head, h | ヘルメットスロットに装備するアイテム | |
| chestplate | chest, c | チェストプレートスロットに装備するアイテム | |
| leggings | legs, l | レギンススロットに装備するアイテム | |
| boots | feet, f | ブーツスロットに装備するアイテム | |
| dropchance | dc | 装備のドロップ率（0〜1） | 0 |

## 使用例

```yaml
  Skills:
  - equip{mh=DIAMOND_SWORD;helmet=DIAMOND_HELMET} @self ~onSpawn
```

## エイリアス
- [x] e
