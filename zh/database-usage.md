## Database > RDS for MS-SQL > Enable Database

RDS for MS-SQL uses database for internal control or restricts a few user authorities so as to provide automated management and backup at a stable manner. 

### Database for Control 

`rdsadmin` refers to database for internal control, which cannot be deleted or accessed by user.  
`rdsadmin` includes a table and stored procedure for management. 

### Name Change of Database 

To change name of a database, call a separate stored procedure, instead of a general ALTER statement.  
See the below example to change database name from `FOO` to `BAR`.

```sql
EXEC [master].[dbo].[rdsp_alter_database_name] N'FOO', N'BAR'
GO
```
