# TagRemove（スコアボードタグ削除）

## 説明

ターゲットからスコアボードタグを削除します。

**hastag条件**（[条件](/conditions/start)を参照）と組み合わせて使用します。バニラコマンド `/scoreboard players tag <player name> remove [Tag Name]` でも同様の操作が可能です。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| tag | t | タグの名前（文字列） | default |

## 使用例

```yaml
# このスキルはキャストするモブから "Test" タグを削除します。
UntagSkill:
  Skills:
  - removetag{t=Test} @self
```

## エイリアス
- [x] removetag
- [x] removescoreboardtag
