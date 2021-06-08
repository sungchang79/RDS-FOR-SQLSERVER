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

### DB Instance Status

DB instance status consists of the following values, and it may change depending on the user's action and current status.

| Status    | Description |
| ------- | -------------------------------------------------|
| Available | The DB instance is stable capable of performing other actions |
| Connection failed | Cannot access the database |
| Not enough storage | DB instance storage does not have enough free space |
| Creating | DB instance is being created |
| Changing | DB instance is being changed |
| Backing up | The backup of DB instance is being made |
| Deleting | DB instance is being deleted |
| Rebooting | DB instance is being rebooted |
| Recovering high availability configuration | The secondary server for the high-availability DB instance is being reconfigured |
| Failing over | Failover is in progress for the DB instance |
| Failed over | The DB instance is successfully failed over and the process is stopped. |
| Error | Cannot use the DB instance due to unknown reasons |

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
