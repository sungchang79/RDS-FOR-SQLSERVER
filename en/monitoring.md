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

### 레이아웃

차트를 보기 위해서 레이아웃을 먼저 구성해야 합니다. 레아아웃은 여러 차트로 구성되며 각 차트의 위치와 크기를 저장합니다.
RDS for MS-SQL은 **기본 시스템 지표**, **기본 SQL 서버 지표** 2개의 기본 레이아웃을 제공합니다. 기본 레이아웃은 사용자가 수정, 삭제할 수 없습니다.

### 차트

DB 인스턴스의 각종 성능 지표를 차트 형태로 볼 수 있습니다. 성능 지표마다 각기 다른 형태의 차트로 구성되어 있습니다.
기본적인 시스템 지표 이외에 SQL Server의 `sys.dm_os_performance_counters`에서 제공하는 성능 지표를 차트로 제공하고 있습니다.

| 차트 | 지표 (단위) |
| --- | --- |
| CPU 사용률 | cpu used (%) |
| CPU 상세 | cpu user (%)<br> cpu system (%) |
| 메모리 사용량 | memory used (%) |
| 메모리 상세 | memory used (bytes)<br> memory free (bytes) |
| 스왑 사용률 | swap used (%) |
| 스왑 사용량 | swap used (bytes)<br> swap total (bytes) |
| 디스크 사용률 | storage used (%) |
| 디스크 전송률 | disk read (bytes)<br> disk write (bytes) |
| 네트워크 전송률 | nic incoming (bytes)<br> nic outgoing (bytes) |
| 네트워크 전송률 (pps) | nic incoming (pps)<br> nic outgoing (pps) |
| Batch requests/sec | Batch requests/sec (count) |
| Buffer cache hit ratio | Buffer cache hit ratio (%) |
| Checkpoint pages/sec | Checkpoint pages/sec (count) |
| Errors/sec | Errors/sec (count) |
| Full Scans/sec | Full Scans/sec (count) |
| Latch Waits/sec | Latch Waits/sec (count) |
| Lazy writes/sec | Lazy writes/sec (count) |
| Lock Waits/sec | Lock Waits/sec (count) |
| Number of Deadlocks/sec | Number of Deadlocks/sec (count) |
| Page life expectancy | Page life expectancy (seconds) |
| Page lookups/sec | Page lookups/sec (count) |
| SQL Compilations/sec | SQL Compilations/sec (count) |
| SQL Re-Compilations/sec | SQL Re-Compilations/sec (count) |
| Transactions/sec | Transactions/sec (count) |
| User Connections | User Connections (count) |

## 알림 그룹

알림 그룹을 통해 성능 지표에 대한 알림을 받을 수 있습니다.
알림 그룹에 감시 대상 인스턴스와 알림을 통보받을 사용자 그룹을 지정합니다.
감시 설정을 통해 알림을 받을 성능 지표의 임곗값과 조건을 설정합니다.
설정된 지표가 감시 설정의 조건을 충족하면 연결된 사용자 그룹에 알림을 발송하게 됩니다.
알림 그룹에 설정된 알림 유형에 따라 SMS 혹은 메일로 알림을 발송합니다.

### 감시 설정

감시 설정은 항목과 비교 방법, 임곗값, 지속 시간으로 구성됩니다. 감시 설정의 지속 시간은 중요한 요소입니다. 지속 시간은 감시 대상이 지정한 임계치에 도달한 후 그 상태가 지속되는 시간을 조건으로 지정할 때 사용합니다. 예를 들어, CPU 사용률의 임계치가 90% 이상이고 지속 시간이 5분이라면, 해당 알림 그룹과 연동된 서버의 CPU 사용률이 90% 이상인 상태가 5분 이상 지속되었을 때 사용자 그룹에 정의된 사용자들에게 알림을 보냅니다. 만약 CPU 사용률이 90% 이상이 되어도, 5분 이내에 90% 미만으로 떨어지면 알림이 발생하지 않습니다.

## 사용자 그룹

알림을 받을 사용자를 그룹으로 관리할 수 있습니다. 알림 대상은 반드시 프로젝트 멤버로 등록이 되어 있어야 합니다.
사용자 그룹에 속한 사용자가 프로젝트 멤버에서 제외되면, 사용자 그룹에 속해 있다 하더라도 알림을 받을 수 없습니다.

> [주의] 실명 인증을 하지 않아 휴대폰 정보가 없는 경우 SMS 알림을 받지 못합니다.

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
