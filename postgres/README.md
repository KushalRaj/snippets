**Access PostgreSQL**
```
sudo -u postgres psql;
```
OR
```
sudo -i -u postgres;
psql;
```

**Create database**
```
CREATE DATABASE <?database_name?>
```
OR
```
createdb fnj_prod
```

**Create database user**
```
CREATE ROLE <?database_username?> WITH LOGIN PASSWORD '<?password?>’;
```
OR
```
createuser --interactive <?database_username?>
```
OR
```
createuser -P -s -e <?database_username?>
```

**Grant all permission to user on a database**
```
GRANT ALL PRIVILEGES ON DATABASE <?database_name?> TO <?database_username?>;
```

**Change user password**
```
REVOKE ALL PRIVILEGES ON <?database_name?> FROM <?database_username?>;
```

**Change user password**
```
ALTER USER <?database_username?> WITH PASSWORD '<?password?>';
```

**Delete a user**
```
drop user <?database_username?>;
```

**Alter table auto increment sequence**
```
ALTER SEQUENCE <?table_id_seq?> RESTART WITH <?start_from?>

eg. ALTER SEQUENCE product_id_seq RESTART WITH 1453
```

**List database user**
```
\du
```

**Connect to a database**
```
\c <?database_name?>
```
OR
```
\connect <?database_name?>
```

**List all database**
```
\list OR \l
```


###ADVANCE

**Drop all tables**
```
DROP SCHEMA public CASCADE;
CREATE SCHEMA public;
```

**Drop database**
```
drop database <?database_name?>;
```

**Alter table column**
```
ALTER TABLE <?table_name?> ALTER COLUMN <?column_name?> TYPE <?data_type?>;

eg. ALTER TABLE failed_jobs ALTER COLUMN payload TYPE JSON USING payload::JSON;
```

**Take database backup**
```
pg_dump -U <?database_username?> -h <?database_host?> <?database_name?> | gzip -c > <?filename?>.sql.gz
```

**Show config file path**
```
SHOW config_file;
```

**Remove postgres**
```
rm /usr/local/var/postgres/postmaster.pid
pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
```
