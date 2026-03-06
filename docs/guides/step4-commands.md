# ステップ4: 基本的なコマンド

モブを設定したら、いくつかの重要なコマンドを知っておく必要があります。

## 必須コマンド

### リロード

設定ファイルを変更した後は、プラグインをリロードして変更を反映させる必要があります：

```
/mm reload
または
/mm r
```

### モブのスポーン

特定のMythicMobをスポーンさせます：

```
/mm mobs spawn [mob_name]
または
/mm m s [mob_name]
```

例：
```
/mm m s SkeletonKing
/mm m s SkeletonKing:5    # レベル5でスポーン
/mm m s SkeletonKing 3    # 3体スポーン
```

### モブの削除

すべてのアクティブなMythicMobを削除します：

```
/mm mobs killall
または
/mm m killall
```

特定の名前のモブを削除します：

```
/mm mobs kill [mob_name]
```

### アイテムの取得

MythicMobsで作成したアイテムを取得します：

```
/mm items get [item_name]
または
/mm i get [item_name]
```

### スキルのテスト

スキルをテストします：

```
/mm test cast [skillname]
```

### デバッグモード

問題が発生した場合はデバッグモードを有効にします：

```
/mm debug 1   # デバッグレベル1（情報）
/mm debug 2   # デバッグレベル2（詳細）
/mm debug 0   # デバッグOFF
```

## ヒントとコツ

- 設定を変更するたびに`/mm reload`を実行することを忘れないでください
- スポーンしたモブを確認するには`/mm mobs listactive`を使用します
- モブに問題がある場合は`/mm mobs info [mob_name]`でモブの情報を確認します

---

**[<< ステップ3: 最初のモブの作成](step3-first-mob.md)** | **[>> ステップ5: 追加のメモ](step5-notes.md)**
