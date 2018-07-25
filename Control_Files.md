# Control Files
## Desde SQL
show parameter control_files
## Vista
select * from v$parameter where name = 'control_files';
## Agregar o cambiar control files
ALTER SYSTEM SET control_files = 'C:\APP\SOPORTETECNICO\ORADATA\ORCL\CONTROL01.CTL', 'C:\APP\SOPORTETECNICO\FLASH_RECOVERY_AREA\ORCL\CONTROL02.CTL','C:\APP\SOPORTETECNICO\ORADATA\ORCL\CONTROL03.CTL' SCOPE=SPFILE;
## Ver Alert Log
show parameter background
## Genera un script para recrear un controlfile
ALTER DATABASE BACKUP CONTROLFILE TO TRACE
