# PostgreSQL
## Create Users
```bash
sudo service postgresql start
echo $USER #Check user
sudo su - postgres;
createuser postgres -dslP
\q # quit
exit
```
## Change default template encoding to UTF8
```bash
psql -U postgres # or ubuntu
update pg_database set datallowconn = TRUE where datname = 'template0';
\c template0
update pg_database set datistemplate = FALSE where datname = 'template1';
drop database template1;
create database template1 with template = template0 encoding = 'UTF8';
update pg_database set datistemplate = TRUE where datname = 'template1';
\c template1
update pg_database set datallowconn = FALSE where datname = 'template0';
\q
```
```bash
psql -c "create database rails_bdd_development owner=ubuntu"
```