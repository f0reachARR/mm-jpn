# Gamemode

**タイプ**: 🟦 エンティティ (Entity)

## 説明

プレイヤーのゲームモードをチェックします。

> *Matches the target player's gamemode*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `mode` | m | The gamemode to match | SURVIVAL |

## 使用例

```yaml
ExampleSkill:
  Conditions:
  - gamemode{m=ADVENTURE} true
```

## エイリアス

- `gm`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/Gamemode)を基に日本語訳されています。
