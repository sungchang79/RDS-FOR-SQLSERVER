## Database > RDS for MS-SQL > 콘솔 사용 가이드

## DB 인스턴스

DB 인스턴스 탭에서는 DB 인스턴스의 생성, 수정, 삭제 등의 작업을 하거나, 현재 생성된 DB 인스턴스의 각종 상태 정보를 조회할 수 있습니다.

### DB 인스턴스 생성

DB 인스턴스를 생성하려면 먼저 DB 인스턴스 리스트 화면 좌측 상단의 [DB 인스턴스 생성] 버튼을 클릭하여 DB 인스턴스 생성 화면으로 이동합니다.
생성하고자 하는 DB 인스턴스의 사양, 정보, 네트워크, 플로팅 IP, DB 보안 그룹, 백업 설정을 입력한 후 [DB 인스턴스 생성] 버튼을 클릭하여 DB 인스턴스 생성 요청을 합니다.

![DB 인스턴스 생성 001](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_create_001_kr.png)

* ❶ Compute & Network 서비스에서 생성한 VPC 서브넷을 선택할 수 있습니다.
* ❷ DB 보안 그룹이 없을 경우, [DB 보안 그룹 생성] 버튼을 클릭하여 즉시 생성, 적용할 수 있습니다.
* 그외 자세한 사항은 [DB 인스턴스](./db-instance) 와 [데이터베이스 접속](./database-connection) 을 참고합니다.

DB 인스턴스 생성 요청에 성공하면, 자동으로 DB 인스턴스 리스트로 이동합니다. DB 인스턴스 생성에는 몇 분에서 몇십 분이 소요됩니다.

### DB 인스턴스 목록

DB 인스턴스의 간략한 정보 목록을 조회할 수 있습니다. 
한 화면에 최대 50개의 DB 인스턴스 목록이 노출됩니다. 

![DB 인스턴스 목록 001](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_list_001.png)

* ❶ DB 인스턴스 이름 및 UUID 로 검색할 수 있습니다.
* ❷ 조건 버튼 클릭 시, 가용성 영역과 DB 인스턴스 상태로 검색 결과를 필터링할 수 있습니다.

