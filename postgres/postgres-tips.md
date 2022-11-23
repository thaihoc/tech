# Hướng dẫn Postgres cơ bản

## Quản lý database

```
CREATE DATABASE keycloak;
```

## Quản lý user (role) 

Tạo user:

```
CREATE USER keycloak WITH ENCRYPTED PASSWORD '1122';
```

Gán full quyền database cho user:

```
GRANT ALL PRIVILEGES ON DATABASE keycloak to keycloak;
```
