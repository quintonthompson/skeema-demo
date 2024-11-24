# skeema-demo

## Local Development
### Start mysql server
- Get mysql image: `docker pull mysql:8.0`

- Start docker container: `docker run --name skeema-demo-mysql -e MYSQL_ROOT_PASSWORD=root -p 3306:3306 -d mysql:8.0`

- Use the `init.sql` file to initialize the local db: `mysql -h 127.0.0.1 -p < init.sql`
### Configure local environment
-  Use `skeema add-environment development` to configure the connection information for your dev environment(s): `skeema add-environment development -h localhost -S /var/run/mysqld/mysqld.sock`

### Diffing locally
- To diff your local changes run the following: `skeema diff development`

### Applying locally
- To apply your changes to local run the following: `skeema push development`

## Configure environments
- Use `skeema add-environment <environment>` to configure a new environment: `skeema add-environment <environment> -h localhost`

## Importing Schemas
- To import a schema you can run: `skeema init <environment> --host 127.0.0.1 --password`
