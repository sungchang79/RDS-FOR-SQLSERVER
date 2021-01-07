## Database > RDS for MS-SQL > 모니터링

DB 인스턴스의 각종 성능 지표와 DB 인스턴스, 백업, 파라미터 그룹, 보안 그룹에서 발생한 각종 이벤트를 모니터링할 수 있습니다.

## 서버 대시보드

서버 대시보드에서 성능 지표를 차트 형태로 시각화해 볼 수 있습니다. 지표는 1분에 한 번씩 수집되며 최대 5년간 보관됩니다. 지표 데이터는 5분, 30분, 2시간, 1일 단위의 평균값으로 집계됩니다. 집계 단위별 보관 기간은 아래와 같습니다.

| 집계 단위 | 보관 기간 |
| - | - |
| 1분 | 7일 |
| 5분 | 1개월 |
| 30분 | 6개월 |
| 2시간 | 2년 |
| 1일 | 5년 |

차트는 원하는 레이아웃으로 배치할 수 있으며, 레이아웃을 여러 개 생성해 목적에 따라 관리할 수 있습니다.

## 이벤트

이벤트는 RDS for MS-SQL이나 사용자에 의해 발생한 중요한 사건을 의미합니다. 이벤트는 이벤트 유형, 발생 일시, 원본 소스와 메시지로 구성됩니다. 이벤트는 웹 콘솔에서 조회 가능하며, 구독을 통해 이메일, SMS, 웹훅으로 이벤트 발생 알림을 받을 수 있습니다. 이벤트의 유형과 발생 가능한 이벤트는 아래와 같습니다.

