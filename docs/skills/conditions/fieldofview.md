# fieldofview

**タイプ**: 🟧 比較 (Compare)

## 説明

ターゲットがキャスターの視野内にいるかどうかをチェックします。

> *Tests if the target is within the given angle from where the caster is looking.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `angle` | a | The angle of the FOV to check in | 90 |
| `rotation` | r | Rotates the FOV to check in | 0 |

## 使用例

**例 1:**

```yaml
  TargetConditions:
  - fieldofview{angle=90} false
```

**例 2:**

```yaml
  TargetConditions:
  - fieldofview{angle=90} true
```

## エイリアス

- `infieldofview`
- `fov`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/fieldofview)を基に日本語訳されています。
