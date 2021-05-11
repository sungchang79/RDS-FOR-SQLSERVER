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

### 데이터베이스 삭제

데이터베이스를 삭제 하려면 일반적인 DROP 구문 대신, 별도의 저장 프로시저 (Stored Procedure) 를 호출해야 합니다.
아래 예제는 `FOO` 데이터베이스를 삭제하는 예제입니다.

```sql
EXEC [master].[dbo].[rdsp_drop_database] N'FOO'
GO
```