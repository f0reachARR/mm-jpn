# BreakBlock（ブロック破壊）

## 説明

ターゲット位置のブロックを破壊します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| material | m, mat | このマテリアルのブロックのみ破壊する（設定しない場合はすべて破壊） | |
| dodrops | drops, d | ブロックのドロップを生成するか | false |
| explosionforce | force, ef | 爆発力でブロックを破壊するか | false |
| radius | r | 破壊する範囲（1以上で周囲のブロックも含む） | 0 |
| saferadius | sr | 安全に保つ範囲（この範囲内のブロックは破壊しない） | 0 |
| angle | a | 採掘角度 | 90 |
| offset | off | ブロック選択のオフセット | 0 |
| toggle | t | ブロックをトグル（破壊と配置を切り替える）するか | false |

## 使用例

```yaml
  Skills:
  - breakblock{d=true} @targetblock ~onInteract
```

```yaml
  Skills:
  - breakblock{m=STONE;r=3;dodrops=true} @targetblock ~onTimer:20
```

## エイリアス
- [x] bb
