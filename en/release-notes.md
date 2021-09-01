## Database > RDS for MS-SQL > Release Notes

### 2021. 09. 14.

#### 버그 수정

* 감시 서버 재구축 진행 중에 수동 백업을 진행할 수 있는 버그 수정
* drop procedure로 database를 drop 하는 도중 MS-SQL 문제로 실패했음에도 drop 된 것처럼 동작하던 버그 수정

### 2021. 08. 10.

#### Feature Improvements

* Modified to verify the integrity of the file by checking the checksum when uploading/downloading a file.
* Fixed to return an error when the quota is insufficient by performing a quota check in advance when creating instances, changing types, and expanding storage.

#### Bug Fixes

* Fixed an issue where the database items in the web console were incorrectly synchronized when repeatedly creating and deleting databases in instances with high availability.
* Fixed an issue where backups failed intermittently when repeatedly creating and deleting databases in instances with high availability.
* Fixed an issue where it was impossible to restore when trying to restore to a specific point in time.
* Fixed an issue where backups in use for restore could be deleted
* Fixed an issue where the log could not be looked up in SQL Server 2017 Standard (14.0.3294.2)

### 2021. 07. 13.

#### More Features

* Force restart feature added

#### Bug Fixes

* Fixed a bug in which a small amount of internet traffic is billed for connecting to the domain server in the instance without a floating IP
* Fixed a bug in which the reset button in the event list doesn’t work

### 2021. 06. 15.

* Added the notification group feature
* Added user group feature

### 2021. 05. 11.

### Feature Updates

* Added the checkbox that selects all backups

### 2021. 04. 13.

#### Features Development

* Modified the system so that users can select multiple backups and delete them at once
* Modified the system so that object storages can be restored with a different name

#### Features Updates

* Modified the system so that instances of which memory is less than 8GB cannot access the high availability feature

### March 9, 2021

####  Bug Fixes

* Added a verification logic to prevent the use of a manual backup of database of which recovery model is `SIMPLE` for restoration of high availability configuration

### February 9, 2021

#### Feature Updates

* New instance type supported (x1 type)

#### Bug Fixes

* Fixed an issue where manual backup of a database of which recovery model is set to `SIMPLE` fails

### January 12, 2021

#### Feature Development

- Added the Stored Procedure for deleting databases

#### Feature Updates

- Fixed the application to leave additional server events for creating instance
- Fixed the application to display the instance type category in the same manner as in the Compute & Network service
- Fixed the application to leave events on promoted primary servers when an auto failover occurs.

#### Bug Fixes

- Fixed a bug where an error would occur when restoring a previous backup after an auto failover.
- Fixed a bug where the database of the web console would sometimes be exposed multiple times on a high availability DB instance.
- Fixed a bug where an error would occur when restoring to the point in time right after creating instance
- Fixed a bug where a DB instance with a completed failover would often fail to edit.
- Fixed a bug where the name of a DB instance with a completed failover would not be exposed on the web console usage page under specific conditions.

### December 15, 2020

#### Feature Development

- High-availability DB instance feature added

### October 13, 2020

#### Bug Fixes

- Fixed a bug of DB instance restoration failure where it is rolled back to the time it was created

### September 15, 2020

#### Feature Updates

- Updated UX for a more subdivided representation of DB instance status

#### Bug Fixes

- Fixed a bug of failure to roll back to a certain point of time right after a new database is created
- Fixed a UI bug where the date insertion component failed to operate properly when Japanese was selected

#### Other

- Excluded c2.c2m2 instance from instances that can be generated

### August 11, 2020

#### Feature Updates

- Updated UX to use DB instance type and storage size of the original DB instance as default

#### Bug Fixes

- Fixed a bug that only allows restoration to 5 minutes before a desired time point.
- Fixed a bug where attempts to access a DB instance creator page are led to an error page in the absence of a subnet.

### July 14, 2020

#### Release of Alpha Service 

* TOAST Relational Database Service for SQL Server (RDS for MS-SQL) provides Microsoft SQL Server in the cloud environment.
