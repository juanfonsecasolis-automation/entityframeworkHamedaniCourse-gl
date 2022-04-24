# entityframeworkHamedaniCourse-gl
2022 Juan Fonseca-Solis. Notes and excercises of course https://gorillalogic.udemy.com/course/entity-framework-tutorial/

## 1 Pre-requisites 

### SQL server express

* DB installation:
```
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
sudo add-apt-repository "$(wget -qO- https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2019.list)"
sudo apt-get update
sudo apt-get install -y mssql-server
sudo /opt/mssql/bin/mssql-conf setup
```
* Verify that SQL server is running by hitting `systemctl status mssql-server --no-pager`
* Install the command line equivalent for the SSMS:
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
curl https://packages.microsoft.com/config/ubuntu/20.04/prod.list | sudo tee /etc/apt/sources.list.d/msprod.list
sudo apt-get update 
sudo apt-get install mssql-tools unixodbc-dev
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
```
* Connect to the DB: `/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P <password>`
* Then create DB 
```
CREATE DATABASE Pluto
Go
```

## 2 Project set-up
Run the Pluto.sql script provided by the course:
```
/opt/mssql-tools/bin/sqlcmd -S localhost -U SA -P <password> -i scripts/Pluto.sql 
```

Connect back to the DB and check that the tables, stored procedures, and functions were created:
```
SELECT TABLE_NAME FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_TYPE = 'BASE TABLE' AND TABLE_CATALOG='Pluto'
SELECT SPECIFIC_NAME FROM Master.INFORMATION_SCHEMA.ROUTINES WHERE ROUTINE_TYPE = 'PROCEDURE'
Go
```

## 3 Run
To be defined...

## 4 Theory
To be defined...

## 5 References
* Udemy. M. Hamedani. [Entity Framework in Depth: The Complete Guide](https://gorillalogic.udemy.com/course/entity-framework-tutorial)
* Microsoft. [Quickstart: Install SQL Server and create a database on Ubuntu](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-ubuntu?view=sql-server-linux-ver15&preserve-view=true)
