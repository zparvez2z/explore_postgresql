## What is PostgreSQL?
PostgreSQL is an advanced, enterprise-class, and open-source relational database system. PostgreSQL supports both SQL (relational) and JSON (non-relational) querying. PostgreSQL is a highly stable database backed by more than 20 years of development by the open-source community. PostgreSQL is used as a primary database for many web applications as well as mobile and analytics applications.[source](https://www.postgresqltutorial.com/what-is-postgresql/)

## installation(Ubuntu)

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
