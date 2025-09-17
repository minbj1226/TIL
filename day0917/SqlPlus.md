## SQLPlus.exe 사용법
- Oracle DBMS에서 제공하는 DB Client 프로그램
- SQL문을 작성하고, 실행하고, 결과를 얻는 일
- SQL문과 SQLPlus문 2가지를 사용할 수 있다.

### SQL문
DDL(Data Definition Language): create, drop, alter, truncate
DCL(Data Control Language): commit, rollback, grant, revoke
DML(Data Manipulation Language): insert, update, delete, select

규칙: SQL문에 끝에는 반드시 ;을 넣어야 한다.

### SQLPlus문
Oracle DBMS에서만 제공되는 명령, show,set,column 등으로 ;을 넣지 않아도 실행되는 명령
show 설정명
set 설정명 옵션
column (col) 칼럼명 format 글자수

---------------------------------------------
접속)
-아이디와 비번을 노출하여 접속
sqlplus "아이디/비번" <- 아이디나 비번에 공백이 포함되어 있는 경우
sqlplus 아이디/비번

-아이디만 노출하여 접속
sqlplus 아이디

-아이디와 비번을 노출하지 않고 접속
sqlplus

### 계정 생성
-관리자 계정만 계정을 생성할 수 있다.("/as sysdba", system/managerjung)

*Oracle Version
8i 9i 10g 11g | 12c 19c 21c 23ai
-계정명만 사용	  | -계정명에 c##이 붙는 계정이 기본계정으로 사용
			  | c##scott
			  | -이전버전의 계정형태 가능
			  |
			  |

1.계정 생성)- 접속권한이 없음
``create user 계정명 identified by 비번;``

0.c##이 붙지 않은 이전 계정으로 만들 때)- _ORACLE_SCRIPT 활성화
``alter session set "_ORACLE_SCRIPT"=true;``

2.권한 부여)- 생성된 계정은 접속권한이 없음
-접속권한(connect)
``grant connect to scott;``

-DB사용권한(resource)
``grant resource to scott;``

3.테이블스페이스 사용권한 수정)
``alter user 계정명 default tablespace 테이블스페이스명 quota unlimited on 테이블스페이스명;``