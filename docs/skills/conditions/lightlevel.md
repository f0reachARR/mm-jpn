# lightlevel

**タイプ**: 🟩 ロケーション (Location)

## 説明

ターゲットの位置の光レベルをテストします。

> *Tests the light level at the target location*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `level` | l | The level range to match | 0 |

## 使用例

**例 1:**

```yaml
  Conditions:
  - lightlevel{l=10} true
```

**例 2:**

```yaml
  Conditions:
  - lightlevel{l=>10} true
```

**例 3:**

```yaml
  Conditions:
  - lightlevel{l=1to10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/lightlevel)を基に日本語訳されています。
