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
