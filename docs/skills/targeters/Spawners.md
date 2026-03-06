# @Spawners (スポナー位置ターゲッター)

## 概要
指定したモブスポナーの位置をターゲットにします。

- **タイプ**: 複数場所ターゲッター

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| spawners | spawner, s | スポナーの名前（グループ名 `g:グループ名` やワイルドカード `Spawner*` も使用可） | |

## 使用例
```yaml
ExampleSkill_SingleSpawner:
  Skills:
  - effect:particles @Spawner{s=TestSpawner}  # 単一スポナーの位置にパーティクル

ExampleSkill_Group:
  Skills:
  - effect:particles @Spawner{s=g:ExampleSpawnerGroup}  # スポナーグループにパーティクル

ExampleSkill_WildCard:
  Skills:
  - effect:particles @Spawner{s=ForestSpawner_*}  # ワイルドカードで複数スポナーにパーティクル
```

## 備考
- スポナー名はMythicMobsのスポナー設定で定義されたものを使用します
- ワイルドカード（`*`）で複数のスポナーをまとめてターゲットにできます
- グループ指定（`g:グループ名`）でスポナーグループをターゲットにできます
