# RDS

### Online Transaction Processing vs. Online Analytic
Processing


### Database Engines

### 只读副本

数据分析用，只读副本和master可以在不同的az甚至是不同的region
如果master宕机可以把只读副本提升为master，只读副本是异步，可能会丢失数据

### multi-az

多可用区部署必须在一个az，同步复制
多可用区部署是同步的，如果主库宕机，那么会转移到备用数据库


For MySQL and MariaDB, you can create a multi-AZ read replica in a different region. This lets you fail over to a different region. Multi-region failover isn’t supported for Micro- soft SQL Server, PostgreSQL, or Oracle.

Amazon Aurora gives you two options for multi-AZ: single-master and multi-master.

### 