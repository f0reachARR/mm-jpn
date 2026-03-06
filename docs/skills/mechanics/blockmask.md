# BlockMask（ブロックマスク）

## 説明

指定したターゲットの周囲にブロックのマスクを作成します。このエフェクトで作成・変更されたブロックは、指定した時間が経過すると元の状態に戻ります。`blockunmask` エフェクトを使用することで早期にリセットすることも可能です。

blockmask エフェクトは実際にはワールドのブロックを一切変更しないため、環境を破壊することはありません。このエフェクトによる変更は純粋に視覚的なものであり、実際のブロックは変更されず、常に元の状態に戻ります。

`material` 属性には [Bukkit マテリアル名](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) を使用します。  
ゲーム内で `/itemdb` コマンドを使用してブロックのマテリアル名を確認できます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| material | mat, m, block, b | blockmask に使用する[ブロックの種類](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) | GRAVEL |
| radius | r | blockmask エフェクトの範囲 | 0 |
| radiusy | ry | 範囲のY方向の成分 | radius の値 |
| noise | n | エフェクトのランダム性 | 0 |
| duration | d | エフェクトの継続時間（tick単位） | 0 |
| shape | s | エフェクトの形状（`Sphere` / `Cube`） | SPHERE |
| noair | na | 空気ブロックのみマスクしない | true |
| onlyair | oa | 空気ブロックのみマスクする | false |
| audience | | エフェクトの[対象者] | nearby |
| occ | o, oc | onlyair 使用時、透明ブロックも対象にするか | true |

### duration 属性
1秒は20tickです。0に設定すると無限の継続時間になります。

### shape 属性
`Sphere`（球体）と `Cube`（立方体）のみ使用可能です。

## 使用例

キャスターの周囲にネザーラックの環境を作成する例（duration=0 で手動のブロック更新かログインし直すまで維持）:
```yaml
- effect:blockmask{m=netherrack;r=5} @self ~onTimer:1200
```

半径50ブロック以内のすべてのプレイヤーの足元に氷を生成し、常に滑りやすい状態にする例:
```yaml
- effect:blockmask{m=ice;r=2;d=20} @PIR{r=50} ~onTimer:5
```

空気ブロック（および透明ブロック）を氷に置き換える例:
```yaml
- effect:blockmask{m=ice;r=2;d=20;onlyair=true} @origin ~onTimer:5
- effect:blockmask{m=ice;r=2;d=20;onlyair=true;occ=false} @origin ~onTimer:5
```

blockmask エフェクトを強制的に元に戻す例（blockunmask）:
```yaml
- effect:blockunmask{r=30}
```

## エイリアス
- [x] effect:blockMask
- [x] e:blockMask
