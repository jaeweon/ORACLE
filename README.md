### ORACLE

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

IDE 설치 - DBeaver
   https://dbeaver.io/download/
   > Windows (zip) 클릭 - 무설치 버전
   > 압축 해제 후 DBeaver.exe 실행
   > Sample Database는 만들지 않는다.

# Project 생성
   좌측 상단에 Project 탭 클릭
   > New Project 버튼 클릭(+모양)
   > 생성된 Project 우클릭
   > Set Active Project 클릭

# Connections 연동
   Project 안에 있는 Connections 우클릭
   > New > New Connection 클릭
   > Oracle 선택
   > host: localhost
     Database: XE
     username: hr
     password: hr

# Driver 연결
   Edit Driver Settings 클릭
   > Libraries 탭 클릭
   > 기존에 있는 라이브러리 전체 삭제
   > Add File
   > C:/oraclexe/app/oracle/product/11.2.0/server/jdbc/lib/ojdbc6.jar 추가
   > 확인

Test Connection 클릭 > Connected 성공


# RDBMS(관계형 데이터베이스 시스템)
   테이블끼리 서로 관계를 맺을 수 있다.


# 이러한 구조를 가지는 것을 Table, Relation(오라클), Class라고 부른다.

# COLUMN(열, 속성, 필드)
	공통된 값들의 주제

# ROW(행, 레코드, 튜플)
	하나의 정보

# PRIMARY KEY(PK)
	고유한 값
	각 행의 구분점으로 사용된다.
	중복이 없고 NULL값을 허용하지 않는다.
	*NULL : 아직 어떤 값을 넣을 지 모르겠다는 의미로 넣는 값.











