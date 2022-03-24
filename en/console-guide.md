## Database > RDS for SQL Server > Console User Guide

## Database Instances

On Database Instances, you can create, modify, or delete database instances, or query status information of created database instances.

### Creating Database Instances

To create a database instance, click **Create Database Instances** on top left of the list and go to page for database instance creation.
Enter specifications, network, floating IP, database security group, and backup settings for the instance, click **Create Database Instances** and send a request for creation.

![Create Database Instances 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_create_001_kr.png)

* ❶ From Compute & Network, select a created VPC subnet.
* ❷ When a database security group is not available, click **Create Database Security Groups** to immediately create and apply a security group.
* For more details, see [Database Instances](./db-instance) and [Database Access](./database-connection).

With a database instance successfully created, you're automatically moved to the list of database instances. It takes a few minutes, or up to a few dozens of minutes, to create a database instance.

### List of Database Instances

Brief information of database instances can be listed.
One page shows up to 50 database instances on the list.

![List of Database Instances 001](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_list_001.png)

* ❶ Search is available by the name or UUID of a database instance.
* ❷ With a click on the condition, search results can be filtered by availability zone or database instance status.

![List of Database Instances > Conditions 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_list_cond_001_kr.png)

* ❸ Frequently used tasks can be performed.
* ❹ Not frequently used additional tasks can be performed.
* ❺ Pages can be navigated when the current list is refreshed or there are 50 DB instances or more.
* ❻ Current CPU usage and number of active sessions. The value is updated every minute.
* ❼ The DB instance status. Different status values and colors appear depending on the status. A spinner appears if the DB instance is in operation.

### Restarting DB Instance

Microsoft SQL Server process for the DB instance can be restarted. DB instances can be restarted using failover while using the high availability feature.

![List of Database Instances > Restart 001](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_restart_001_kr.png)

* ❶ If the DB instance is restarted, it will restart the Microsoft SQL Server process. If the Microsoft SQL Server process fails to be restarted, the DB instance VM is rebooted.
* ❷ With the high availability feature, failover can also be used to restart instances.

### Force restarting DB instance

If the status of the DB instance is determined to be abnormal, it may restart regardless of the current operation.

![Force restart DB instance 001](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_force_restart_001.png)

* ❶ When the **force restart** button is clicked after selecting a DB instance, the **force restart** confirmation window appears.

