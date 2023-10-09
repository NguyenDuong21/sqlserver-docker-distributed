
# Config MSSQL SERVER distribution database using container with docker-compose

### Step 1:
Install docker: 
https://docs.docker.com/engine/install/

Install docker-compose:
https://docs.docker.com/compose/install/


### Step 2:
Clone this repository

### Step 3: Run docker compose under background
Run below command to start container:
```
docker compose up -d
```

### Step 4: Wait for a minute and check container running

Run below command to check two container:
```
docker ps
```

### Step 5: Access container db 1 and sqlserver 1
Access container db1:
```
docker exec -it [CONTAINER ID] /bin/bash
```

Access sqlserver1:

```
cd /opt/mssql-tools/bin/

./sqlcmd -S db1 -U sa -P <password>
```
Note: <password> specific in docker-compose as environment

### Step 6: Create db, add table, create link server ...
example: 
```
...
...
use master
go 
EXEC master.dbo.sp_addlinkedserver @server=N'db2', @srvproduct=N'SQL Server';
EXEC master.dbo.sp_addlinkedsrvlogin @rmtsrvname = N'db2', @rmtuser = 'sa', @rmtpassword = 'MssqlPass123', @useself = N'False';
...
...
```

END
