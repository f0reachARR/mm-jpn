# @ProjectileForward (プロジェクタイル前方ターゲッター)

## 概要
発射中のプロジェクタイルの進行方向に対して前方の位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| forward | f, amount, a | ターゲット地点までの距離（ブロック数） | 1 |
| rotate | rot | プロジェクタイルを中心としたターゲット位置の回転 | 0 |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - projectile{...;
    onTick=[
      - effect:particles{p=flame} @ProjectileForward{f=2}  # プロジェクタイル前方2ブロックにフレームパーティクル
      - effect:particles @Origin
    ]}
```

## 備考
- プロジェクタイルスキルの `onTick` 内で使用します
- プロジェクタイルの現在位置ではなく、その進行方向前方の位置をターゲットにします
