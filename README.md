# QUIZ_DATABASE


*Create a bigtablespace with the name "big_tbs_your_name" example 'big_tbs_andres". It should contains one datafile of 1Gb

CREATE BIGFILE TABLESPACE big_tbs_DAVID DATAFILE 'big_tbs_DAVID.dbf' SIZE 1G;

*Create a tablespace named "quiz" with three datafiles, each of them of 200Mb.

CREATE TABLESPACE quiz 
datafile 'quiz1.dbf' size 200M,
'quiz2.dbf' size 200M,
'quiz3.dbf' size 200M;

create profile perfil_quiz limit
sessions_per_user UNLIMITED 
CPU_PER_SESSION UNLIMITED 
idle_time UNLIMITED 
 CONNECT_TIME 45 
failed_login_attempts UNLIMITED;

CREATE USER USUARIODBA
identified by 123
default tablespace quiz;

GRANT perfil_quiz on USUARIODBA;

.