## Database > RDS for MS-SQL > Release Notes

### March 9, 2021

####  Bug Fixes

* Added a verification logic to prevent the use of a manual backup of database of which recovery model is `SIMPLE` for restoration of high availability configuration

### February 9, 2021

#### Feature Updates
* New instance type supported (x1 type)

#### Bug Fixes
* Fixed an issue where manual backup of a database of which recovery model is set to “SIMPLE” fails

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
