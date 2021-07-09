## Database > RDS for SQL Server > Monitoring

Performance indicators of a database instance, as well as events occurred at each database instance, backup, parameter group or security group can be monitored. 

## Server Dashboard

Server Dashboard helps to visualize performance indicators on a chart. Indicators are collected at every minute and retained for up to 5 years. Indicator data are collected by the average of 5 minutes, 30 minutes, 2 hours, or 1 day. Each collecting unit provides different retention period like below:  

| Collecting Unit | Retention Period |
| - | - |
| 1 minute | 7 days |
| 5 minutes | 1 month |
| 30 minutes | 6 months |
| 2 hours | 2 years |
| 1 day | 5 years |

Chart layout is made available as user needs, and many number of layouts can be created to meet management purposes.  

## Event

An event refers to an important incident incurred by RDS for SQL Server or user. An event is comprised of a category, date of occurrence, original source and message. It can be queried on a web console and notified via email, SMS, or webshook on subscription. Each event category may include event occurrences, like follows:  

| Event Category | Event Code | Event Message |
| - | - | - |
| DB_INSTANCE | DB_INSTANCE_CREATED | DB instance created |
| DB_INSTANCE | DB_INSTANCE_CREATED_FAIL | Creating DB instance failed |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_START | DB 인스턴스 서버 생성 시작 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_END | DB 인스턴스 서버 생성 종료 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_FAIL | DB 인스턴스 서버 생성 실패 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_START | Backup of DB instance started  |
| DB_INSTANCE | DB_INSTANCE_BACKUP_END | DB instance backed up  |
| DB_INSTANCE | DB_INSTANCE_BACKUP_FAIL | Backup of DB instance failed  |
| DB_INSTANCE | DB_INSTANCE_DELETED | Backup of DB instance deleted  |
| DB_INSTANCE | DB_INSTANCE_DELETED_FAIL | Deleting DB instance backup failed |
| DB_INSTANCE | DB_INSTANCE_RESTORE_START | DB instance restoration started  |
| DB_INSTANCE | DB_INSTANCE_RESTORE_END | DB instance restored  |
| DB_INSTANCE | DB_INSTANCE_RESTORE_FAIL | Restoring DB instance failed  |
| DB_INSTANCE | DB_INSTANCE_MODIFY_START | Modifying DB instance started |
| DB_INSTANCE | DB_INSTANCE_MODIFY_END | DB instance modified |
| DB_INSTANCE | DB_INSTANCE_MODIFY_FAIL | Modifying DB instance failed |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_START | Changing DB instance security group started |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_END | DB instance security group changed |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_FAIL | Changing DB instance security group failed |
| DB_INSTANCE | DB_INSTANCE_REBOOT_START | DB instance restarted |
| DB_INSTANCE | DB_INSTANCE_REBOOT_END | Restarting DB instance completed |
| DB_INSTANCE | DB_INSTANCE_REBOOT_FAIL | Restarting DB instance failed  |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_START | DB 인스턴스 고가용성 구성 복구 시작 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_END | DB 인스턴스 고가용성 구성 복구 완료 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_FAIL | DB 인스턴스 고가용성 구성 복구 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_START | DB 인스터스 고가용성 구성 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_END | DB 인스터스 고가용성 구성 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_FAIL | DB 인스터스 고가용성 구성 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_START | Changing DB instance password started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_END | Changing DB instance password completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_FAIL | Changing DB instance password failed  |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_START | Changing DB instance port started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_END | Changing DB instance port completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_FAIL | Changing DB instance port failed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_START | Changing DB instance parameter group started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_END | Changing DB instance parameter group completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_FAIL | Changing DB instance parameter group failed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_START | Changing DB instance type started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_END | Changing DB instance type completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_FAIL | Changing DB instance type failed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_START | Changing DB instance storage size started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_END | Changing DB instance storage size completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_FAIL | Changing DB instance storage size failed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_START | Changing started for whether to use DB instance floating IP |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_END | Changing completed for whether to use DB instance floating IP |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_FAIL | Changing failed for whether to use DB instance floating IP |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_START | Changing DB instance backup setting started |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_END | Changing DB instance backup setting completed |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_FAIL | Changing DB instance backup setting failed |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_AVAILABLE | DB 인스턴스 상태 정상화 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_FAIL_TO_CONNECT | DB 인스턴스 접속 불가 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_STORAGE_FULL | DB 인스턴스 스토리지 부족 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_START | 고가용성 DB 인스턴스 자동 장애 조치 시작 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_END | 고가용성 DB 인스턴스 자동 장애 조치 완료 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_FAIL | 고가용성 DB 인스턴스 자동 장애 조치 실패 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_END | 고가용성 DB 인스턴스 승격 완료 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_FAIL | 고가용성 DB 인스턴스 승격 실패 |
| BACKUP | BACKUP_START | Backup started |
| BACKUP | BACKUP_END | Backup completed |
| BACKUP | BACKUP_DELETED | Backup deleted |
| PARAMETER_GROUP | PARAMETER_GROUP_CREATED | Parameter group created |
| PARAMETER_GROUP | PARAMETER_GROUP_MODIFIED | Parameter group modified |
| PARAMETER_GROUP | PARAMETER_GROUP_DELETED | Parameter group deleted |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_CREATED | DB security group created |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_MODIFIED | DB security group modified |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_DELETED | DB security group deleted |

### Subscribing Events

You may subscribe events by each category, code or source. When subscribed by event category, for example, you'll be notified on every event code included in the event category. If the range of notification is too broad, subscription may be divided by event code or source.  

Only project members can be selected as notified users. By default, event notification is sent by email, and if mobile phone number is registered from real-name verification, additional notification is sent via SMS. In addition to email and SMS, with webhook registration, HTTP request is sent on a pre-defined form, which is like below. 

#### Method, URL
```
POST {URL for user-registered webhook}
Content-Type: application/json;charset=UTF-8
```

#### Request Body
```json
{
    "name": "Name of Event Subscription",
    "source": "Event Source",
    "sourceId": "ID of Event Source",
    "category": "Event Category",
    "code": "Event Code"
}
```
