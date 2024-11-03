# Database Component

## Summary
Under construction

## Steps for build and run a single database


## 1.Create sql files:
Create a 'db' folder and include the following files:
- 'schema.sql' : Contains te SQL statements for create tables [Using DDL]
- 'data.sql' : Cointains the SQL statements for insert initial data [using DML]


### 2.Create 'Dockerfile'
Set postgres image base:
- FROM postgres:14

Add lines for copy files into container:
- COPY schema.sql /docker-entrypoint-initdb.d/00-schema.sql
- COPY data.sql /docker-entrypoint-initdb.d/01-data.sql


### 3. Build database image
inside database folder:

```
docker build -t laustefania/facturion_01  .
```

### 4. Run server with postgres

```
docker run --name facturion_01 -p 0.0.0.0:5432:5432 -e POSTGRES_PASSWORD=aP4sw0rd laustefania/facturion_01
```

### Run integrate with dockercompose
Under development
