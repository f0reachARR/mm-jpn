# ステップ5: 追加のメモ

## YAMLのヒント

### インデント

YAMLファイルでは、インデントに**スペース**を使用する必要があります。**タブは使用しないでください**。

正しい例（スペース2つのインデント）：

```yaml
MyMob:
  Type: ZOMBIE
  Health: 100
  Skills:
  - ignite @target ~onAttack
```

### 引用符

値にコロン（:）、ハッシュ（#）、またはYAMLの特殊文字が含まれる場合は引用符を使用します：

```yaml
Display: 'ゾンビ：最強の敵'
```

### コメント

`#`を使ってコメントを追加できます：

```yaml
# これはコメントです
MyMob:
  Type: ZOMBIE  # このモブはゾンビです
  Health: 100
```

## よくある間違い

### スペースのある内部名

内部名にはスペースを使用できません！

❌ 間違い:
```yaml
My Mob:
  Type: ZOMBIE
```

✅ 正しい:
```yaml
MyMob:
  Type: ZOMBIE
```

### タブのインデント

タブインデントはYAMLエラーを引き起こします。常にスペースを使用してください。

### メタスキルでのトリガー

トリガーはモブのスキルセクションでのみ使用できます。メタスキルファイルにはトリガーを含めないでください。

❌ 間違い（スキルファイル内）:
```yaml
ExampleSkill:
  Skills:
  - ignite @target ~onAttack  # メタスキル内でのトリガーは無効
```

✅ 正しい（モブファイル内）:
```yaml
MyMob:
  Type: ZOMBIE
  Skills:
  - skill{s=ExampleSkill} @self ~onAttack  # モブファイル内のトリガー
```

## デバッグのヒント

1. `/mm reload`後にコンソールでエラーを確認する
2. `/mm debug 1`でデバッグモードを有効にする
3. モブがスポーンしない場合は`/mm mobs list`でモブが正しくロードされているか確認
4. スキルが機能しない場合は`/mm test cast [skillname]`でテスト

## テキストエディタ

YAMLを編集するには、YAML対応のテキストエディタを使用することをお勧めします：

- [Visual Studio Code](https://code.visualstudio.com/) - 無料、YAML拡張機能あり
- [Notepad++](https://notepad-plus-plus.org/) - 軽量、シンタックスハイライト
- [IntelliJ IDEA](https://www.jetbrains.com/idea/) - 高機能IDE

---

**[<< ステップ4: 基本的なコマンド](step4-commands.md)**
