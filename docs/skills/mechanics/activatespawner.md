# ActivateSpawner（スポナー起動）

## 説明

ターゲット位置にあるMythicMobsの[スポナー](Spawners)を起動し、モブをスポーンさせます。スポナーに設定された条件やオプションは上書きされません。

> `useTimer` を `false` に設定したスポナーと組み合わせて使用するのが最適です。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| spawners | spawner, s | 起動するスポナーの名前。グループ指定やワイルドカードも使用可能 | NONE |

## 使用例

"BossAdd" という名前のスポナーを起動する例:
```yaml
    Skills:
    - activatespawner{spawner=BossAdd}
```

"Castle" グループに属するすべてのスポナーを起動する例:
```yaml
    Skills:
    - activatespawner{spawner=g:Castle}
```

"DungeonBoss1Spawner" で始まるすべてのスポナーを起動する例（例: DungeonBoss1Spawner1、DungeonBoss1Spawner2 など）:
```yaml
    Skills:
    - activatespawner{spawner=DungeonBoss1Spawner*}
```

## エイリアス
- [x] as
