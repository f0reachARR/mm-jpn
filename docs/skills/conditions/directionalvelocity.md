# directionalvelocity

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティの方向速度をチェックします。

> *A condition that checks checks if the target has a velocity matching the given parameters.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `x` | s, side | The X velocity. Can be a range. Isn't checked by the condition if not set |  |
| `absx` | ax, abss, as | Whether to use only the absolute values for the X velocity | `relative`'s value |
| `y` | up, down, vertical, v | The Y velocity. Can be a range. Isn't checked by the condition if not set |  |
| `absy` | ay | Whether to use only the absolute values for the Y velocity | false |
| `z` | f, forward | The Z velocity. Can be a range. Isn't checked by the condition if not set |  |
| `absz` | az, absf, af | Whether to use only the absolute values for the Z velocity | false |
| `relative` | rel | Whether the check should be relative to the entity's orientation and not to the world axis. If true, X is forward/backward and Z is side-to-side | false |

## 使用例

```yaml
  Conditions:
  - directionalVelocity{y=<0;absx=true} true
```

## エイリアス

- `dvelocity`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/directionalvelocity)を基に日本語訳されています。