![DB 인스턴스 리스트 > 조건 001](https://static.toastoven.net/prod_rds_mssql/20200112/output/db_instance_list_cond_001_kr.png)

* ❸ 빈번하게 사용되는 작업을 수행할 수 있습니다.
* ❹ 빈번하게 사용되지 않는 추가 작업을 수행할 수 있습니다.
* ❺ 현재 목록을 갱신하거나, 50개 이상의 DB 인스턴스가 있을 경우, 페이지 이동을 할 수 있습니다.
* ❻ 현재 CPU 사용량과 활성 세션 개수를 나타냅니다. 값은 1분마다 갱신됩니다.
* ❼ DB 인스턴스의 상태를 나타냅니다. 상태에 따라 서로 다른 상탯값 및 색상이 나타납니다. DB 인스턴스가 작업 중이면 스피너가 나타납니다.

### DB 인스턴스 재시작

DB 인스턴스의 Microsoft SQL Server 프로세스를 재시작할 수 있습니다. DB 인스턴스가 고가용성 구성을 사용하면, 장애 조치를 이용해 재시작할 수 있습니다.

![DB 인스턴스 목록 > 재시작 001](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_restart_001_kr.png)

* ❶ DB 인스턴스를 재시작하면, Microsoft SQL Server 프로세스를 재시작하게 됩니다. 만약 Microsoft SQL Server 프로세스의 재시작에 실패할 경우 DB 인스턴스 VM이 리부팅됩니다.
* ❷ 고가용성 기능을 사용하는 경우 장애 조치를 이용해 재시작할 수도 있습니다.

### DB 인스턴스 강제 재시작

DB 인스턴스의 상태가 비정상이라고 판단되면, 현재 진행 중인 작업과 상관없이 강제로 재시작할 수 있습니다.

![DB 인스턴스 강제 재시작 001](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_force_restart_001.png)

* ❶ DB 인스턴스를 선택한 후, **강제 재시작** 버튼을 클릭하면 **강제 재시작** 확인 창이 나타납니다.

![DB 인스턴스 강제 재시작 002](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_force_restart_002.png)

* ❷  **강제 재시작** 버튼을 클릭하면 DB 인스턴스가 강제 재시작됩니다.

> [주의]
> 강제 재시작을 할 경우, 현재 작업 중인 모든 작업이 유실 됩니다. 동작 중인 VM이 재부팅됩니다.
> 강제 재시작 이후 DB 인스턴스의 상태가 정상으로 돌아오지 않을 수 있습니다. 해당 상황 발생 시 고객센터로 문의해주세요.

### DB 인스턴스 수정

사용 가능 상태의 DB 인스턴스는 웹콘솔을 통해 손쉽게 주요 설정을 변경할 수 있습니다.

![DB 인스턴스 리스트 002](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_list_002_kr.png)

* ❶ 수정하고자 하는 DB 인스턴스를 목록에서 선택 후, 우측 상단의 수정 버튼을 클릭합니다.

변경하고자 하는 설정을 변경 후, 페이지 하단의 [수정] 버튼을 클릭하여 DB 인스턴스를 수정합니다.
DB 인스턴스 수정 요청에 성공하면, 자동으로 DB 인스턴스 리스트로 이동합니다. DB 인스턴스 수정에는 몇 분에서 몇십 분이 소요됩니다.

![DB 인스턴스 수정 001](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_modify_001_kr.png)

* ❶ 가용성 영역은 변경할 수 업습니다.
* ❷ DB 인스턴스 타입 변경 시, 데이터베이스가 재시작됩니다.
* ❸ 스토리지 타입은 변경할 수 업습니다.
* ❹ 한번 증가시킨 스토리지 크기는 다시 줄일 수 없습니다.
* ❺ 백업 보관 기간이 1일 이상이어야 고가용성 기능을 사용할 수 있습니다.
* ❻ 사용자 ID 는 변경할 수 없습니다.
* ❼ 비밀번호를 입력하지 않으면, 변경되지 않습니다.
* ❽ 포트 변경 시, 데이터베이스가 재시작됩니다.
* ❾ VPC 는 변경할 수 없습니다.

### DB 인스턴스 상세

DB 인스턴스를 선택하면 화면 하단에 상세 보기 패널이 노출되어, 좀 더 상세한 정보를 확인할 수 있습니다.
상세 보기 패널은 5가지 탭으로 구성되어 있으며, DB 인스턴스와 연관된 추가 정보를 확인할 수 있습니다.

#### 기본 정보

선택한 DB 인스턴스의 기본정보를 확인할 수 있습니다.

![DB 인스턴스 상세 > 기본 정보 001](https://static.toastoven.net/prod_rds_mssql/20200112/output/db_instance_detail_inst_001_kr.png)

* ❶ [변경] 버튼 클릭 시, DB 인스턴스의 이름을 변경할 수 있습니다.
* ❷ [복사] 버튼 클릭 시, DB 인스턴스의 아이디를 클립보드로 복사합니다.
* ❸ DB 인스턴스에 접속할 수 있는 도메인이 노출됩니다. 도메인을 클릭하면 도메인의 타입과 아이피 정보를 볼 수 있습니다.

![DB 인스턴스 상세 > 기본 정보 001 도메인](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_detail_inst_001_domain_kr.png)

* ❹ [복사] 버튼 클릭 시, 도메인 정보를 클립보드로 복사합니다.
* ❺ 고가용성 DB 인스턴스의 데이터베이스 복제 상태를 표시합니다.
    * 데이터베이스 생성 후, 웹콘솔에 노출되기까지 일정 시간이 소요됩니다.
    * `복제됨` 상태가 아닌 데이터베이스는 자동 장애 조치가 되지 않습니다.
* ❻ 적용된 DB 보안 그룹을 확인할 수 있습니다. DB 보안 그룹 이름 위에 마우스 커서를 올려놓으면, 보안 그룹 규칙을 볼 수 있습니다.

![DB 인스턴스 상세 > 기본 정보 001 보안 규칙](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_detail_inst_001_dsg_kr.png)

#### 모니터링

선택한 DB 인스턴스와 연관된 지표를 차트를 통해 확인할 수 있습니다. 자세한 사용법은 [서버 대시보드](./console-guide#_20) 를 참고합니다.

![DB 인스턴스 상세 > 모니터링 001](https://static.toastoven.net/prod_rds_mssql/db_instance_detail_mon_001.png)

#### 이벤트

선택한 DB 인스턴스와 연관된 이벤트를 확인할 수 있습니다. 자세한 사용법은 [이벤트](./console-guide#_12) 를 참고합니다.

![DB 인스턴스 상세 > 이벤트 001](https://static.toastoven.net/prod_rds_mssql/db_instance_detail_event_001.png)

#### 로그

선택한 DB 인스턴스에서 발생한 Microsoft SQL Server 의 에러로그를 확인할 수 있습니다. 
에러로그 내용을 최신 순으로 정렬하며, 한화면에 최대 10줄의 에러로그를 확인할 수 있습니다.

![DB 인스턴스 상세 > 로그 001](https://static.toastoven.net/prod_rds_mssql/db_instance_detail_log_001.png)

* ❶ 조회 기간을 선택합니다. 별도로 지정하지 않으면 최근 일주일간의 에러로그를 조회합니다.
* ❷ 조회 기간을 기본값으로 초기화합니다.
* ❸ 현재 목록을 갱신하거나, 10줄 이상의 에러로그가 있을 경우, 페이지 이동을 할 수 있습니다.

#### 백업

선택한 DB 인스턴스의 백업 관련 설정 정보 및 백업 파일에 대한 정보를 확인할 수 있습니다.
한 화면에 최대 50개의 백업 목록이 노출됩니다. 

![DB 인스턴스 상세 > 백업 001](https://static.toastoven.net/prod_rds_mssql/db_instance_detail_backup_001.png)

* ❶ 백업 수행 시간이 노출됩니다. 백업 수행 시간을 지정하지 않았을 경우 시스템에서 지정한 시간이 노출됩니다.
* ❷ 가장 최근 수행된 백업의 생성 시각이 노출됩니다.
* ❸ 백업 이름으로 검색할 수 있습니다.
* ❹ 선택된 백업을 이용하여 DB 인스턴스를 복원합니다.
* ❺ 선택된 백업을 삭제합니다. 수동 백업만 삭제할 수 있습니다.
* ❻ 수동 백업 파일을 생성합니다.
* ❼ 현재 목록을 갱신하거나 50개 이상의 백업 파일이 있을 경우, 페이지 이동을 할 수 있습니다. 

### 오브젝트 스토리지에 백업

DB 인스턴스를 백업하고, 백업 파일을 오브젝트 스토리지로 내보낼 수 있습니다.

![DB 인스턴스 상세 > 오브젝트 스토리지에 백업](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_obs_backup_menu.png)

DB 인스턴스 목록에서 특정 DB 인스턴스를 선택 한 후, **오브젝트 스토리지로 백업** 버튼을 클릭하면 아래와 같은 팝업이 노출됩니다.

![DB 인스턴스 상세 > 오브젝트 스토리지에 백업 팝업](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_backup_to_obs_modal.png)

* ❶ 백업 파일이 저장될 오브젝트 스토리지의 Tenant ID를 입력합니다. 오브젝트 스토리지 서비스 웹 콘솔의 API 엔드포인트 설정에서 확인할 수 있습니다.
* ❷ 백업 파일이 저장될 오브젝트 스토리지의 NHN Cloud 계정(이메일)을 입력합니다.
* ❸ 백업 파일이 저장될 오브젝트 스토리지의 API 비밀번호를 입력합니다.
* ❹ 백업 파일이 저장될 오브젝트 스토리지의 컨테이너 이름을 입력합니다.
* ❺ 컨테이너에 저장될 백업 파일의 경로를 입력합니다.
  * 폴더 이름은 최대 255바이트이고, 전체 경로는 최대 1024바이트입니다.
  * 특정 형태(. 또는 ..)는 사용할 수 없으며 특수문자(' " < > ; /)와 공백은 입력할 수 없습니다.
* ❻ 백업을 수행할 데이터베이스 이름을 입력합니다.
* ❼ 차등 백업 여부를 선택합니다.

정보를 입력한 후, **확인** 버튼을 누르면 백업이 진행됩니다. 백업이 완료되면 입력한 오브젝트 스토리지의 컨테이너에서 백업 파일을 다운로드할 수 있습니다.

![오브젝트 스토리지에 올려진 백업 파일 확인](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_backup_to_obs_result.png)

### 오브젝트 스토리지에 있는 백업으로 복원

오브젝트 스토리지에 있는 백업 파일을 DB 인스턴스에 복원할 수 있습니다.

![DB 인스턴스 상세 > 오브젝트 스토리지에 있는 백업으로 복원](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_obs_backup_menu.png)

DB 인스턴스 목록에서 특정 DB 인스턴스를 선택한 후, [오브젝트 스토리지에 있는 백업으로 복원] 버튼을 클릭하면 아래와 대화 상자가 나타납니다.

![DB 인스턴스 상세 > 오브젝트 스토리지에 있는 백업으로 복원 팝업](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_backup_from_obs_modal.png)

* ❶ 백업 파일이 저장될 오브젝트 스토리지의 Tenant ID를 입력합니다. 오브젝트 스토리지 서비스 웹 콘솔의 API 엔드포인트 설정에서 확인할 수 있습니다.
* ❷ 백업 파일이 저장될 오브젝트 스토리지의 NHN Cloud 계정(이메일)을 입력합니다.
* ❸ 백업 파일이 저장될 오브젝트 스토리지의 API 비밀번호를 입력합니다.
* ❹ 백업 파일이 저장될 오브젝트 스토리지의 컨테이너 이름을 입력합니다.
* ❺ 컨테이너에 저장될 백업 파일의 경로를 입력합니다.
  * 폴더 이름은 최대 255바이트이고, 전체 경로는 최대 1024바이트입니다.
  * 특정 형태(. 또는 ..)는 사용할 수 없으며 특수문자(' " < > ; /)와 공백은 입력할 수 없습니다.
* ❻ 백업을 수행할 데이터베이스 이름을 입력합니다.
* ❼ 복원 여부를 선택합니다.

정보를 입력한 후, [확인] 버튼을 누르면 복원이 진행됩니다.

## 백업

백업 탭에서는 모든 DB 인스턴스의 수동, 자동 백업 파일에 대한 정보를 확인할 수 있습니다.

### 백업 목록

![백업 목록 001](https://static.toastoven.net/prod_rds_mssql/backup_list_001.png)

* ❶ 백업 이름으로 검색할 수 있습니다.
* ❷ 선택된 백업을 이용하여 DB 인스턴스를 복원합니다.
* ❸ 선택된 백업을 삭제합니다. 수동 백업만 삭제할 수 있습니다.
* ❹ 수동 백업 파일을 생성합니다.
* ❺ 현재 목록을 갱신하거나, 50개 이상의 백업 파일이 있을 경우, 페이지 이동을 할 수 있습니다.

### 백업 생성

백업 탭의 [백업 생성] 버튼을 클릭하면 백업을 생성하기 위한 팝업이 노출됩니다.
DB 인스턴스를 선택하고, 이름을 입력한 후 [생성] 버튼을 클릭하면 백업이 수행됩니다.

![백업 목록 002](https://static.toastoven.net/prod_rds_mssql/backup_list_002.png)

* ❶ 백업하려는 DB 인스턴스를 선택합니다. 현재 사용가능한 DB 인스턴스만 노출됩니다.
* ❷ 백업 이름을 입력합니다.
* 그외 자세한 사항은 [백업 및 복원](./backup-restore) 을 참고합니다.

### 오브젝트 스토리지로 백업 내보내기

자동 백업 파일 혹은 수동 백업 파일을 오브젝트 스토리지로 내보낼 수 있습니다.

![백업 목록 002](https://static.toastoven.net/prod_rds_mssql/20210209/output/backup_to_obs_menu.png)

백업 목록에서 오브젝트 스토리지로 내보낼 백업을 선택한 후, [오브젝트 스토리지로 백업 내보내기] 버튼을 클릭합니다.

![백업 목록 > 오브젝트 스토리지로 백업 내보내기 팝업](https://static.toastoven.net/prod_rds_mssql/20210713/output/backup_to_obs_modal.png)

* ❶ 백업 파일이 저장될 오브젝트 스토리지의 Tenant ID를 입력합니다. 오브젝트 스토리지 서비스 웹 콘솔의 API 엔드포인트 설정에서 확인할 수 있습니다.
* ❷ 백업 파일이 저장될 오브젝트 스토리지의 NHN Cloud 계정(이메일) 혹은 IAM 회원 ID를 입력합니다.
* ❸ 백업 파일이 저장될 오브젝트 스토리지의 API 비밀번호를 입력합니다.
* ❹ 백업 파일이 저장될 오브젝트 스토리지의 컨테이너 이름을 입력합니다.
* ❺ 컨테이너에 저장될 백업 파일의 경로를 입력합니다.
  * 폴더 이름은 최대 255바이트 이고, 전체 경로는 최대 1024바이트 입니다.
  * 특정형태(. 또는 ..)는 사용할 수 없으며 특수문자(' " < > ; /)와 공백은 입력 할 수 없습니다.
* ❻ 백업을 수행할 데이터베이스 이름을 입력합니다.
* ❼ 차등 백업 여부를 선택합니다.

## 복원

RDS for MS-SQL에서는 백업을 이용한 복원과 시점 복원을 지원합니다.
복원에 대한 자세한 사항은 [백업 및 복원](./backup-restore) 을 참고합니다.

### 백업을 이용한 복원

백업 탭 혹은 DB 인스턴스 상세 보기 패널의 백업 탭에서 백업을 이용한 복원을 할 수 있습니다.
복원에 사용할 백업을 목록에서 선택 한 후, [복원] 버튼을 클릭하면 복원 화면으로 이동합니다.

![복원 001](https://static.toastoven.net/prod_rds_mssql/restore_001.png)
![복원 002](https://static.toastoven.net/prod_rds_mssql/restore_002.png)

복원 화면에서 신규로 생성되는 DB 인스턴스의 타입 및 각종 설정을 한 후, 화면 하단의 [DB 인스턴스 복원] 버튼을 눌러 DB 인스턴스를 복원합니다.
백업이 수행된 시점의 DB 인스턴스 타입, 스토리지 타입, 스토리지 크기, 포트, 파라미터 그룹 및 DB 보안 그룹이 자동으로 선택됩니다.

> [주의]
> 백업 당시의 파라미터 그룹이 존재하지 않으면 기본 파라미터 그룹이 선택됩니다.
> 백업 당시에 존재하는 DB 보안 그룹만 자동으로 선택됩니다.

![복원 003](https://static.toastoven.net/prod_rds_mssql/restore_003.png)

DB 인스턴스 복원에는 몇 분에서 몇십 분이 소요됩니다.

### 백업 보관 기간 중 어느 한 시점으로 복원

DB 인스턴스의 백업 보관 주기가 1일 이상이면 백업 보관 기간 중 어느 한 시점으로 복원할 수 있습니다.
시점 복원할 DB 인스턴스를 선택한 후, [시점 복원] 버튼을 클릭하면 복원 화면으로 이동합니다.

![복원 004](https://static.toastoven.net/prod_rds_mssql/restore_004.png)

백업을 이용한 복원과 동일한 화면이지만, 화면 상단에서 복원할 시점을 선택할 수 있습니다.

![복원 005](https://static.toastoven.net/prod_rds_mssql/restore_005.png)

최근 복원 가능 시각 이외에 다른 시점으로 복원 하려면 [사용자 지정] 을 선택합니다.

![복원 006](https://static.toastoven.net/prod_rds_mssql/restore_006.png)

복원 화면에서 신규로 생성되는 DB 인스턴스의 타입 및 각종 설정을 한 후, 화면 하단의 [DB 인스턴스 복원] 버튼을 눌러 DB 인스턴스를 복원합니다.
DB 인스턴스 복원에는 몇 분에서 몇십 분이 소요됩니다.

## 이벤트

이벤트 탭에서는 최근 발생한 이벤트를 확인하거나, 이벤트 구독에 관한 설정을 할 수 있습니다.
이벤트와 구독에 대한 자세한 설명은 [모니터링](./monitoring#_2) 을 참고합니다.

### 최근 이벤트 목록

최근 발생한 이벤트를 확인할 수 있습니다. 한 번에 50개의 이벤트가 노출되며, 다양한 조건으로 필터링할 수 있습니다.

![최근 이벤트 목록 001](https://static.toastoven.net/prod_rds_mssql/event_list_001.png)

* ❶ 노출될 이벤트 유형을 선택합니다.
* ❷ 검색어로 검색할 대상을 선택합니다. 이벤트 소스 및 메시지로 검색할 수 있습니다.
* ❸ 노출된 이벤트 발생 일시를 선택합니다.
* ❹ [초기화] 버튼 클릭 시, 모든 검색 조건을 기본값으로 설정합니다.
* ❺ 현재 목록을 갱신하거나, 50개 이상의 이벤트가 있을 경우, 페이지 이동을 할 수 있습니다.

### 이벤트 구독하기

이벤트 구독 목록 상단의 [이벤트 구독 등록] 버튼을 클릭하면 이벤트를 구독할 수 있는 팝업이 노출됩니다.
구독할 이벤트 정보를 입력 후, 팝업 하단의 [생성] 버튼을 클릭하면 이벤트를 구독할 수 있습니다.

![이벤트 구독 팝업 001](https://static.toastoven.net/prod_rds_mssql/event_subscription_create_001.png)

* ❶ 이벤트 유형에 따라 이벤트 코드, 이벤트 소스를 좀더 세분화해서 선택할 수 있습니다.
* ❷ 이벤트 발생 시 알림을 보낼 사용자 그룹을 선택할 수 있습니다.
    * 자동 완성 입력을 지원합니다.

![이벤트 구독 팝업 002](https://static.toastoven.net/prod_rds_mssql/event_subscription_002.png)

* 이벤트 유형을 선택하면 해당 유형에 속하는 이벤트 코드를 선택할 수 있습니다.

![이벤트 구독 팝업 003](https://static.toastoven.net/prod_rds_mssql/event_subscription_003.png)

* ❶ 자동 완성 입력을 지원합니다.
    * 입력한 키워드에 따라 선택할 수 있는 이벤트 코드가 필터링 됩니다.
    * 키보드 방향키 위, 아래 키로 이벤트 코드를 선택한 후 엔터를 누르면 자동완성됩니다.
    * 이미 추가된 이벤트 코드는 백 스페이스키를 눌르거나 [x] 버튼을 클릭하면 삭제할 수 있습니다.
* ❷ 마우스로 이벤트 코드를 선택할 수 있습니다.

![이벤트 구독 팝업 004](https://static.toastoven.net/prod_rds_mssql/event_subscription_004.png)

* 이벤트 유형에 따른 이벤트 소스가 노출됩니다.
* ❶ 자동 완성 입력을 지원합니다.
    * 입력한 키워드에 따라 선택할 수 있는 이벤트 소스가 필터링 됩니다.
    * 키보드 방향키 위, 아래 키로 이벤트 소스를 선택한 후 엔터를 누르면 자동완성됩니다.
    * 이미 추가된 이벤트 소스는 백 스페이스키를 눌르거나 [x] 버튼을 클릭하면 삭제할 수 있습니다.
* ❷ 마우스로 이벤트 소스를 선택할 수 있습니다.

## 파라미터 그룹

파라미터 탭에서는 DB 인스턴스에 적용할 파라미터 그룹을 생성하거나, 파라미터 그룹의 파라미터를 수정할 수 있습니다.

### 파라미터 그룹 생성

파라미터 그룹을 생성하기 위해서는 기존 파라미터 그룹으로부터 기본값을 복사해야 합니다.
파라미터 그룹 목록에서 복사하고자 하는 대상을 먼저 선택한 이후, [파라미터 그룹 복사] 버튼을 클릭합니다.

![파라미터 그룹 리스트 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_001.png)

새로 생성할 파라미터 그룹의 이름 및 설명을 입력한 후 [복사] 버튼을 클릭하여 새로운 파라미터 그룹을 생성할 수 있습니다.

![파라미터 그룹 복사 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_copy_001.png)

### 파라미터 그룹 수정

파라미터 그룹 목록에서 수정하고자 하는 대상의 이름을 클릭하여, 파라미터 상세 화면으로 이동합니다.

![파라미터 그룹 리스트 002](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_002.png)

파라미터 상세 화면의 상단에 있는 [파라미터 편집] 버튼을 클릭하여 편집 모드로 진입합니다.

![파라미터 그룹 상세 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_001.png)

파라미터를 수정하고 [변경 사항 저장] 버튼을 클릭하여 파라미터 그룹의 파라미터를 수정합니다.

![파라미터 그룹 상세 002](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_002.png)

* ❶ 키워드를 입력하여 노출되는 파라미터를 필터링할 수 있습니다.
* ❷ 현재까지 수정된 모든 파라미터 변경사항이 취소하고 상세 화면으로 이동합니다.
* ❸ 변경 전과 후를 비교하여 보여주는 팝업이 노출됩니다.

![파라미터 그룹 상세 003](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_003.png)

* ❹ 모든 파라미터의 값을 기본값으로 초기화합니다.
* ❺❻ 파라미터 수정 과정에서 발생한 에러메시지가 노출됩니다.

### 파라미터 그룹 비교

서로 다른 2개의 파라미터 그룹을 비교하여 다른 파라미터 값이 무엇이 있는지 확인할 수 있습니다.
파라미터 목록에서 비교하고자 하는 파라미터 그룹 2개를 선택합니다.

![파라미터 그룹 리스트 003](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_003.png)

상단의 [파라미터 그룹 비교] 버튼을 클릭하여 서로 다른 파라미터의 값을 확인합니다.

![파라미터 그룹 비교 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_diff_001.png)

## DB 보안 그룹

DB 보안 그룹 탭에서는 DB 보안 그룹의 생성 및 삭제가 가능합니다. 또한 DB 보안 그룹에 정책을 추가, 수정, 삭제할 수 있습니다.
DB 보안 그룹에 대한 자세한 설명은 [데이터베이스 접속](./database-connection) 을 참고합니다.

### DB 보안 그룹 생성

DB 보안 그룹 목록 상단의 [DB 보안 그룹 생성] 버튼을 클릭하면, DB 보안 그룹을 생성할 수 있는 팝업이 노출됩니다.

![DB 보안 그룹 목록 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_list_001.png)
![DB 보안 그룹 생성 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_create_001.png)

* ❶ [+] 버튼을 클릭하여 보안 정책을 추가합니다.

팝업 하단의 [확인] 버튼을 클릭하여 DB 보안 그룹을 생성합니다.

### DB 보안 그룹 수정

DB 보안 그룹 목록에서 수정하고자 하는 DB 보안 그룹을 선택 후, 상단의 [DB 보안 그룹 변경] 버튼을 클릭합니다.

![DB 보안 그룹 수정 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_modify_001.png)

DB 보안 그룹의 이름과 설명을 수정할 수 있으며, 보안 정책은 별도로 수정해야 합니다.

### 보안 정책 수정

DB 보안 그룹 목록에서 DB 보안 그룹을 선택하면 화면 하단에 보안 정책을 확인, 수정할 수 있는 상세 보기 패널이 노출됩니다.

![DB 보안 그룹 상세 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_detail_001.png)

상세 보기 패널의 [보안 정책 생성] 버튼을 클릭하면, 보안 정책을 생성할 수 있는 팝업이 노출됩니다.

![DB 보안 그룹 상세 002](https://static.toastoven.net/prod_rds_mssql/db_security_group_detail_002.png)

상세 보기 패널에서 DB 보안 그룹 정책을 선택하면 정책을 변경, 삭제할 수 있습니다.

## 서버 대시보드

서버 대시보드 탭에서는 DB 인스턴스의 각종 성능 지표를 차트 형태로 확인할 수 있습니다.
RDS for MS-SQL 는 기본 시스템 지표 및 기본 SQL 서버 지표, 2개의 기본 레이아웃을 제공합니다.
기본 레이아웃은 삭제 및 변경이 불가능합니다.

![서버 대시보드 001](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_001.png)

* ❶ 생성된 DB 인스턴스가 목록에 노출됩니다. DB 인스턴스 선택 시, 연관된 차트를 확인할 수 있습니다.
* ❷ 레이아웃을 변경하여, 새로운 지표를 확인할 수 있습니다.
* ❸ 차트 조회 기간을 현재 시각 기준으로 설정합니다.

### 사용자 레이아웃의 활용

[레이아웃 만들기] 버튼을 클릭하여, 레이아웃을 신규로 만들수 있습니다.

![서버 대시보드 002](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_002.png)

![서버 대시보드 003](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_003.png)

신규로 생성한 레이아웃에 보고 싶은 차트를 추가할 수 있습니다.

![서버 대시보드 004](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_004.png)

레이아웃을 선택한 후, [차트 추가] 버튼을 누르면 차트 추가 팝업이 노출됩니다.

![서버 대시보드 005](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_005.png)

차트를 추가하면 레이아웃에 차트가 추가됩니다.

![서버 대시보드 006](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_006.png)

사용자 레이아웃의 차트는 자유롭게 배치를 수정하거나 크기를 변경할 수 있습니다.

![서버 대시보드 007](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_007.png)

* ❶ 1번 영역을 마우스로 드래그 & 드랍하여 위치를 변경할 수 있습니다.
* ❷ 우측 하단 영역을 마우스로 드래그 & 드랍하여 크기를 변경할 수 있습니다.
* ❸ 추가된 차트를 제거할 수 있습니다.

## 알림 그룹

알림 그룹 탭에서는 알림 그룹의 생성 및 삭제가 가능합니다. 또한 알림 그룹에 감시 대상, 사용자 그룹, 감시 설정을 추가, 수정, 삭제할 수 있습니다.
알림 그룹에 대한 자세한 설명은 [알림 그룹](./monitoring#_4) 을 참고합니다.

### 알림 그룹 생성

알림 그룹 목록 상단의 [+ 그룹 만들기] 버튼을 클릭하면, 알림 그룹을 생성할 수 있는 팝업이 노출됩니다.

![알림 그룹 목록 001](https://static.toastoven.net/prod_rds_mssql/notification_group_list_001.png)
![알림 그룹 생성 001](https://static.toastoven.net/prod_rds_mssql/notification_group_create_001.png)
* ❶ 알림 그룹의 활성화 여부를 선택할 수 있습니다.
    * 사용 안 함 선택시 알림이 오지 않습니다.
* ❷ 감시할 DB 인스턴스를 선택할 수 있습니다.
    * ![알림 그룹 DB 인스턴스 001](https://static.toastoven.net/prod_rds_mssql/notification_group_db_instance_001.png)
    * 자동 완성 입력을 지원합니다.
    * 사용 가능, 접속 실패, 스토리지 부족 상태의 DB 인스턴스만 선택 가능합니다.
    * 사용 가능, 접속 실패, 스토리지 부족 상태의 DB 인스턴스만 감시대상 DB 인스턴스에서 제거 가능합니다.
* ❸ 이벤트 발생 시 알림을 보낼 사용자 그룹을 선택할 수 있습니다.
    * ![알림 그룹 사용자 그룹 001](https://static.toastoven.net/prod_rds_mssql/notification_group_user_group_001.png)
    * 자동 완성 입력을 지원합니다.

팝업 하단의 [확인] 버튼을 클릭하여 알림 그룹을 생성합니다.

### 알림 그룹 수정

알림 그룹 목록에서 수정하고자 하는 알림 그룹의 우측 [편집] 버튼을 클릭합니다.
![알림 그룹 목록 001](https://static.toastoven.net/prod_rds_mssql/notification_group_list_002.png)
![알림 그룹 수정 001](https://static.toastoven.net/prod_rds_mssql/notification_group_modify_001.png)

* 알림 그룹 생성과 동일하게 이름, 알림 유형, 활성화 여부, 감시대상 DB 인스턴스, 사용자 그룹을 수정할 수 있습니다.


### 알림 그룹 감시 설정

알림 그룹 목록에서 감시 설정하고자 하는 알림 그룹의 우측 [감시 설정] 버튼을 클릭합니다.

![알림 그룹 감시 설정 001](https://static.toastoven.net/prod_rds_mssql/notification_group_metric_001.png)

* ❶ [+ 감시 설정] 버튼을 클릭하면, 새로운 감시가 추가됩니다.
    * ![알림 그룹 감시 설정 추가 001](https://static.toastoven.net/prod_rds_mssql/notification_group_metric_add_001.png)
    * 임곗값은 0이상 100이하의 값을 지정할 수 있습니다.
    * 지속 시간은 0이상 32,767이하의 값을 설정할 수 있습니다.
* ❷ 버튼을 클릭하면, 기존의 감시 설정을 수정할 수 있습니다.
* ❸ 버튼을 클릭하면, 감시 설정을 삭제할 수 있습니다.

## 사용자 그룹

사용자 그룹 탭에서는 사용자 그룹의 생성 및 삭제가 가능합니다. 또한 사용자 그룹의 사용자 목록을 추가, 수정, 삭제할 수 있습니다.

### 사용자 그룹 생성

사용자 그룹 목록 상단의 [+ 사용자 그룹 생성] 버튼을 클릭하면, 사용자 그룹을 생성할 수 있는 팝업이 노출됩니다.

![사용자 그룹 목록 001](https://static.toastoven.net/prod_rds_mssql/user_group_list_001.png)
![사용자 그룹 생성 001](https://static.toastoven.net/prod_rds_mssql/user_group_create_001.png)
* ❶ 통보 대상을 추가, 삭제할 수 있습니다.
    * ![사용자 그룹 생성 001](https://static.toastoven.net/prod_rds_mssql/user_group_user_list_001.png)
    * 추가하고자 하는 사용자 우측 [추가] 버튼을 클릭하면 통보 대상에 추가할 수 있습니다.
    * 삭제하고자 하는 사용자 이름 오른쪽 [x] 버튼을 클릭하면 통보 대상에서 제거할 수 있습니다.
    * 프로젝트 멤버만 사용자 목록에 노출됩니다. 실명 인증을 한 멤버만 이름과 SMS가 추가로 노출됩니다.

팝업 하단의 [확인] 버튼을 클릭하여 사용자 그룹을 생성합니다.

### 사용자 그룹 수정

사용자 그룹 목록에서 수정하고자 하는 사용자 그룹의 우측 [편집] 버튼을 클릭합니다.

![사용자 그룹 수정 001](https://static.toastoven.net/prod_rds_mssql/user_group_modify_001.png)

* 사용자 그룹 생성과 동일하게 이름, 통보 대상을 수정할 수 있습니다.