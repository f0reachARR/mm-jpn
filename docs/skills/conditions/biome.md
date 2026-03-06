# biome

**タイプ**: 🟩 ロケーション (Location)

## 説明

ターゲットが指定されたバイオームのリスト内にいるかどうかをテストします。

> *This condition tests if the target is within the given list of biomes.  
If no namespace is provided, it will default to `minecraft:`*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `biome` | b | チェックするバイオームのリスト | minecraft:plains |
| `exact` | e | バイオームを完全一致でチェックするかどうか | true |

## 使用例

**例 1:**

```yaml
Conditions:
- biome{b=minecraft:plains,river} true
```

**例 2:**

```yaml
Conditions:
- biome{b=far_end:void,far_end:warped_marsh} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/biome)を基に日本語訳されています。
