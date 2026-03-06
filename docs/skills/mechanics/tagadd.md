# TagAdd（スコアボードタグ追加）

## 説明

ターゲットにスコアボードタグを追加します。

**hastag条件**（[条件](/skills/conditions/hastag)を参照）と組み合わせて使用します。バニラコマンド `/tag <targets> add <name>` でも同様の操作が可能です。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| tag | t | タグの名前（文字列） | default |

## 使用例

```yaml
# このスキルはキャストするモブに "Test" タグを付与します。
TagSkill:
  Skills:
  - addtag{t=Test} @self
```

```yaml
# このスキルはモブが "Test" タグを持っている場合のみ実行されます。
TagTest:
  Conditions:
  - hastag{t=Test}
  Skills:
  - suicide @self
```

## エイリアス
- [x] addtag
- [x] addscoreboardtag
