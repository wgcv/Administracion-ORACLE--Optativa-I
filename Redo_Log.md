# Redo Log Files
## Información sobre los log
select * from v$log;
## Informació sobre los archivos log
select * from v$logfile

## Agregar miembros a los logfiles
ALTER DATABASE ADD LOGFILE MEMBER 'C:\APP\SOPORTETECNICO\ORADATA\ORCL\REDO04B.LOG' TO GROUP 4,
 'C:\APP\SOPORTETECNICO\ORADATA\ORCL\REDO03B.LOG' TO GROUP 3,
  'C:\APP\SOPORTETECNICO\ORADATA\ORCL\REDO02B.LOG' TO GROUP 2;
  
  ## Borrar un miembro de un grupo (No se puede borrar un miembro current, ni el último miembro o si esta mdo Archivelog y no esta archivado
  ALTER DATABASE DROP LOGFILE MEMBER 'C:\APP\SOPORTETECNICO\ORADATA\ORCL\REDO04B.LOG'
  
  ## Borrar un grupo (Debe tener almenos dos grupos. No borra el archivo en físico)
  Alter database DROP logfile group 4;
