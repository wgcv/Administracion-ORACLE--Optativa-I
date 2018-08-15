# Usuario

## Crear usuario
CREATE USER PRUEBA_TOPICOS IDENTIFIED BY TOPICOS12;

## Cambiar contraseña
ALTER USER SYS IDENTIFIED BY Admincidt17;

El TABLESPACE temporal se asigna el temporal por defecto DFAULT_TEMP_TABLESPACE
## Dar permisos para conectarse y crear objetos (Como SYSDBA)}
GRANT CONNECT, RESOURCE TO PRUEBA_TOPICOS;

## Ver tablas del usuario
select * from user_tables;

## Crear una tabla
CREATE TABLE ALUMNOS (ID NUMBER, NOMBRES VARCHAR2(50), APELLIDOS VARCHAR2(50));


## Inserta un valor a la tabla
insert into alumnos (id, nombres, apellidos) values(1,'Tulio','Marco');

## Crear usuarios con opciones
CREATE USER TOP_DBA
IDENTIFIED by Top123
DEFAULT TABLESPACE EXAMPLE
TEMPORARY TABLESPACE TEMP
QUOTA UNLIMITED ON EXAMPLE
PROFILE DEFAULT
ACCOUNT LOCK;

## Ver a todos los usuarios
select * from DBA_USERS;

## Unlock user
alter user TOP_DBA account unlock;
## Privilegio Conectarse
GRANT CREATE SESSION TO TOP_DBA;
## Privilegio crear tabla
GRANT CREATE TABLE TO TOP_DBA;
## Ver la quota de cada usuario
select * from DBA_TS_QUOTAS;
### Crear una tabla de prueba
CREATE TABLE ALUMNOS (codigo Number(3), nombres varchar(50));
INSERT INTO ALUMNOS (codigo, nombres) VALUES (0, 'Ana');
## Consultar permisos orogados solo para objetos
select * from DBA_TAB_PRIVS where GRANTEE ='HR'

## Consultar prvilegios asigandos
select * from dba_sys_privs where grantee ='HR'


## Ver permisos
### Permisos de objetos
select * from dba_tab_privs where grantee='DBA'
### Permisos de sistema
select * from dba_sys_privs where grantee='DBA'

## Roles
### Crear rol
CREATE ROLE CLASE
### Ver roles
select * from DBA_ROLES
#### Agrgar permisos a rol
GRANT CREATE SESSION TO CLASES;
GRANT CREATE TABLE TO CLASE;
GRANT CREATE VIEW TO CLASE;
GRANT SELECT ON HR.EMPLOYEES TO CLASE;
### Asignar el rol a un usuario
GRANT CLASE TO PRUEBA_TOPICOS1
## Crear un sinonimo
CREATE SYNONYM PRUEBA_TOPICOS1.EPLOYEES FOR HR.EMPLOYEES;


## Profile
### Crear un nuevo perfil
create profile PROFILE_TOPICOS limit sessions_per_user 3  failed_login_attempts 3 password_life_time 1 password_reuse_max 2 password_lock_time 1 password_grace_time 1;
Tambien se puede usar el modo visual de PLSQL
### Ver los profiles creados
select * from DBA_PROFILE
### Asignar un profie
ALTER USER PRUEBA_TOPICOS1 PROFILE POFILE_TOPICOS;
