### ORACLE

##
![image](https://github.com/jaeweon/ORACLE/assets/34277606/9e645d15-c82c-44a7-82fe-2dced5a9acd9)
![image](https://github.com/jaeweon/ORACLE/assets/34277606/fc6827da-23e7-419b-b37b-e322aea3e066)


# SELECT
 SELECT [컬럼명1, 컬럼명2,... ] FROM [테이블명];


# INSERT
  INSERT INTO [테이블명]
  VALUES('data1', 2000, 'data2');

# UPDATE
  UPDATE [테이블명]
  SET [기존컬럼명1] = [새로운 값], [기존컬럼명2] = [새로운값];

# DELETE
  DELETE FROM [테이블명]
  
  
## DB(Database)
   데이터가 모여 있는 기지
   추상적인 용어

# DBMS(Database Management System)
   DB를 관리할 수 있는 구체적인 시스템
   오라클, 마리아DB, MySQL, MS-SQL, MongoDB, ...


# 계정
   sys : 모든 권한
   system : 계정 관리
   일반 계정: 스키마 관리(hr, scott, ...)

# 스키마
   정리가 잘 되어 있는 표들의 묶음, 상태

# 일반 계정 접속(hr)
   cmd 접속
   > sqlplus system/1234
   > password : 1234
   SQL> show user
   USER is "SYSTEM"
   SQL> alter user hr account unlock;
   SQL> alter user hr identified by hr;
   SQL> conn hr/hr
   SQL> show user
   USER is "HR"


# Connections 연동
   Project 안에 있는 Connections 우클릭
   > New > New Connection 클릭
   > Oracle 선택
   > host: localhost
     Database: XE
     username: hr
     password: hr

# RDBMS(관계형 데이터베이스 시스템)
   테이블끼리 서로 관계를 맺을 수 있다.
   
# SQL문(쿼리문)
- DDL, DMl, DCL, TCL
  스크립트 언어
  DBMS와 소통하는 언어
  - DDL(Data Definition Language) : 데이터 정의어
    1. CREATE : 테이블 생성
    	CREATE TABLE [테이블 명] (
	   [컬러명] [자료형(용량)] [제약조건]
	   ...
	);
    2. DROP : 테이블 삭제
    	DROP TABLE [테이블 명];
    3. ALTER : 테이블 수정
    	    - 테이블 명 수정 : RENAME TO [새로운 테이블 명]
    	    - 컬럼 추가 : ADD ([새로운 컬럼명] [자료형(용량)])
     	    - 컬러명 변경 : RENAME COLUMN [기존 컬러명] TO [새로운 컬럼명]
    	    - 컬럼 삭제 : DROP COLUMN [기존 컬러명]
    	    - 컬럼 수정 : MODIFY ([기존 컬러명] [자료형(용량)])
    4. TRUNCATE : 테이블 내용 
	TRUNCATE TABLE [테이블 명];
	
	
### 자료형(TYPE)
	
	
# COLUMN(열, 속성, 필드)
	공통된 값들의 주제

# ROW(행, 레코드, 튜플)
	하나의 정보

# PRIMARY KEY(PK)
	고유한 값
	각 행의 구분점으로 사용된다.
	중복이 없고 NULL값을 허용하지 않는다.
	*NULL : 아직 어떤 값을 넣을 지 모르겠다는 의미로 넣는 값.

------------------------------------------------------------------------
 - DML(Data Manipulation Language) : 데이터 조작어
   1. SELECT : 조회(검색)
      1) 원하는 컬럼을 골라서 조회할 때
      SELECT [컬럼명1, 컬럼명2, ...] FROM [테이블명] WHERE 조건식;
      
      2) 전체 컬럼을 조회할 때, 대신 컬럼명을 직접 작성하는 것보다는 느리다.
      SELECT * FROM [테이블명] WHERE 조건식;

   2. INSERT
      1) 컬럼을 생략할 수 있다, 이 때 default 제약조건이 발동된다.
      INSERT INTO [테이블명]
      ([컬럼명1], [컬럼명2], [...])
      VALUES([값1], [값2], [...]);

      2) 모든 값을 전부 작성해야 되며, 컬럼명은 직접 작성하지 않는다.
      INSERT INTO [테이블명]
      VALUES([값1], [값2], [...]);

   3. UPDATE : 수정
      UPDATE [테이블명]
      SET [기존 컬럼명1] = [새로운 값], [기존 컬럼명2] = [새로운 값]
      WHERE 조건식;

   4. DELETE : 삭제
      DELETE FROM [테이블명] WHERE 조건식;
------------------------------------------------------------------------
조건식 : 참 또는 거짓 둘 중 하나가 나오는 식
   >, < : 초과, 미만
   >=, <= : 이상, 이하
   = : 같다
   <>, !=, ^= : 같지 않다
   AND : 둘 다 참이면 참
   OR : 둘 중 하나라도 참이면 참

※ 위 연산자들은 WHERE절에서 사용가능하다.
------------------------------------------------------------------------

![alias](https://github.com/jaeweon/ORACLE/assets/34277606/8098848a-bbf4-4e0f-bb91-e20a99f472fd)


![groupby](https://github.com/jaeweon/ORACLE/assets/34277606/08e36ea4-53e6-4c86-a5f1-46572facc1e5)













# 동적 쿼리
사용방법
실행 중 변경 가능한 문자열 변수 또는 문자열 상수로 제공된 SQL문을 실행

ex) 
EXECUTE IMMEDIATE 'SELECT COUNT(*) FROM
emp' INTO v_cnt;


장점
사전에 정의되지 않은 SQL을 실행 시에 확정하여 실행 할 수 있다.
DML과 TCL외에도 DDL, DCL을 사용할 수 있다.

단점
프로그램을 작성하기 복잡하다

사용 이유
SQL이 몇 개 문장으로 고정될 수 없을 때
SQL이 실행될지 예측할 수 없는 경우
