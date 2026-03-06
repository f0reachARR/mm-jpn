# よくある質問 (FAQ)

MythicMobs に関するよくある質問と回答をまとめています。

---

## インストール・設定関連

### Q: MythicMobs はどこでダウンロードできますか？

**A:** [SpigotMC のリソースページ](https://www.spigotmc.org/resources/mythicmobs.5702/)からダウンロードできます。無料版と有料版（MythicMobs Premium）があります。

---

### Q: 設定を変更した後、再起動しないといけませんか？

**A:** 多くの設定は `/mm reload` コマンドでリロードできます。ただし、一部の設定（`config.yml` の基本設定など）はサーバーの再起動が必要な場合があります。

---

### Q: YAML のインデント（字下げ）が正しいか確認するには？

**A:** [YAML Lint](http://www.yamllint.com/) などのオンラインバリデーターを使用してください。MythicMobs の設定は YAML 形式なので、インデントのエラーがあるとファイルが読み込まれません。スペースを使い（タブは不可）、一般的に2スペースのインデントを推奨します。

---

### Q: ログにエラーが出ています。どう対処すればよいですか？

**A:** サーバーの `logs/latest.log` を確認し、`MythicMobs` に関連するエラーメッセージを探してください。よくあるエラーの原因：
- YAML 構文エラー（インデントミス、特殊文字のエスケープ漏れ）
- 存在しないモブ名やアイテム名の参照
- 設定値の型ミス（数値が必要な箇所に文字列を記入など）

---

## モブ関連

### Q: カスタムモブをスポーンするには？

**A:** コマンドを使います：
```
/mm mobs spawn <モブ名>
```

---

### Q: モブが自然デスポーンしないようにするには？

**A:** モブの Options セクションで設定します：
```yaml
Options:
  NaturallyDespawn: false
  Despawn: false
```

---

### Q: モブのレベルをランダムにするには？

**A:** スポーナーやコマンドでレベル範囲を指定できます：
```yaml
# スポーナーで
Level: 1-10

# コマンドで
/mm mobs spawn MyMob{level=<数>}
```

---

### Q: モブが特定のバイオームにのみ出現するようにするには？

**A:** ランダムスポーンの `Biomes` 設定を使います：
```yaml
MySpawn:
  MobName: DesertCreature
  Biomes:
  - DESERT
  - BADLANDS
```

---

## スキル関連

### Q: スキルのクールダウンを設定するには？

**A:** 外部スキルファイルで `Cooldown` フィールドを使います：
```yaml
MySkill:
  Cooldown: 10    # 10秒のクールダウン
  Skills:
  - ...
```

---

### Q: 複数のスキルを順番に実行するには？

**A:** スキル内で `delay` メカニクスを使います：
```yaml
ComboSkill:
  Skills:
  - skill{s=FirstSkill} @self
  - delay{d=20}              # 1秒待機
  - skill{s=SecondSkill} @self
  - delay{d=40}              # 2秒待機
  - skill{s=ThirdSkill} @self
```

---

### Q: スキルが特定の確率で発動するようにするには？

**A:** スキルの末尾に確率（0.0〜1.0）を追加します：
```yaml
Skills:
- damage{a=10} @target ~onTimer:100 0.5    # 50%の確率で発動
```

または `chance` 条件を使います：
```yaml
Skills:
- damage{a=10} @target ~onTimer:100 ?chance{c=0.5}
```

---

## アイテム関連

### Q: カスタムアイテムをモブのドロップにするには？

**A:** モブの `Drops` セクションにカスタムアイテム名を指定します：
```yaml
MyMob:
  Drops:
  - MyCustomSword 1 0.05    # 5%の確率でドロップ
```

---

### Q: カスタムアイテムを入手するコマンドは？

**A:**
```
/mm items get <アイテム名>
/mm items get <アイテム名> <数量>
```

---

## 互換性関連

### Q: どのプラグインと互換性がありますか？

**A:** MythicMobs は多くのプラグインと互換性があります：
- **PlaceholderAPI** - プレースホルダーの使用
- **WorldGuard** - スポーンの領域制限
- **Citizens** - NPCとの連携
- **Vault** - 通貨システムとの連携
- **MythicCrucible** - MythicMobs の拡張アイテムプラグイン

---

### Q: 古いバージョンの Minecraft でも動作しますか？

**A:** MythicMobs は Minecraft 1.12 以降をサポートしていますが、最新バージョンを推奨します。古いバージョンでは一部機能が使えない場合があります。

---

## パフォーマンス関連

### Q: MythicMobs がサーバーを重くしています。改善方法は？

**A:** 以下を試してください：
1. スポーナーの `MaxMobs` を下げる
2. ランダムスポーンの `Chance` を下げる
3. スキルの `~onTimer` の頻度を下げる
4. `config.yml` の `MaxMobsPerChunk` を設定する
5. 不要なモブを `/mm mobs kill all` で削除する

---

## デバッグ関連

### Q: スキルが動作しているか確認するには？

**A:** デバッグモードを使います：
```
/mm debug 5    # デバッグレベル5（詳細）
/mm debug 0    # デバッグモード無効
```

---

[← ホームに戻る](Home.md)
