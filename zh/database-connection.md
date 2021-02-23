## Database > RDS for SQL Server > Database Access 

Access is not directly allowed to an operating system of a database instance but is available only via such port entered when creating a database instance. 

## Database Port 

A random port between 1150 and 65535 can be specified as a database port.  

> [Caution]
> When a port for the kernel, service, or an application program of Windows server is specified, database may not run properly. 
> When there is a change in the database port for a created database instance, database shall restart. 

## VPC Subnet 

To create a database instance, choose VPC subnet of Compute & Network of the user.  
Network connection is activated between a database instance within same VPC subnet and an instance of Compute & Network. 
Database instance is disconnected from external networks, except user's VPC subnet. To allow external connection, it must be associated with a floating IP.  

## DB Security Group 

Database security group is enabled to protect database instances from other traffic. By adopting 'Positive Security Model', specific traffic is allowed while the other traffic are blocked.  
At the start of a service, a default security group is created, to block all traffic inflow. Therefore, access is not allowed only with a floating IP, but policy setting is required. 
Database security group is applied the same throughout the external access via floating IP and the internal access via private IP. 
Many security groups can be set for a database instance. By creating further security groups along with many policies and setting them to an instance, policies of all security groups are applied to the instance.   

| Item        | Description                                                         |
| ----------- | ------------------------------------------------------------ |
| Direction        | Inbound refers to inflow to an instance, while outbound means outflow from instance.  |
| Ether Type  | Version of EtherType IP: specify IPv4 or IPv6.  |
| Remote        | Range of an IP address can be specified. If the direction is 'Outbound', the destination is remote, but if it is 'Inbound', the departure is remote. <br> Depending on the policy direction, compare if the traffic departure or destination is IP address or range.  |
| Description        | Description for a security group policy can be added.  |

The port of a database security group is fixed as the port of database, and if database port is changed, the policy of database security group is also automatically changed and applied. 
Only inbound setting is allowed for a database security group. 
