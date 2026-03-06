# @TargetBlock (ターゲットブロックターゲッター)

## 概要
プレイヤーキャスターが見ているブロックをターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| maxdistance | max, distance, d | プレイヤーキャスターの場合の最大距離 | 64 |
| ignoreTransparent | it | 透明なブロックを無視するか | true |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - effect:particles{hs=1;vs=1} @TargetBlock{ignoreTransparent=false}  # 見ているブロックにパーティクル
```

## 備考
- キャスターがプレイヤー: 視線の先のブロック
- キャスターがMythicMobsで脅威テーブルあり: 最高脅威エンティティの位置
- キャスターが戦闘中: ターゲットの位置
- 上記いずれでもない場合: 最後に攻撃したエンティティの位置
