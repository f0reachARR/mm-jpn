# ステップ2: ファイルとディレクトリ

各要素が何であるかを理解したら、それをどこに置くかを知る必要があります！

MythicMobsフォルダにはモブ、アイテム、スポーンを含む複数のサブフォルダが含まれています。また、[パック](../packs.md)を使用して物事を独自のミニディレクトリに整理することもできます。

MythicMobsフォルダ内には、Mythicの各コンポーネントのサブフォルダがあります。これらのフォルダには好きなだけサブフォルダと`.yml`ファイルを含めることができ、各ファイルには好きなだけモブ、アイテム、ランダムスポーンなどを含めることができます。

## フォルダ構造

```
/plugins/MythicMobs/
├── Mobs/           # モブファイル
│   └── 例: SkeletonKing.yml
├── Skills/         # スキル（メタスキル）ファイル
├── Items/          # アイテムファイル
├── DropTables/     # ドロップテーブルファイル
├── RandomSpawns/   # ランダムスポーンファイル
├── Spawners/       # スポナーファイル（ゲーム内で管理）
├── Packs/          # パックフォルダ
│   └── 例: Skeletons/
│       └── Mobs/
│           └── King.yml
└── config/         # 設定ファイル
    ├── config.yml
    ├── config-mobs.yml
    └── config-spawning.yml
```

## 有効なファイルパスの例

- `/plugins/MythicMobs/Mobs/SkeletonKing.yml`
- `/plugins/MythicMobs/Mobs/Skeletons/King.yml`
- `/plugins/MythicMobs/Packs/Skeletons/Mobs/King.yml`

## YAMLファイルの基本

各`.yml`ファイルには複数のモブ、アイテム、スキルなどを定義できます。YAMLのインデントは非常に重要で、スペースを使用する必要があります（タブは使用しないでください）。

```yaml
# これはモブファイル（例: Mobs/MyMobs.yml）の例です

Zombie1:
  Type: ZOMBIE
  Health: 100
  Display: '普通のゾンビ'

Zombie2:
  Type: ZOMBIE
  Health: 200
  Display: '強いゾンビ'
  Damage: 15
```

---

**[<< ステップ1: 用語の理解](step1-terms.md)** | **[>> ステップ3: 最初のモブの作成](step3-first-mob.md)**
