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

# 오라클 DBMS 버전
   i : internet
   g : grid
   c : cloud

# 오라클 DBMS 설치 - 11G
https://drive.google.com/file/d/1rM1Z7-mA6vjySBgwWLr3ZI883xiL27HN/view?usp=sharing

# 압축 해제 > DISK1/setup.exe 실행 > Next > I Agree.. 체크 > Next > Next > 비밀번호 1234
> Next > 정보 확인 후 Install > Finish

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
































