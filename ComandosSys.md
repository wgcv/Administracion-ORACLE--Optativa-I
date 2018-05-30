## Comandos como SYSDBA

sqlplus sysAdmincidt18 as sysdba

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
