# コマンドとパーミッション (Commands and Permissions)

## コマンド

MythicMobsは **/mythicmobs** と入力することでアクセスできるシンプルなコマンド構造を持っています。**[]** で囲まれたコマンドパラメータは必須で、**<>** はオプションです。

> [メタスキル](skills/meta-skills.md)を使って[カスタムコマンド](skills/skill-commands.md)を作成することが可能です。

## フラグ

一部のコマンドには、最初の引数の前にフラグを設定することができ、コマンドの動作を変更します。

| フラグ | 説明 | 影響するコマンド | 例 |
|------|------|--------------|-----|
| -s | サイレントコマンドはチャットフィードバックを表示しません | `mm mobs spawn`, `mm item give`, `mm test cast`, `mm test mechanic` | `/mm test cast -s [metaskill]` |
| -p <プレイヤー名> | 指定されたプレイヤーでコマンドを実行します | `mm mobs spawn`, `mm spawners create`, `mm spawners move` | `/mm m s -p <player> [mobname]` |
| -t | ターゲット位置でコマンドを実行します | `mm mobs spawn` | `/mm m s -t [mobname]` |
| -n | モブが自然にスポーンしたかのようにシミュレートします | `mm mobs spawn` | `/mm m s -n [mobname]` |
| -p | 永続モブも削除するかどうか | `mm mobs killall` | `/mm m killall -p` |
| -f | 指定されたファクションのすべてのモブを削除します | `mm mobs kill` | `/mm m kill -f [factionname]` |
| -d | インベントリが満杯の場合、アイテムを地面にドロップします | `mm item give` | `/mm i give -d [itemname]` |

## 一般コマンド

- **/mm**（エイリアス: **/mythicmobs**）- プラグインのベースコマンド。他のすべてのコマンドを表示します。
- **/mm debug [level]**（エイリアス: **/mm d [level]**）- プラグインのデバッグレベルを設定します。0 = OFF。
- **/mm debugmode [true/false]** - デバッグモードを有効にします。ランダムスポナー、モブスポナー、デバッグを困難にする他のランダムな機能を無効にします。
- **/mm reload**（エイリアス: **/mm r**）- プラグインをリロードします。
- **/mm save** - アクティブなすべてのモブとスポナーを強制的に保存します。
- **/mm version** - MythicMobsのバージョンを表示します。

## アイテムコマンド

- **/mm items**（エイリアス: **/mm i**）- アイテム関連コマンドのベース。
- **/mm items get [item_name] <amount>** - 設定されたモブ装備からアイテムを取得します。
- **/mm items give [player] [item_name] <amount>** - プレイヤーにアイテムを与えます。
- **/mm items give -s [player] [item_name] <amount>** - プレイヤーにサイレントでアイテムを与えます。
- **/mm items give -d [player] [item_name] <amount>** - プレイヤーにアイテムを与え、余分なアイテムを地面にドロップします。
- **/mm items list** - 設定されたすべてのモブ装備をリスト表示します。
- **/mm item import <itemName> [fileName]** - 持っているアイテムをItemsフォルダにインポートします。
- **/mm items browse** - ロードされたすべてのMythicアイテムを表示するGUIを開きます。（プレミアムのみ）

## モブコマンド

- **/mm mobs**（エイリアス: **/mm m**）- モブ関連コマンドのベース。
- **/mm mobs info [mob_name]** - MythicMobに関する多くの情報を表示します。
- **/mm mobs list** - サーバーにロードされたモブのリストを表示します。
- **/mm mobs listactive** - 現在スポーンしているモブとその数のリストを表示します。
- **/mm mobs kill [mob_name]** - 指定した名前のすべてのMythicMobを削除します。
- **/mm mobs kill -f [faction]** - 指定したファクションのすべてのMythicMobを削除します。
- **/mm mobs killall** - アクティブなすべてのMythicMobを削除します。
- **/mm mobs killall -p** - すべての永続的なMythicMobを削除します。
- **/mm mobs spawn [mob_name]:<level> <amount> <world,x,y,z,yaw,pitch>** - 指定した名前のモブをスポーンします。
- **/mm mobs spawn -s [mob_name]:<level> <amount>** - サイレントでモブをスポーンします。
- **/mm mobs stats** - サーバーにロードされているモブ数に関する有用な情報を表示します。

## モブエッグコマンド

- **/mm egg**（エイリアス: **/mm e**）- エッグ関連コマンドのベース。
- **/mm egg get [mob_name] <amount>** - 指定したMythicMobのモブエッグを取得します。
- **/mm egg give [player] [mob_name] <amount>** - プレイヤーに指定したMythicMobのモブエッグを与えます。

## スポナーコマンド

- **/mm spawners**（エイリアス: **/mm s**）- スポナー関連コマンドのベース。
- **/mm s create [spawner_name] [mob_name]** - プレイヤーの照準の位置に新しいスポナーを作成します。
- **/mm s set [spawner_name] [setting] [value]** - スポナーの設定を変更します。
- **/mm s addcondition [spawner_name] [condition] [value]** - スポナー条件を追加します。
- **/mm s removecondition [spawner_name] [condition]** - スポナー条件を削除します。
- **/mm s info [spawner_name]** - 特定のスポナーに関する情報のリストを提供します。
- **/mm s listnear <distance>** - 近くのすべてのスポナーをリストします。
- **/mm s resettimers [name]** - リストされたスポナーのクールダウンとリセットタイマーをリセットします。
- **/mm s activate [name]** - 特定のモブスポナーを起動します。
- **/mm s cut [search_string]** - 指定した文字列に従ってスポナーのグループをカットします。
- **/mm s paste** - カットされたスポナーのグループを新しい相対位置に貼り付けます。
- **/mm s undo** - 前のカット操作を元に戻します。

スポナーコマンドでは以下のワイルドカードが使用できます：
- **g:group_name** - スポナーグループ全体でコマンドを実行します。
- **r:radius** - radius ブロック以内のすべてのスポナーでコマンドを実行します。
- **?** - 1文字のワイルドカード
- **\*** - 任意の数の文字のワイルドカード

## ユーティリティコマンド

- **/mm test cast [skillname]** - モブであるかのようにスキルを実行します。
- **/mm test mechanic [line]** - モブであるかのようにメカニクスラインを実行します。
- **/mm i get [droptable]** - モブがドロップするドロップテーブルからアイテムを取得します。

## シグナルコマンド

- **/mm signal <UUID> <signal>** - 特定のスキルを切り替えるためにモブにシグナルを送ります。

## メニューコマンド

- **/mm menu open [menu name]** - 関連するカスタムメニューを開きます。MythicMobs PremiumまたはMythicRPGが必要です。

## パーミッション

### 一般

- **mythicmobs.admin** - プラグインのコマンドへの完全アクセスを付与します。

### コマンド個別パーミッション

- **mythicmobs.command.info** - `/mm info` コマンドへのアクセス。
- **mythicmobs.command.mobs.list** - `/mm mobs list` コマンドへのアクセス。
- **mythicmobs.command.signal** - `/mm signal <mob.uuid> <signal>` コマンドへのアクセス。
- **mythicmobs.command.test.cast** - `/mm test cast` コマンドへのアクセス。
- **mythicmobs.command.test.addthreat** - `/mm test addthreat` コマンドへのアクセス。
- **mythicmobs.command.test.reducethreat** - `/mm test reducethreat` コマンドへのアクセス。
