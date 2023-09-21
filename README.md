# aws_postgres_db

The aim here is to write the code to manage a database on AWS. The database loaded will be Pagila (a port of the Sakila Sample Database in MySQL.)

## Creating the Database
- Create an AWS EC2 Ubuntu instance
- Connect to the instance via SSH and run the script:
```
sudo apt update
sudo apt install -y postgresql
```

### Configuring a Postgres Database
```
sudo -u postgres psql template1
ALTER USER postgres with encrypted password 'your_password';
```

### Install the Client
```
sudo apt install -y postgresql-client
```

### Test Local Connection
```
sudo apt install postgresql-client
psql --host localhost --username postgres --password --dbname template1
```

### Install the Pagila Database
```
wget https://raw.githubusercontent.com/aiven/devportal/main/code/products/postgresql/pagila/pagila-data.sql
psql --host localhost --username postgres --password --dbname template1
CREATE DATABASE pagila;
\c pagila;
\i pagila-data.sql;
```
