## Database > RDS for MS-SQL > モニタリング

DBインスタンスの各種性能指標およびDBインスタンス、バックアップ、パラメータグループとセキュリティグループで発生した各種イベントをモニタリングできます。

## サーバーダッシュボード

サーバーダッシュボードを通して、性能指標をチャート形式で視覚化して確認できます。指標は1分毎に収集され、最長5年間保管されます。指標データは5分、30分、2時間、1日単位の平均値で集計されます。各集計単位の保管期間は下記の通りです。

| 集計単位 | 保管期間 |
| - | - |
| 1分 | 7日 |
| 5分 | 1か月 |
| 30分 | 6か月 |
| 2時間 | 2年 |
| 1日 | 5年 |

チャートは、任意のレイアウトで配置することができます。レイアウトを複数作成して目的に応じて管理できます。

## イベント

イベントはRDS for MS-SQLまたはユーザーにより発生した重要事件を意味します。イベントは、イベントのタイプと発生日時、原本ソースとメッセージで構成されます。イベントはWebコンソールで照会可能です。購読することでメール、SMS、Webフックを通してイベント発生通知を受信することができます。イベントのタイプと発生可能なイベントは、下記の通りです。

| イベントタイプ | イベントコード | イベントメッセージ |
| - | - | - |
| DB_INSTANCE | DB_INSTANCE_CREATED | DBインスタンス作成 |
| DB_INSTANCE | DB_INSTANCE_CREATED_FAIL | DBインスタンス作成失敗 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_START | DBインスタンスサーバー作成開始 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_END | DBインスタンスサーバー作成終了 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_FAIL | DBインスタンスサーバー作成失敗 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_START | DBインスタンスバックアップ開始 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_END | DBインスタンスバックアップ完了 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_FAIL | DBインスタンスバックアップ失敗 |
| DB_INSTANCE | DB_INSTANCE_DELETED | DBインスタンスバックアップ削除 |
| DB_INSTANCE | DB_INSTANCE_DELETED_FAIL | DBインスタンスバックアップ削除失敗 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_START | DBインスタンス復元開始 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_END | DBインスタンス復元完了 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_FAIL | DBインスタンス復元失敗 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_START | DBインスタンス修正開始 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_END | DBインスタンス修正完了 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_FAIL | DBインスタンス修正失敗 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_START | DBインスタンスセキュリティグループ変更開始 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_END | DBインスタンスセキュリティグループ変更完了 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_FAIL | DBインスタンスセキュリティグループ変更失敗 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_START | DBインスタンス再起動開始 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_END | DBインスタンス再起動完了 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_FAIL | DBインスタンス再起動失敗 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_START | DBインスタンス高可用性構成の復旧開始 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_END | DBインスタンス高可用性構成の復旧完了 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_FAIL | DBインスタンス高可用性構成の復旧失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_START | DBインスタンス高可用性構成の変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_END | DBインスタンス高可用性構成の変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_FAIL | DBインスタンス高可用性構の成変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_START | DBインスタンスパスワード変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_END | DBインスタンスパスワード変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_FAIL | DBインスタンスパスワード変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_START | DBインスタンスポート変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_END | DBインスタンスポート変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_FAIL | DBインスタンスポート変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_START | DBインスタンスパラメータグループ変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_END | DBインスタンスパラメータグループ変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_FAIL | DBインスタンスパラメータグループ変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_START | DBインスタンスタイプ変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_END | DBインスタンスタイプ変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_FAIL | DBインスタンスタイプ変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_START | DBインスタンスストレージサイズ変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_END | DBインスタンスストレージサイズ変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_FAIL | DBインスタンスストレージサイズ変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_START | DBインスタンスFloating IP使用有無変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_END | DBインスタンスFloating IP使用有無変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_FAIL | DBインスタンスFloating IP使用有無変更失敗 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_START | DBインスタンスバックアップ設定変更開始 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_END | DBインスタンスバックアップ設定変更完了 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_FAIL | DBインスタンスバックアップ設定変更失敗 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_AVAILABLE | DBインスタンス状態正常化 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_FAIL_TO_CONNECT | DBインスタンス接続不可 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_STORAGE_FULL | DBインスタンスストレージ不足 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_START | 高可用性DBインスタンス自動フェイルオーバー開始 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_END | 高可用性DBインスタンス自動フェイルオーバー完了 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_FAIL | 高可用性DBインスタンス自動フェイルオーバー失敗 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_END | 高可用性DBインスタンス昇格完了 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_FAIL | 高可用性DBインスタンス昇格失敗 |
| BACKUP | BACKUP_START | バックアップ開始 |
| BACKUP | BACKUP_END | バックアップ完了 |
| BACKUP | BACKUP_DELETED | バックアップ削除 |
| PARAMETER_GROUP | PARAMETER_GROUP_CREATED | パラメータグループ作成 |
| PARAMETER_GROUP | PARAMETER_GROUP_MODIFIED | パラメータグループ修正 |
| PARAMETER_GROUP | PARAMETER_GROUP_DELETED | パラメータグループ削除 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_CREATED | DBセキュリティグループ作成 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_MODIFIED | DBセキュリティグループ修正 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_DELETED | DBセキュリティグループ削除 |

### イベント購読

イベントタイプ、コードおよびソースで区分してイベントを購読できます。イベントタイプで購読すると、イベントタイプに含まれるすべてのイベントコードの通知を受信します。通知があまりにも広範囲の場合、イベントコードとソースに細分化して購読できます。 

プロジェクトのメンバーのみ、通知を受信するユーザーに選択できます。基本的にメールでイベント通知が送信され、実名認証により携帯電話番号が登録された場合にのみSMSで追加イベント通知が送信されます。メールとSMS以外にもWebフックを登録すると、事前に定義したフォーマットでHTTPリクエストを送ります。Webフックのフォーマットは下記の通りです。

#### Method, URL
```
POST {ユーザーが登録したWebフックURL}
Content-Type: application/json;charset=UTF-8
```

#### Request Body
```json
{
    "name": "イベント購読名",
    "source": "イベントソース",
    "sourceId": "イベントソースID",
    "category": "イベントタイプ",
    "code": "イベントコード"
}
```
