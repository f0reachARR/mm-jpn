# @MobsNearOrigin (原点付近モブターゲッター)

## 概要
メタスキルの原点付近にいる指定タイプのMythicMobsまたはバニラオーバーライドのモブをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@mobssnearsource`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | ターゲッターの半径（ブロック数） | 5 |
| types | type, t | ターゲットとするMythicMobのタイプ（複数指定可） | （すべて） |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - projectile{...;
    onEnd=[
      - ignite @MobsNearOrigin{r=10;types=IncredibleZombie,SpookyScarySkeleton}
      # 終了時、原点付近の特定タイプのモブに火をつける
    ]}
```

## 備考
- `@MobsInRadius` はキャスター基準、こちらはスキルの原点基準です
