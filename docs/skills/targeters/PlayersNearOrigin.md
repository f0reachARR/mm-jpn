# @PlayersNearOrigin (原点付近プレイヤーターゲッター)

## 概要
メタスキルの原点付近にいるすべてのプレイヤーをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@playersnearsource`, `@PNO`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | ターゲッターの半径（ブロック数） | 5 |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - projectile{...;
    onEnd=[
      - damage{a=10} @PlayersNearOrigin{r=2}
      # プロジェクタイルが終了した時、原点から2ブロック以内のプレイヤーにダメージ
    ]} @target
```

## 備考
- プロジェクタイルの `onEnd` や `onTick` と組み合わせると強力です
- `@PlayersInRadius` はキャスター基準、こちらはスキルの原点（プロジェクタイルなど）基準です
