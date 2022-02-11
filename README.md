# Trino DB2 Plugin

This is a plugin for Trino that allow you to use DB2 Jdbc Connection

####  Connection Configuration

####  Create new properties file inside etc/catalog dir:

```
connector.name=db2
connection-url=jdbc:db2://host:port/dbname
connection-user=xxxx
connection-password=xxxx
```

####  Create a dir inside plugin dir called db2. To make it easier you could copy mysql dir to db2 and remove the mysql-connector and trino-mysql jars. Finally put the trino-db2 in plugin/db2 folder. Here is the sptes:

``` shell
cd /data/trino/plugin
cp -r /data/trino/plugin/mysql /data/trino/plugin/db2
rm /data/trino/plugin/db2/mysql-connector*
rm /data/trino/plugin/db2/trino-mysql*
```

```
docker cp D:\trino-db2-352.jar trino:/data/trino/plugin/db2
docker cp D:\trino-db2-352-services.jar trino:/data/trino/plugin/db2
docker cp D:\db2jcc-db2jcc4.jar trino:/data/trino/plugin/db2
```

####  Building Trino DB2 JDBC Plugin
mvn clean install
