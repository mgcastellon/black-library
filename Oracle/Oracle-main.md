## SPACE USED BY A TABLESPACE

select segment_name, segment_type, bytes/1024/1024 AS MB from dba_segments
where tablespace_name='TEST_TABLESPACE_NAME' and segment_type in ('TABLE','INDEX')
order by 3 desc;

select a.table_name, b.segment_type, b.BYTES/1024/1024, a.segment_name from dba_lobs a, dba_segments b
where a.tablespace_name='TEST_ABLESPACE' and b.segment_name=a.SEGMENT_NAME
order by 3 desc;


## FRA USAGE

SELECT Name, (SPACE_LIMIT/1024/1024/1024) Space_Limit_GB, SPACE_USED/1024/1024/1024 Space_Used_GB, SPACE_RECLAIMABLE/1024/1024/1024 Space_Reclaimable_GB, NUMBER_OF_FILES
FROM V$RECOVERY_FILE_DEST;

select * from V$RECOVERY_AREA_USAGE;


## SCHEMA SPACE

SELECT SUM(BYTES)/1024/1024 FROM DBA_EXTENTS MB
WHERE OWNER='EVERSUITE_MANGO';


## BASIC VIEWS

select * from v$instance
select * from v$system_parameter

## Identify SESSION - PID

SELECT  s.saddr, s.sid, s.serial#, s.username,
  s.osuser, s.machine, s.program, s.logon_time, s.status, 
  p.program, p.spid
FROM v$session s, v$process p
WHERE s.paddr = p.addr
AND p.spid IN (12345);
