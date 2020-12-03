# sharding-jdbc-orchestration-test
This project is used to reproduce Sharding-JDBC loading configuration error with Zookeeper as Orchestration center. In the class `AppConfig`, using class `YamlOrchestrationShardingDataSourceFactory` to create the DataSource object and it throws error.

## Environment

JDK: Java 8

Gradle: 6.6

Zookeeper: 3.6.1

## Prepare

1. create two database **demo_ds_0** and **demo_ds_1**
2. create table user in the above 2 databases with following SQL statement.

```sql
DROP TABLE IF EXISTS user;
CREATE TABLE user (
    user_id bigint(20) NOT NULL COMMENT '用户 ID',
    username varchar(128) NOT NULL COMMENT '账号',
    PRIMARY KEY (`user_id`) COMMENT '用户的 ID 作为主键'
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;
```

## Run

In the terminal cd to the project folder and run the command `gradle bootRun`.

