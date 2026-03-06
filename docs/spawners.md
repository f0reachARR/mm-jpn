# スポナー (Spawners)

> **警告**: スポナーの設定ファイルが実行中のサーバーにロードされると、ゲーム内コマンドでのみ編集できます。テキストエディタでロード済みのスポナー設定ファイルを編集したい場合は、ファイルを編集する前にサーバーを停止する必要があります。

スポナーを使用すると、カスタムモブがスポーンするワールド内の特定のポイントを定義できます。条件、組み込みタイマー、クールダウン、ウォームアップなど、さまざまな便利なオプションと一緒に使用できます。

スポナーは[コマンド](../commands-and-permissions.md)を使ってゲーム内で直接作成するか、*/MythicMobs/Spawners*フォルダに設定ファイルを作成することで作成できます。

## スポナーの利点

- 自然なモブスポーンが有効になっている必要がありません。
- 各モブスポーンの場所と方法を正確に指定できるため、スポーン実装をより細かく制御できます。
- タイマー、リーシュなどの機能をサポートしています。
- 小さなアリーナやダンジョンの人口を増やすのに最適です。

## スポナーの欠点

- セットアップが時間のかかる作業になる可能性があります（特に大規模な実装の場合）。
- 正しく計画されていないと管理が非常に難しくなります。
- モブを適切に設定する必要があります。

## 設定例

```yaml
SpawnerName:
  MobName: mobTypeName 
  World: worldname
  SpawnerGroup: GroupName
  X: 0 
  Y: 0 
  Z: 0 
  Radius: 0 
  RadiusY: 0 
  UseTimer: true  
  MaxMobs: 1
  MobLevel: 1
  MobsPerSpawn: 1
  Cooldown: 0
  WarmUp: 0
  CheckForPlayers: true
  ActivationRange: 40
  LeashRange: 32
  HealOnLeash: false
  ResetThreatOnLeash: false
  ShowFlames: false
  Conditions: []
```

## オプション

| オプション | 説明 | デフォルト |
|---------|------|---------|
| MobName/MobType | スポナーがスポーンするモブタイプ | N/A |
| World | スポナーが配置されているワールド | 作成ワールド |
| SpawnerGroup | スポナーのグループ名 | N/A |
| X/Y/Z | スポナーの座標 | 作成場所 |
| Radius | モブがスポーンできるスポナー周辺の半径 | 0 |
| RadiusY | モブがスポーンできる垂直半径 | 0 |
| UseTimer | スポナーがタイマーで起動するかどうか | true |
| MaxMobs | このスポナーからスポーンして存在できる最大モブ数 | 1 |
| MobLevel | スポナーからスポーンするモブのレベル | 1 |
| MobsPerSpawn | スポナーが1回でスポーンするモブの数 | 1 |
| Cooldown | モブがスポーンした後、次のモブがスポーンするまでの待機時間（秒） | 0 |
| WarmUp | スポナーが起動してからクールダウンを開始するまでの時間（秒） | 0 |
| CheckForPlayers | スポナーが「アクティブ化」するためにプレイヤーが近くにいる必要があるかどうか | true |
| ActivationRange | スポナーがアクティブ化するためのプレイヤーの範囲 | 40 |
| LeashRange | モブがスポーン場所から移動できる最大距離 | -1（なし） |
| HealOnLeash | モブがスポナーにリーシュバックするときに全快するかどうか | false |
| ResetThreatOnLeash | モブがスポナーにテレポートするときに脅威テーブルをリセットするかどうか | false |
| ShowFlames | スポナー周辺に炎を表示するかどうか | false |
| Conditions | スポナーがアクティブ化するための条件 | なし |

## タイミングの注意

スポーンのタイミング: `ウォームアップ → モブスポーン → クールダウン → モブスポーン...`

## ゲーム内コマンドでの作成

```
/mm spawners create [spawner_name] [mob_name]
または
/mm s create [spawner_name] [mob_name]
```

詳細なスポナーコマンドは[コマンドとパーミッション](../commands-and-permissions.md)を参照してください。
