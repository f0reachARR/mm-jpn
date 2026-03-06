# altitude

**タイプ**: 🟦🟩 エンティティ/ロケーション

## 説明

ターゲットエンティティが地面からどれだけ高い位置にいるかをテストします。

> *This condition tests how far above the ground the target entity is.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `height` | altitude, a, h | チェックする高さの範囲 |  |
| `maxHeight` | mH | このコンディションがチェックできる最大高さを制限する | 30 |

## 使用例

```yaml
Conditions:
- altitude{h=3-5} true
```

## エイリアス

- `heightfromsurface`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/altitude)を基に日本語訳されています。
