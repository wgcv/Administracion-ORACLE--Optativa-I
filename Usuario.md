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

