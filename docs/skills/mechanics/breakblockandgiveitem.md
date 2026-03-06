# BreakBlockAndGiveItem（ブロック破壊＆アイテム付与）

## 説明

ターゲット位置のブロックを破壊し、アイテムまたはドロップテーブルを付与します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| material | m, mat | このマテリアルのブロックのみ破壊する | |
| item | i | 付与するアイテムまたはドロップテーブル | |
| dodrops | drops, d | ブロックのドロップを生成するか | false |
| radius | r | 破壊する範囲 | 0 |

## 使用例

```yaml
  Skills:
  - breakblockandgiveitem{m=STONE;item=MyStoneDrop} @targetblock ~onTimer:20
```

## エイリアス
- [x] bbgi
- [x] breakandgive
