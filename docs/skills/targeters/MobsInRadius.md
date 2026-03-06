# @MobsInRadius (半径内モブターゲッター)

## 概要
キャスターを中心とした指定半径内のMythicMobsまたはバニラオーバーライドのモブをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@MIR`, `@mobs`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | ターゲッターの半径（ブロック数） | 5 |
| types | type, t | ターゲットとするMythicMobのタイプ（複数指定可） | （すべて） |
| checkiftemplate | cit | モブの内部名ではなくテンプレートに対してチェックするか | false |

## 使用例
```yaml
ExampleSkill:
  Skills:
  # 半径10ブロック内の特定タイプのモブに火をつける
  - ignite @MobsInRadius{r=10;types=IncredibleZombie,SpookyScarySkeleton}
```

## 備考
- `types` 属性でカンマ区切りで複数のモブタイプを指定できます
- MythicMobsとして定義されたモブのみを対象とします
