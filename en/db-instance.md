## Database > RDS for SQL Server > Database Instance

## Database Instance

Database instance encompasses virtual equipment and installed Microsoft SQL Server, serving as the unit of Microsoft SQL Server provided by RDS for SQL Server. 
Direct access to a database instance is not allowed, but access is enabled only through the port entered when creating the database instance. 
Database instances can be identified by user-specified name or automatically assigned 32-bit ID. 
A database instance must be named, considering the following constraints: 

* Must be unique for each region. 
* Must be comprised of alphabets, numbers, -, _ ,and .only, between 4 and 100 characters.
* Must start with a letter. 

To create a database instance, user account and password setting is required, considering the following constraints: 

* User account must be between 4 and 16 characters, comprised of alphabets and numbers only, starting with a letter. 
* Password must be between 8 and 128, comprised of alphabets, numbers, !, $, #, and % only. 
* Password cannot include user's account name. 
* Password must include at least three categories out of capital letters, small-case letters, numbers, and special characters. 

### Availability Area

RDS for SQL Server has many availability areas under one system so as to prepare against failure in physical hardware. A failure occurred within an availability area does not affect other availability areas, raising availability of the entire service. Database instances that are dispersed and created in different areas can communicate via network, with no charges.   

> [Caution]
> The availability area of already-created database instance cannot be changed. 

### Version of Microsoft SQL Server

Only the SQL Server 2016 Standard version is supported.   

### Database Instance Type

Each type of database instance has different CPU core count and memory volume. 
To create a database instance, an appropriate type must be selected depending on the database workload. 

| Type    | Description |
| ------- | -------------------------------------------------|
| m2 | Configures balance between CPU and memory.   |
| c2 | Has higher performance setting for CPU. |
| r2 | Available when momory takes more volume than other reources|
| x1 | A type that supports high performance CPUs and memory. Used for services and applications that require high performance. |

It is easy to change the type of already-created database instance via web console.

> [Caution]
> Changing already-created database instance type requires minutes of downtime since database instance must be closed.

### DB 인스턴스 상태

DB 인스턴스의 상태는 아래와 같은 값들로 구성되며, 사용자의 행위와 현재 상태에 따라 변경됩니다.

| 상태    | 설명 |
| ------- | -------------------------------------------------|
| 사용 가능 | DB 인스턴스가 안정적이며, 여러 다른 행위를 할 수 있는 상태 |
| 접속 실패 | 데이터베이스 접속이 안되는 상태 |
| 스토리지 부족 | DB 인스턴스 스토리지의 여유 공간이 모자른 상태 |
| 생성 중 | DB 인스턴스가 생성 중인 상태 |
| 변경 중 | DB 인스턴스가 변경 중인 상태 |
| 백업 중 | DB 인스턴스가 백업 중인 상태 |
| 삭제 중 | DB 인스턴스가 삭제 중인 상태 |
| 재부팅 중 | DB 인스턴스가 재부팅 중인 상태 |
| 고가용성 구성 복구 중 | 고가용성 DB 인스턴스의 보조서버를 재구성하는 중 |
| 장애 조치 중 | DB 인스턴스가 장애 조치 중인 상태 |
| 장애 조치 완료 | DB 인스턴스가 자동 장애 조치가 완료되어 정지된 상태 |
| 에러 | 알 수 없는 이유로 DB 인스턴스를 사용할 수 없는 상태 |

### Storage Type

Database instances support two storage types: HDD or SSD. 
Since each storage type provides different performance and pricing, an appropriate storage type must be selected depending on the database workload.  
A storage type can be created from 20GB up to 2,000 GB. 
It is easy to change the size of already-created storage via web console. 

> [Caution]
> Changing already-created storage size requires minutes of downtime since database instance must be closed. 
> The type of already-created storage cannot be changed. 

## High-availability DB instance

High-ability DB instance increases availability and data durability, and provides fault-tolerant database. 
RDS for MS-SQL uses the mirroring function of the Microsoft SQL Server, consisting of a primary server, a secondary server, and an event monitor server, to offer high availability. The primary and secondary servers are created in different availability areas.

### Failover action

A failover action automatically takes place when the primary server becomes unavailable due to an unexpected failure. Upon failover, the failed primary server is halted to prevent split brain and the secondary server takes over the primary server. Applications do not have to be adjusted for this change, as the A record of the internal and external domains that are used to connect is automatically switched from the primary server to the secondary server. 
When failover is complete, high availability DB instances will disappear and the rest of DB instances are separated into two groups: the failed DB instances and the DB instances promoted due to the failure. The promoted DB instances inherit all the configurations of existing DB instances except backups. The promoted DB instances will not perform backed up immediately after the promotion. This is to prevent any system load after the failover action. 
The DB instances with failover completed can be restarted by pressing the [Restart] button.

### Manual failover action

A high availability DB instance can be manually restarted after the failover action to deal with failover. When restarting a DB instance using failover, manual failover is performed and the roles of the primary and secondary servers are switched. During failover, both primary and secondary servers will restart their Microsoft SQL Server process and their internal and external domain IPs will be changed. Connection to those servers may fail from a couple of seconds to a couple of minutes until the domains are successfully changed.

### Cautions and constraints

- You can use the high-availability DB instance only if the storage backup period is at least 1 day.
- High-availability configuration of different regions is not supported.
- You cannot use a secondary server for high-availability for read load balancing.
- A mirroring configuration is proceeded anew when you change the name of a high-availability instance database, and the process takes a certain amount of time. You may experience performance degradation during the mirroring configuration, and the failover action may not be executed properly when a failure occurs.
- Database of high-availability DB instances only supports Full Recovery Model. When change of recovery model is detected, it will be changed back to the Full Recovery Model.
- DB instances with completed failover may fail to operate or operate properly due to issues such as data loss on the account of failures.
- As the high availability feature is based on domains, if a Compute & Network service instance for a user is in a network environment where it cannot reach any DNS server, the relevant instance cannot access the DB instance through a domain and normal access will be blocked when a failover occurs.
- When a new database is created in a DB instance, it may take at least 5 minutes up to dozens of minutes for the database to be mirrored.
  - If a failover occurs before the mirroring is complete, the failover of the database won't be properly done.
- All databases of high-availability DB instances operate in the same server. When a failure occurs on a specific database, all databases will fail over.
- Failover is not performed if there is no mirrored database.
- User, login, and permission of the primary server will be duplicated to the secondary server.
  - Duplication takes at least 10 seconds up to dozens of minutes.
  - When a failure occurs before the copying process is complete, the corrections will be lost.
* SQL Server Agent jobs cannot be duplicated. When failover is complete, it needs to be created again in the promoted DB instance.
* The failover time is impacted by the recovery process; the larger the transaction, the longer the time.
* The auto failover feature will be temporarily disabled while changing a DB instance.
* Instances of which memory is less than 8GB cannot use the high availability feature