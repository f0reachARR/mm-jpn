# AddTrade（取引追加）

## 説明

村人の取引を変更します。  
このメカニックを使用したときに職業が割り当てられていない場合、村人はニットウィットになります。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| action | mode, m | 実行するアクション。`ADD`（追加）、`REMOVE`（削除）、`REPLACE`（置換）のいずれか | ADD |
| slot | s, index | アクションを適用するスロット番号（0始まり。3つの取引がある場合、中央は slot=1） | 0 |
| ingredient | item, ingredient1, item1, i, i1 | 1つ目の素材 | STONE |
| ingredient2 | item2, i2 | 2つ目の素材 | |
| result | r | 取引の結果アイテム | STONE |
| maxUses | uses, u | 取引の最大使用回数 | 最大整数値 |
| experienceReward | expReward, exp, dropExp | 取引時に経験値をドロップするか | false |
| villagerExp | villExp, vexp | 取引成功時に村人に付与する経験値量 | 0 |
| priceMultiplier | multiplier | プレイヤーが村人を怒らせた場合の価格乗数 | 0 |
| demand | d | 取引の需要 | 1 |
| specialPrice | special | プレイヤーが村人に好意的な場合（評判またはヒーローオブザビレッジ効果）の特別価格 | 1 |
| ignoreDiscounts | discounts | 割引を無視するかどうか | false |

## 使用例

```yaml
TestVillager:
  Type: Villager
  Display: 'OwO'
  Skills:
  - addTrade{item=DIAMOND 1;item2=EMERALD 2;result=IRON_INGOT 3;expReward=True;villExp=999;multiplier=0} @self ~onDamaged
  - addTrade{action=REPLACE;slot=1;item=DIRT 1;item2=COAL 2;result=DIAMOND_BLOCK 3;expReward=True;villExp=999;multiplier=0} @self ~onSignal:rev
```

## エイリアス
- [x] setTrade
- [x] removeTrade
- [x] replaceTrade
