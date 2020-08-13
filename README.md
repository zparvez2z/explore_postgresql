## What is PostgreSQL?
PostgreSQL is an advanced, enterprise-class, and open-source relational database system. PostgreSQL supports both SQL (relational) and JSON (non-relational) querying. PostgreSQL is a highly stable database backed by more than 20 years of development by the open-source community. PostgreSQL is used as a primary database for many web applications as well as mobile and analytics applications.[source](https://www.postgresqltutorial.com/what-is-postgresql/)

## Getting started

### installation(Ubuntu)

Create the file repository configuration:
```shell
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
```
Import the repository signing key:
```shell
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```
Update the package lists:
```shell
sudo apt-get update
```
Install the latest version of PostgreSQL.(If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql'):
```shell
sudo apt-get install postgresql
```

### check status and running server

check if the postgres server is running
```shell
service postgresql status
```
or
```shell
pgrep -u postgres -fa -- -D
```
if the server is not running you can start the server by 
```shell
sudo systemctl enable --now postgresql.service
```
or 
```shell
sudo service postgresql start
```

### Accessing postgresql command prompt

#### Accessing with Switching Accounts

After installation by default PostgreSQL created an account called postgres that is the default PostgreSQL Role. To log in this account, switch over to the postgres type this command:
```shell
sudo -i -u postgres
```
To access a Postgres prompt type:
```shell
$ psql
```

#### Accessing without Switching Accounts

Following is the command that will log into Postgres without the intermediary bash shell in between.:
```shell
sudo -u postgres psql
```
#### Quit from Postgres prompt

To quit from Postgres prompt just type `\q` :
```shell
postgres=# \q
```

### Some useful commands
`help` to display help.

`\l` to display list of databases

### Create database
There are two ways to create a database.

To create a database from shell type:
```shell
$ createdb database_name
```
To create a database from `psql` prompt:
```sql
CREATE DATABASE database_name;
```

### connect to specific database

To connect directly from shell prompt :
```shell
psql -h localhost -p 5432 -U user_name database_name
```
Connect from `psql` prompt :
```shell
postgres=# \c database_name
```
### delete database
following command will delete the database given. (be careful before using this command!)
```sql
DROP database_name;
```

### create table

```sql
CREATE TABLE person (
    id INT,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    gender VARCHAR(7),
    date_of_birth DATE);
```