| 이벤트 유형 | 이벤트 코드 | 이벤트 메시지 |
| - | - | - |
| DB_INSTANCE | DB_INSTANCE_CREATED | DB 인스턴스 생성 |
| DB_INSTANCE | DB_INSTANCE_CREATED_FAIL | DB 인스턴스 생성 실패 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_START | DB 인스턴스 서버 생성 시작 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_END | DB 인스턴스 서버 생성 종료 |
| DB_INSTANCE | DB_INSTANCE_SERVER_CREATE_FAIL | DB 인스턴스 서버 생성 실패 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_START | DB 인스턴스 백업 시작 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_END | DB 인스턴스 백업 완료 |
| DB_INSTANCE | DB_INSTANCE_BACKUP_FAIL | DB 인스턴스 백업 실패 |
| DB_INSTANCE | DB_INSTANCE_DELETED | DB 인스턴스 백업 삭제 |
| DB_INSTANCE | DB_INSTANCE_DELETED_FAIL | DB 인스턴스 백업 삭제 실패 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_START | DB 인스턴스 복원 시작 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_END | DB 인스턴스 복원 완료 |
| DB_INSTANCE | DB_INSTANCE_RESTORE_FAIL | DB 인스턴스 복원 실패 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_START | DB 인스턴스 수정 시작 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_END | DB 인스턴스 수정 완료 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_FAIL | DB 인스턴스 수정 실패 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_START | DB 인스턴스 보안 그룹 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_END | DB 인스턴스 보안 그룹 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_MODIFY_SECURITY_GROUP_FAIL | DB 인스턴스 보안 그룹 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_START | DB 인스턴스 재시작 시작 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_END | DB 인스턴스 재시작 완료 |
| DB_INSTANCE | DB_INSTANCE_REBOOT_FAIL | DB 인스턴스 재시작 실패 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_START | DB 인스턴스 고가용성 구성 복구 시작 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_END | DB 인스턴스 고가용성 구성 복구 완료 |
| DB_INSTANCE | DB_INSTANCE_RECOVER_HA_FAIL | DB 인스턴스 고가용성 구성 복구 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_START | DB 인스터스 고가용성 구성 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_END | DB 인스터스 고가용성 구성 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_HA_FAIL | DB 인스터스 고가용성 구성 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_START | DB 인스턴스 비밀번호 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_END | DB 인스턴스 비밀번호 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PASSWORD_FAIL | DB 인스턴스 비밀번호 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_START | DB 인스턴스 포트 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_END | DB 인스턴스 포트 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PORT_FAIL | DB 인스턴스 포트 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_START | DB 인스턴스 파라미터 그룹 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_END | DB 인스턴스 파라미터 그룹 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_PARAMETER_GROUP_FAIL | DB 인스턴스 파라미터 그룹 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_START | DB 인스턴스 타입 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_END | DB 인스턴스 타입 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLAVOR_FAIL | DB 인스턴스 타입 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_START | DB 인스턴스 스토리지 크기 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_END | DB 인스턴스 스토리지 크기 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_STORAGE_SIZE_FAIL | DB 인스턴스 스토리지 크기 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_START | DB 인스턴스 플로팅 IP 사용 여부 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_END | DB 인스턴스 플로팅 IP 사용 여부 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_FLOATING_IP_FAIL | DB 인스턴스 플로팅 IP 사용 여부 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_START | DB 인스턴스 백업 설정 변경 시작 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_END | DB 인스턴스 백업 설정 변경 완료 |
| DB_INSTANCE | DB_INSTANCE_CHANGE_BACKUP_CONFIG_FAIL | DB 인스턴스 백업 설정 변경 실패 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_AVAILABLE | DB 인스턴스 상태 정상화 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_FAIL_TO_CONNECT | DB 인스턴스 접속 불가 |
| DB_INSTANCE | DB_INSTANCE_STATUS_CHANGED_TO_STORAGE_FULL | DB 인스턴스 스토리지 부족 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_START | 고가용성 DB 인스턴스 자동 장애 조치 시작 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_END | 고가용성 DB 인스턴스 자동 장애 조치 완료 |
| DB_INSTANCE | HA_AUTOMATIC_FAILOVER_FAIL | 고가용성 DB 인스턴스 자동 장애 조치 실패 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_END | 고가용성 DB 인스턴스 승격 완료 |
| DB_INSTANCE | HA_AUTOMATIC_PROMOTE_FAIL | 고가용성 DB 인스턴스 승격 실패 |
| BACKUP | BACKUP_START | 백업 시작 |
| BACKUP | BACKUP_END | 백업 완료 |
| BACKUP | BACKUP_DELETED | 백업 삭제 |
| PARAMETER_GROUP | PARAMETER_GROUP_CREATED | 파라미터 그룹 생성 |
| PARAMETER_GROUP | PARAMETER_GROUP_MODIFIED | 파라미터 그룹 수정 |
| PARAMETER_GROUP | PARAMETER_GROUP_DELETED | 파라미터 그룹 삭제 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_CREATED | DB 보안 그룹 생성 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_MODIFIED | DB 보안 그룹 수정 |
| DB_SECURITY_GROUP | DB_SECURITY_GROUP_DELETED | DB 보안 그룹 삭제 |

### 이벤트 구독

이벤트 유형, 코드 및 소스로 구분하여 이벤트를 구독할 수 있습니다. '이벤트 유형'으로 구독하면 이벤트 유형에 포함된 모든 이벤트 코드의 알림을 받습니다. 알림이 너무 광범위할 경우 이벤트 코드와 소스로 세분화해 구독할 수 있습니다. 

프로젝트 멤버만 알림을 받을 사용자로 선택할 수 있습니다. 기본적으로 이메일로 이벤트 알림이 발송되며, 실명을  인증한 휴대폰 번호가 등록된 경우에만 SMS로 추가 이벤트 알림이 발송됩니다. 메일과 SMS 이외에도 웹훅을 등록하면 사전에 정의된 양식으로 HTTP 요청을 보냅니다. 웹훅의 양식은 아래와 같습니다.

#### Method, URL
```
POST {사용자가 등록한 웹훅 URL}
Content-Type: application/json;charset=UTF-8
```

#### Request Body
```json
{
    "name": "이벤트 구독 이름",
    "source": "이벤트 소스",
    "sourceId": "이벤트 소스 아이디",
    "category": "이벤트 유형",
    "code": "이벤트 코드"
}
```