![Force restart DB instance 002](https://static.toastoven.net/prod_rds_mssql/20210713/output/db_instance_force_restart_002.png)

* ❷  **When the force restart** button is clicked, the DB instance gets forced to restart.

> [Caution]
> If you force restart, all the tasks you are currently working on will be lost. Any active VMs will reboot.
> After a force restart, the DB instance may not return to a normal state. In that case, please contact our Customer Center.

### Modifying Database Instances

Available database instances can be easily modified in the setting via web console.

![List of Database Instances 002](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_list_002_kr.png)

* ❶ Select a database instance to modify from the list and click Modify on top right.

After setting is changed, click **Modify** at the bottom of the page to modify database instance.  
Once request for modifying database instance is successfully made, you're moved to the list of database instances. It takes a few minutes, or up to a few dozens of minutes, to modify a database instance.

![Modify Database Instances 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_modify_001_kr.png)

* ❶ Unable to change the availability zone.
* ❷ With the change of database instance type, database shall restart.
* ❸ Unable to change storage type.
* ❹ Unable to reduce storage size, once it is increased.
* ❺ In order to use high availability, the storage backup period must be at least 1 day.
* ❻ If the high availability auto recovery is enabled, a scheduled task for high availability recovery that runs one hour after the completion of automatic failover is created.
* ❼ Unable to change user ID.
* ❽ Without password, change is unavailable.
* ❾ With the change of port, database shall restart.
* ❿ Unable to change VPC.
* ⓫ If you modify the task schedule time, the schedule time of the already created scheduled task is also changed.
* ⓬ If you click **Modify DB Instance**, a confirmation window for DB instance modification appears.
![Modify Database Instances > Confirm Model](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_modify_modal_001_kr.png)
    * If you click **Run Immediately**, it is changed immediately.
    * If you click **Schedule Task**, a task is scheduled at the task schedule time of the DB instance.

### Database Instance Details

Select a database instance to show View Details at the bottom of page for detail information.
The View Details panel is comprised of five tabs, providing more data related to each database instance.

#### Basic Information

You may check basic information of a selected database instance.

![DB Instance Details > Basic Information 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_inst_001_kr.png)

* ❶ Click **Change** to change name of a database instance.
* ❷ Click **Copy** to copy ID of database instance onto clipboard.
* ❸ A domain capable of accessing the DB instance gets exposed. You can click the domain to see the domain type and IP information.

![DB Instance Details > Basic Information 001 Domain](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_detail_inst_001_domain_kr.png)

* ❹ Clicking the **Copy** button will copy the domain information into the clipboard.
* ❺ Shows the database replication status of a high availability DB instance.
    * It takes some time for the database to be exposed to the web console after its creation.
    * Failover is not performed for databases of which status is not 'replicated'.
* ❻ Shows the security group of the applied DB. Hover the cursor over a DB security group name to see its security group rules.

![DB Instance Details > Basic Information 001 Security Rules](https://static.toastoven.net/prod_rds_mssql/20201215/bordered/db_instance_detail_inst_001_dsg_kr.png)

#### Monitoring

Find out relevant metrics of a selected database instance on a chart. For more detail usage, see [Server Dashboard](./console-guide#_20).

![Database Instance Details > Monitoring 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_mon_001.png)

#### Events

Check out relevant events of a selected database instance. For more details, see [Events](./console-guide#_12).

![DB Instance Details > Events 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_event_001.png)

#### Logs

Find out error logs of Microsoft SQL Server occurred at a selected database instance.
Error logs are aligned in the latest time order, with 10 lines of logs on each page.

![DB Instance Details > Logs 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_log_001.png)

* ❶ Select a period to query. Without a period specified, the recent week's error logs show.
* ❷ Initialize query period as default.
* ❸ Pagination is available when the current list is updated or if there are more than 10 lines of error logs.

#### Backups

Check out the setting related to backup of a selected database instance and backup file information.
One page shows up to 50 backups on the list.

![DB Instance Details > Backups 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_backup_001.png)

* ❶ Shows backup execution time. If time is not specified, time shows as the system defines.
* ❷ Shows creation time of the most recently executed backup.
* ❸ Search is available by the backup name.
* ❹ Restore database instances by using selected backups.
* ❺ Delete selected backups: only manual backups can be deleted.
* ❻ Create manual backup files.
* ❼ Pagination is available when the current list is updated or if there are more than 50 backup files.

#### Scheduled Task

You can check the scheduled tasks for the selected DB instance.
A list of up to 50 scheduled tasks appears on a screen.

![DB Instance Details > Scheduled Task 001](https://static.toastoven.net/prod_rds_mssql/20220315/db_instance_detail_reserved_process_001.png)

* ❶ If you click the **Condition** button, you can filter the results by scheduled task status.
    * 'All' searches for all status values ​​other than Deleted.
* ❷ Click **Edit** to change the time set for the scheduled task.
* ❸ Click **Run Immediately** to change the time for the scheduled task to the current time.
* ❹ Click **Delete** to delete a scheduled task.
    * You can delete scheduled tasks with status 'Scheduled', 'Registered', 'Canceled', 'Error', or 'Verification Failed'.
    * If you delete a scheduled task with 'Scheduled' or 'Registered' status, the task will not be executed.

### Backing up to object storage

The DB instance can be backed up and the backup file can be exported to the object storage.

![DB Instance Details > Back Up To Object Storage](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_obs_backup_menu.png)

After selecting a specific DB instance from the list, click the **Back up to object storage** button, which will then show the following popup:

![DB Instance Details > Back Up To Object Storage](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_backup_to_obs_modal.png)

* ❶ Enter the Tenant ID of the object storage where the backup file will be stored. This can be checked in the API endpoint settings in the object storage service web console.
* ❷ Enter the NHN Cloud account (e-mail) of the object storage where the backup will be stored.
* ❸ Enter the API password of the object storage where the backup will be stored.
* ❹ Enter the container name of the object storage where the backup will be stored.
* ❺ Enter the file path of the backup file to be stored in the container.
    * The folder name can be up to 255 bytes, and the full path up to 1024 bytes.
    * Specific forms such as . or .. cannot be used and special characters (' " < > ; /) and spaces are not allowed.
* ❻ Enter the name of the database to be backed up.
* ❼ Select whether to use differential backup.

Enter information and press **OK** to proceed with backup. Once backup completes, the backup file will be available for download from the entered object storage container.

![Check backup file uploaded to object storage](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_backup_to_obs_result.png)

### Recover from backup in object storage

A backup file in object storage can be recovered to a DB instance.

![DB Instance Details > Recover From Backup In Object Storage](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_obs_backup_menu.png)

After selecting a specific DB instance from the list, click the **Recover from backup in object storage** button to show the following popup:

![DB Instance Details > Recover From Backup In Object Storage Popup](https://static.toastoven.net/prod_rds_mssql/20210209/output/db_instance_backup_from_obs_modal.png)

* ❶ Enter the Tenant ID of the object storage where the backup file will be stored. This can be checked in the API endpoint settings in the object storage service web console.
* ❷ Enter the NHN Cloud account (e-mail) of the object storage where the backup will be stored.
* ❸ Enter the API password of the object storage where the backup will be stored.
* ❹ Enter the container name of the object storage where the backup will be stored.
* ❺ Enter the file path of the backup file to be stored in the container.
    * The folder name can be up to 255 bytes, and the full path up to 1024 bytes.
    * Specific forms such as . or .. cannot be used and special characters (' " < > ; /) and spaces are not allowed.
* ❻ Enter the name of the database to be backed up.
* ❼ Select whether to recover.

Press **OK** after entering the information and the backup process begins.

## Backups

On Backups, check out information on manual or auto backup files of all database instances.

### List of Backups

![List of Backups 001](https://static.toastoven.net/prod_rds_mssql/backup_list_001.png)

* ❶ Search is available by the backup name.
* ❷ Restore database instances by using selected backups.
* ❸ Delete selected backups: only manual backups can be deleted.
* ❹ Create manual backup files.
* ❺ Pagination is available when the current list is updated or if there are more than 50 backup files.

### Creating Backups

Click **Create Backups** on Backups and a popup shows to create a backup.
Select a database instance, enter name and click **Create** to execute backup.

![List of Backups 002](https://static.toastoven.net/prod_rds_mssql/backup_list_002.png)

* ❶ Select a database instance to back up. Only currently available database instances show.
* ❷ Enter name of a backup.
* For more details, see [Backup and Restoration](./backup-restore).

### Exporting backup to object storage

An auto backup file or manual backup file can be exported to object storage.

![Backup list 002](https://static.toastoven.net/prod_rds_mssql/20210209/output/backup_to_obs_menu.png)

Select the backup to be sent to object storage from the list and click the **Export to object storage** button.

![Backup List > Export Backup To Object Storage Popup](https://static.toastoven.net/prod_rds_mssql/20210209/output/backup_to_obs_modal.png)

* ❶ Enter the Tenant ID of the object storage where the backup file will be stored. This can be checked in the API endpoint settings in the object storage service web console.
* ❷ Enter the NHN Cloud account (email) or the IAM member ID of the object storage to store the backup file.
* ❸ Enter the API password of the object storage where the backup will be stored.
* ❹ Enter the container name of the object storage where the backup will be stored.
* ❺ Enter the file path of the backup file to be stored in the container.
    * The folder name can be up to 255 bytes, and the full path up to 1024 bytes.
    * Specific forms such as . or .. cannot be used and special characters (' " < > ; /) and spaces are not allowed.
* ❻ Enter the name of the database to be backed up.
* ❼ Select whether to use differential backup.

## Restoration

RDS for SQL Server supports Restoration with Backup and Point-in-time Restoration.  
For more details, see [Backup and Restoration](./backup-restore).

### Restoration with Backup

You may restore data by using backup, from the Backup tab or the backup tab of View Database Details.  
Select a backup for restoration from the list, click **Restore**, and it goes to the restoration page.

![Restoration 001](https://static.toastoven.net/prod_rds_mssql/restore_001.png)
![Restoration 002](https://static.toastoven.net/prod_rds_mssql/20220315/restore_002.png)

Select type of a newly created database instance and set up, and press **Restore Database Instances** at the bottom to restore the database instance.
Database instance type, storage type, storage size, port, parameter group, and database security group are automatically selected.

> [Caution]
> If the parameter group at the time of backup does not exist, default group is selected.  
> Only database security group that exists during backup is automatically selected.

![Restoration 003](https://static.toastoven.net/prod_rds_mssql/20220315/restore_003.png)

It takes a few minutes, or up to a few dozens of minutes, to restore a database instance.

### Point-in-time Restoration

When the backup retention cycle is more than a day, database instances can be restored to a point in time during such retention period.
Select a database instance to restore, click **Point-in-time Restoration** and it goes to the restoration page.

![Restoration 004](https://static.toastoven.net/prod_rds_mssql/restore_004.png)

Provided on the same page for Restoration with Backup, you can select a time to restore on top of the page.

![Restoration 005](https://static.toastoven.net/prod_rds_mssql/restore_005.png)

To restore to a different point in time other than recent available time, select **User Specified**.

![Restoration 006](https://static.toastoven.net/prod_rds_mssql/restore_006.png)

Select type of a newly created database instance and set up, and press **Restore Database Instances** at the bottom to restore the database instance.
It takes a few minutes, or up to a few dozens of minutes to restore a database instance.

## Events

On the Events tab, check out recent events or set up for event subscription.
For more details on events and subscription, see [Monitoring](./monitoring#_2).

### List of Recent Events

Check out events of recent occurrence. The 50 events that are exposed at one shot can be filtered out with many conditions.

![List of Recent Events 001](https://static.toastoven.net/prod_rds_mssql/event_list_001.png)

* ❶ Select an event type to show.
* ❷ Select a target to be searched with search words. Search is available with an event source or a message.
* ❸ Select time of event occurrence.
* ❹ With **Initialize**, all search conditions are set as default.
* ❺ Pagination is available when the current list is updated or if there are more than 50 events.

### Subscribing Events

Click **Register Event Subscription** on top of the list of event subscription, and a popup shows to subscribe an events.
Enter information of an event to subscribe, click **Create** at the bottom and you're subscribed to the event.

![Popup for Event Subscription 001](https://static.toastoven.net/prod_rds_mssql/event_subscription_create_001.png)

* ❶ Each event type can be subdivided into event codes and event sources.
* ❷ Select the user groups to be notified when the event occurs.
    * Supports Autocomplete input.

![Popup for Event Subscription 002](https://static.toastoven.net/prod_rds_mssql/event_subscription_002.png)

* Select an event type and then choose an event code under.

![Popup for Event Subscription 003](https://static.toastoven.net/prod_rds_mssql/event_subscription_003.png)

* ❶ Supports autocomplete.
    * Available event codes are filtered for a keyword.
    * Move up and down on your keyboard to select an event code, press Enter, and it is automatically completed.
    * You may delete an event code, which has already been added, by pressing the backspace or clicking **x**.
* ❷ You may select an event code with a click of the mouse.

![Popup for Event Subscription 004](https://static.toastoven.net/prod_rds_mssql/event_subscription_004.png)

* Shows event sources for each event type.
* ❶ Supports autocomplete.
    * Available event sources are filtered for a keyword.
    * Move up and down on your keyboard to select an event source, press Enter, and it is automatically completed.
    * You may delete an event source, which has already been added, by pressing the backspace or clicking **x**.
* ❷ You may select an event source with a click of the mouse.

## Parameter Groups

On Parameters, create a parameter group to be applied to a database instance, or modify parameters of a parameter group.

### Creating Parameter Groups

To create a parameter group, default value must be copied from an existing parameter group.
Select a target from the list of parameter groups, and click **Copy Parameter Groups**.

![List of Parameter Groups 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_001.png)

Enter name and description of a parameter group to newly create, and click **Copy** to create a parameter group.

![Copy Parameter Groups 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_copy_001.png)

### Modifying Parameter Groups

Click name of a target to modify from the list of parameter groups, and it goes to the parameter details.

![List of Parameter Groups 002](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_002.png)

Click **Edit Parameters** on top of the parameter details to enter into the edit mode.

![Parameter Group Details 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_001.png)

Modify the parameter, click **Save Changes** to modify parameters of the parameter group.

![Parameter Group Details 002](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_002.png)

* ❶ You may enter keyword to filter parameters that are exposed.
* ❷ All parameter changes are cancelled and it goes to the detail page.
* ❸ A popup shows to compare before and after changes are applied.

![Parameter Group Details 003](https://static.toastoven.net/prod_rds_mssql/parameter_group_detail_003.png)

* ❹ All parameters are returned to default.
* ❺❻ Error messages that occur during parameter modification show.

### Comparing Parameter Groups

Compare two different parameter groups to find different parameters.
Select two parameter groups to compare from the list.

![List of Parameter Groups 003](https://static.toastoven.net/prod_rds_mssql/parameter_group_list_003.png)

Click **Compare Parameter Groups** on top to check different parameters.

![Compare Parameter Groups 001](https://static.toastoven.net/prod_rds_mssql/parameter_group_diff_001.png)

## Database Security Groups

From the Database Security Groups tab, a database security group can be created or deleted. It is also possible to add, modify, or delete policy for each group.   
For more details on database security groups, see [Database Access](./database-connection).

### Creating Database Security Groups

On top of the list of database security groups, click **Create Database Security Groups**, and a popup shows to create a database security group.

![List of Database Security Groups 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_list_001.png)
![Create Database Security Groups 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_create_001.png)

* ❶ Click **+** to add security policy.

Click **OK** at the bottom of the popup to create a database security group.

### Modifying Database Security Groups

Select a database security group from the list, and click **Modify Database Security Groups** on top.

![Modify Database Security Groups 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_modify_001.png)

You may modify name and description of a database security group, although security policy can be modified from a separate setting.

### Modifying Security Policy

Select a database security group from the list, and View Details panel show at the bottom of the page to confirm and modify security policy.

![Database Security Group Details 001](https://static.toastoven.net/prod_rds_mssql/db_security_group_detail_001.png)

Click **Create Security Policy** from the panel, and a popup shows to create security policy.

![Database Security Group Details 002](https://static.toastoven.net/prod_rds_mssql/db_security_group_detail_002.png)Data

Select a database security group policy from the View Details panel to change or delete policy.

## Server Dashboard

On the Server Dashboard tab, check out performance metrics of a database instance on a chart.  
RDS for SQL Server, by default, provides two layouts, such as basic system metrics and basic SQL server metrics.
Default layout cannot be deleted or changed.

![Server Dashboard 001](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_001.png)

* ❶ Shows created database instances on the list. By selecting a database instance, relevant charts become available.
* ❷ With layout changes, find out new metrics.
* ❸ Set the chart query period based on the current time.

### How to Use User Layouts

Click **Create Layout** to create a layout.

![Server Dashboard 002](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_002.png)

![Server Dashboard 003](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_003.png)

You may add charts onto a new layout.

![Server Dashboard 004](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_004.png)

Select a layout, click **Add Charts**, and a popup shows to add more charts.

![Server Dashboard 005](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_005.png)

With more charts added, you can find them on the layout.

![Server Dashboard 006](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_006.png)

Charts on a user layout are free to be modified in the layout or size.

![Server Dashboard 007](https://static.toastoven.net/prod_rds_mssql/server_dashboard_list_007.png)

* ❶ Area 1 can be re-located with a drag & drop.
* ❷ To change the size, drag and drop the bottom right area.
* ❸ Added chart can be deleted.

## Notification Group

In the Notification Group tab, a notification group can be created and deleted. In addition, monitoring target, user group, and monitoring settings can be added, modified and deleted in the notification group.
Refer to [notification group](./monitoring) for more details regarding notification group.

### Create Notification Group

Click the **+ Create Group** button at the top of the notification group list and a popup will be displayed to create a notification group.

![notification group list 001](https://static.toastoven.net/prod_rds_mssql/notification_group_list_001.png)
![create notification group 001](https://static.toastoven.net/prod_rds_mssql/notification_group_create_001.png)
* ❶ Choose whether to enable or disable the notification group.
    * Notifications will not be received when disabled.
* ❷ Select the DB instance to monitor.
    * ![notification group DB instance 001](https://static.toastoven.net/prod_rds_mssql/notification_group_db_instance_001.png)
    * Supports Autocomplete input.
    * Only DB instance that is available, failed connection, and have insufficient storage can be selected.
    * Only DB instance that is available, failed connection, and have insufficient storage can be removed from the monitored DB instance.
* ❸ Select the user groups to be notified when the event occurs.
    * ![notification group user group 001](https://static.toastoven.net/prod_rds_mssql/notification_group_user_group_001.png)
    * Supports Autocomplete input.

Click the **OK** button at the bottom of the popup to create the notification group.

### Modify Notification Group

In the notification group list, click the **Edit** button at the right of the notification group to modify.
![notification group list 001](https://static.toastoven.net/prod_rds_mssql/notification_group_list_002.png)
![modify notification group 001](https://static.toastoven.net/prod_rds_mssql/notification_group_modify_001.png)

* Same as creating a notification group, the name, notification type, whether to enable or disable, monitoring target DB instance, and user group can be modified.


### Notification Group Monitoring Settings

In the notification group list, click the **Monitoring Settings** button at the right of the notification group to set to monitor.

![notification group monitoring setting 001](https://static.toastoven.net/prod_rds_mssql/notification_group_metric_001.png)

* ❶ New monitoring settings can be added by clicking the **+ Monitoring Setting** button.
    * ![add notification group monitoring setting 001](https://static.toastoven.net/prod_rds_mssql/notification_group_metric_add_001.png)
    * The threshold can be set to a value between over 0 and below 100.
    * The duration can be set to a value between over 0 and below 32,767.
* ❷ Click the button to modify the default monitoring settings.
* ❸ Click the button to delete the monitoring settings.

## User Group

In the User Group tab, a notification group can be created and deleted. In addition, the user list can be added, modified, and deleted in the user group.

### Create User Group

Click the **+ Create User Group** at the top of the user group list and a popup will be displayed to create a user group.

![user group list 001](https://static.toastoven.net/prod_rds_mssql/user_group_list_001.png)
![create user group 001](https://static.toastoven.net/prod_rds_mssql/user_group_create_001.png)
* ❶ Add and delete notification target.
    * ![create user group 001](https://static.toastoven.net/prod_rds_mssql/user_group_user_list_001.png)
    * Click the **Add** button on the right of the user to add as a notification target.
    * Click the **x** button on the right of the user’s name to remove it from the notification target.
    * Only the project members are displayed on the user list. Only the users who completed verification have their name and SMS displayed in addition.

Click the **OK** button at the bottom of the popup to create a user group.

### Modify User Group

In the user group list, click the **Edit** button at the right of the user group to be modified.

![modify user group 001](https://static.toastoven.net/prod_rds_mssql/user_group_modify_001.png)

* Same as creating the user group, the name and notification target can be modified.

## Scheduled Task

You can register a scheduled task when modifying a DB instance, changing a parameter group, or using high availability auto recovery.

### List of Scheduled Tasks
You can check the scheduled tasks for the selected DB instance.
A list of up to 50 scheduled tasks appears on a screen.

![DB Instance Details > Scheduled Task 001](https://static.toastoven.net/prod_rds_mssql/20220315/reserved_process_list_001_kr.png)

* ❶ If you click the **Condition** button, you can filter the results by scheduled task status.
    * 'All' searches for all status values ​​other than Deleted.
* ❷ Click **Edit** to change the time set for the scheduled task.
* ❸ Click **Run Immediately** to change the time for the scheduled task to the current time.
* ❹ Click **Delete** to delete a scheduled task.
    * You can delete scheduled tasks with status 'Scheduled', 'Registered', 'Canceled', 'Error', and 'Verification Failed'.
    * If you delete a scheduled task with 'Scheduled' or 'Registered' status, the task will not be executed.

### Edit a Scheduled Task
In the list of scheduled tasks, click the **Edit** button on the right of the scheduled task you want to modify.
![Scheduled Task List 001](https://static.toastoven.net/prod_rds_mssql/20220315/reserved_process_modify_modal_001_en.png)
* ❶ You can set the schedule time type.
    * Repeated Daily
        * The system tries starting a scheduled task every day at the set time.
        * If the task fails to start because another task is in progress, the task is tried again the next day.
    * After Specific Time
        * The system attempts to start the task after a specific time.
        * If there is another task in progress, the task starts after the running task is completed.
* ❷ Set the reservation time.
    * Repeated Daily
        ![modify scheduled task daily repeat 001](https://static.toastoven.net/prod_rds_mssql/20220315/reserved_process_modify_modal_002_kr.png)
        * The time interval must be set to at least 30 minutes.
    * After Specific Time
        ![modify scheduled task daily repeat 001](https://static.toastoven.net/prod_rds_mssql/20220315/reserved_process_modify_modal_003_kr.png)

### Run a Scheduled Task Immediately
In the list of scheduled tasks, click **Run Immediately** on the right of the scheduled task you want to run.
Running the scheduled task immediately changes the schedule time to the current time.
If there is a task currently in progress, it will start after completion of the task.

### Delete a Scheduled Task
In the list of scheduled tasks, click **Delete** on the right of the scheduled task you want to delete.
You can delete scheduled jobs with status 'Scheduled', 'Registered', 'Error', 'Canceled' or 'Verification Error'.
If you delete a scheduled task with 'Scheduled' or 'Registered' status, the task will proceed.

## Appendix 1. DB Instance Migration Guide for Hypervisor Maintenance

NHN Cloud periodically updates the hypervisor software of the DB instance to improve security and stability.
DB instances running on a hypervisor that requires maintenance must be migrated to the hypervisor where maintenance has been completed.

You can start DB instance migration from the NHN Cloud console.
Follow the guide below to use the migration feature in the console.
First, go to the project where the DB instance requiring maintenance is located.

### 1. Check the DB instance that requires maintenance.

A DB instance with a **Migrate** button next to its name is the instance that requires maintenance.

![planned migration 001](https://static.toastoven.net/prod_rds_mssql/20211109/planned_migration_001.png)

You can check the detailed maintenance schedule by hovering the mouse cursor over the **Migrate** button.

![planned migration 002](https://static.toastoven.net/prod_rds_mssql/20211109/planned_migration_002.png)

### 2. Stop applications connected to the DB instance that requires maintenance.

Take appropriate measures not to affect services connected to the DB.
If there is no way to do so without affecting the services, please contact the NHN Cloud Customer Center and we will guide you through the appropriate action.

### 3. Request migration of the DB instance that requires maintenance.

Click the **Migrate** button next to the DB instance that requires maintenance. When a confirmation window appears, click the **Migrate** button.

![planned migration 003](https://static.toastoven.net/prod_rds_mssql/20211109/planned_migration_003.png)

### 4. Wait for the DB instance migration to finish.

If the status of DB instance does not change, try clicking the 'refresh' button.

![planned migration 004](https://static.toastoven.net/prod_rds_mssql/20211109/planned_migration_004.png)

No operations can be performed on the DB instance while migration is in progress.
If the DB instance migration is not completed normally, it is automatically reported to the administrator, and NHN Cloud will contact you.
