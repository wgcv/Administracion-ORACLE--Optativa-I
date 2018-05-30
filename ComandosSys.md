## Comandos como SYSDBA

sqlplus sys/Admincidt18 as sysdba

show user
"Enseña el usuario conectado"

show parameter
"Muestra la lista de parametros"

show parameter spfile
"Muestra el parametro especificado"

Create pfile from spfile;
"Genera un pfile desde un spfile"

### Como cambiar parametros de la base de datos
ALTER SYSTEM SET parameter_name = parameter_value [COMMENT 'text'] [SCOPE = MEMORY  |  SPFILE  |  BOTH]

EJ:

ALTER SYSTEM SET open_cursors=600 SCOPE = SPFILE

### Otra forma de consultar parametros
SELECT * FROM V$PARAMETER;
"Los parametros en vivos de la base"
SELECT * FROM V$SPPARAMETER;
"Los parametros en el archivo spfile"
