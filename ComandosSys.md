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
ALTER SYSTEM SET parameter_name = parameter_value [COMMENT = 'text'] [SCOPE = MEMORY  |  SPFILE  |  BOTH]

EJ:

ALTER SYSTEM SET open_cursors=600 SCOPE = SPFILE;
ALTER SYSTEM SET processes=300 COMMENT='29/05/2018 Antes tenia 150' SCOPE = SPFILE;

### Otra forma de consultar parametros
SELECT * FROM V$PARAMETER;
"Los parametros en vivos de la base"

SELECT * FROM V$SPPARAMETER;
"Los parametros en el archivo spfile"

SELECT * FROM V$PARAMETER where NAME='processes'; 
"Un parametro específico"

shutdown immediate
"Baja la base de datos siguiendo los 3 pasos"

STARTUP 
"Arranca la base de datos"

STARTUP [FORCE] [RESTRICT] [PFILE=filename]
[OPEN [RECOVER][database]]
| [NOMOUNT]
| [MOUNT]

ALTER DATABASE {MOUNT | OPEN }
ALTER DATABASE {OPEN READ WRITE | READ ONLY}

STARTUP PFILE=$ORACLE_HOME/dbs/initdb01.ora
