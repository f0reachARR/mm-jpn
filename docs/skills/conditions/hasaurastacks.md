# hasaurastacks

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットエンティティのオーラスタック数をチェックします。

> *Tests if the target has the given range of stacks from an aura*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `aura` | auraname, b, buff, buffname, debuff, debuffname, n, name | The name of the aura to check for | stacks |

## 使用例

```yaml
  Conditions:
  - hasaurastacks{n=firedebuff;s=>3} true
```

## エイリアス

- `hasbuffstacks`
- `hasdebuffstacks`
- `aurastacks`
- `buffstacks`
- `debuffstacks`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/hasaurastacks)を基に日本語訳されています。
