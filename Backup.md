# Respaldos
## EXP
### Generar un Respaldo
exp hr/hr FILE=C:\TOPICOS\hr.dmp LOG=C:\TOPICOS\hr.log

## Cargar Respaldo
IMP SYSTEM/Admincidt18 FILE=C:\TOPICOS\hr.dmp FROMUSER=HR TOUSER=TOPICOS3

### EXDP Y IMPDP
expdp system/Admincidt18 DIRECTORY=EXPORT_TOPICOS FULL=Y DUMPFILE=hr.dmp
