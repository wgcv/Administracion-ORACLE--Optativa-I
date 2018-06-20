# Table Space

### Ver los table Space

select * from DBA_TABLESPACES;
 
 ### Ver fisicamente donde estan ubicados los table space
 
 select * from dba_data_files;
select TABLESPACE_NAME, FILE_NAME, BYTES/(1024*1024) as MB from dba_data_files;
