## What is PostgreSQL?
PostgreSQL is an advanced, enterprise-class, and open-source relational database system. PostgreSQL supports both SQL (relational) and JSON (non-relational) querying. PostgreSQL is a highly stable database backed by more than 20 years of development by the open-source community. PostgreSQL is used as a primary database for many web applications as well as mobile and analytics applications.[source](https://www.postgresqltutorial.com/what-is-postgresql/)

## Getting started

### installation(Ubuntu)

Create the file repository configuration:
```ssh
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
```
Import the repository signing key:
```ssh
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
```
Update the package lists:
```ssh
sudo apt-get update
```
Install the latest version of PostgreSQL.(If you want a specific version, use 'postgresql-12' or similar instead of 'postgresql'):
```ssh
sudo apt-get install postgresql
```

### check status and running server

check if the postgres server is running
```ssh
service postgresql status
```
or
```ssh
pgrep -u postgres -fa -- -D
```
if the server is not running you can start the server by 
```ssh
sudo systemctl enable --now postgresql.service
```
or 
```ssh
sudo service postgresql start
```

### Accessing postgresql server

#### Accessing with Switching Accounts

After installation by default PostgreSQL created an account called postgres that is the default PostgreSQL Role. To log in this account, switch over to the postgres type this command:
```ssh
sudo -i -u postgres
```
To access a Postgres prompt type:
```ssh
$ psql
```

#### Accessing without Switching Accounts

Following is the command that will log into Postgres without the intermediary bash shell in between.:
```ssh
sudo -u postgres psql
```
#### Quit from Postgres prompt

To quit from Postgres prompt just type `\q` :
```ssh
postgres=# \q
```