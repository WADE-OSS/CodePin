---
title : SQL 소개
info : SQL은 데이터베이스에서 데이터를 저장, 조작 및 검색하기 위한 표준 언어입니다. 이 글은 SQL(Structured Query Language)에 대한 소개 글 입니다.
categories : [sql]
tag : [시작하기]
---

# 소개
SQL(Structured Query Language)은 데이터베이스 시스템에서 자료를 처리하는 요도로 사용되는 구조적 데이터 질의 언어입니다. SQL은 어느 데이터베이스에서나 기본으로 제공하기 때문에 MySQL, SQL Server, MS Access, Oracle 등 에서 사용할 수 있습니다. (다만 [NoSQL데이터베이스](https://wade.pw/dictionary/nosql)에서는 사용 할 수 없습니다.)

## 구문
데이터베이스 언어는 다음 세 가지로 구분됩니다.

- [데이터 정의 언어](https://wade.pw/sql/introduction#데이터-정의-언어) (DDL : Data Definition Language)
- [데이터 조작 언어](https://wade.pw/sql/introduction#데이터-조작-언어) (DML : Data Manipulation Language)
- [데이터 제어 언어](https://wade.pw/sql/introduction#데이터-제어-언어) (DCL : Data Control Language)

## 데이터 정의 언어
데이터 정의 언어(DDL : Data Definition Language)는 관계형 데이터베이스의 구조를 정의합니다.SQL에 의해 정의되는 관계형 데이터베이스의 구조는 행, 열, 테이블, 인덱스 파일 위치 등 데이터베이스 고유의 특성을 포함하며, SQL의 데이터 정의 언어의 문장의 집합은 관계 데이터베이스 관리 시스템(RDBMS)의 일부이며 SQL 방언에 의해 많은 차이가 있을 수 있습니다.

- [CREATE](https://wade.pw/sql/create) - 새로운 데이터베이스 테이블, VIEW, 인덱스, 저장 프로시저를 만듭니다.
- [DROP](https://wade.pw/sql/drop) - 이미 존재하는 데이터베이스 테이블, VIEW, 인덱스, 저장 프로시저를 제거합니다.
- [ALTER](https://wade.pw/sql/alter) - 이미 존재하는 데이터베이스 개체에 대한 변경, RENAME의 역할을 합니다.
- [TRUNCATE](https://wade.pw/sql/truncate) - 테이블에서 데이터를 돌이킬 수 없는 제거합니다.

## 데이터 조작 언어
데이터 조작 언어(DML : Data Manipulation Language)는 데이터베이스 사용자 또는 응용 프로그램 소프트웨어가 컴퓨터 데이터베이스에 대해 데이터 검색, 등록, 삭제, 갱신을 위한, 데이터베이스 언어 또는 데이터베이스 언어 요소입니다.

- [SELECT](https://wade.pw/sql/select) - 데이터를 검색합니다.
- [INSERT](https://wade.pw/sql/insert) - 데이터를 삽입합니다.
- [UPDATE](https://wade.pw/sql/update) - 데이터를 업데이트합니다.
- [DELETE](https://wade.pw/sql/delete) - 데이터를 삭제합니다.

## 데이터 제어 언어
데이터 제어 언어(DCL : Data Control Language)는 데이터베이스에서 데이터에 대한 액세스를 제어하기 위한 데이터베이스 언어 또는 데이터베이스 언어 요소입니다.

- [GRANT](https://wade.pw/sql/grant) - 특정 데이터베이스 사용자에게 특정 작업을 수행 권한을 부여합니다.
- [REVOKE](https://wade.pw/sql/revoke) - 특정 데이터베이스 이용자에게 부여한 특정 권한을 박탈합니다.

## 웹사이트에서 사용하기
데이터베이스의 데이터를 표시하는 웹 사이트를 구축하려면 다음이 필요합니다.
- RDBMS 데이터베이스 프로그램
- [PHP](https://wade.pw/php/introduction) 또는 ASP와 같은 서버 츨 스크립팅 언어

## RDBMS
RDBMS는 관계형 데이터베이스 관리 시스템의 약자입니다. RDBMS는 SQL과 MS SQL Server, Oracle, MySQL 및 Microsoft Access와 같은 모든 최신 데이터베이스 시스템의 기반입니다. RDBMS의 데이터는 테이블이라는 데이터베이스 개체에 저장됩니다. 테이블은 관련 데이터 항목의 모음이며 열과 행으로 구성됩니다.

## 구문 예시
member 테이블이 있고 그 안에는 CodePin이라는 사용자가 있다고 과정해봅시다.
만약 CodePin이라는 사용자의 데이터를 추출하려면 다음과 같이 사용할 수 있습니다.

```sql
SELECT * FROM member WHERE name = "CodePin";
```

다음 구문은 테이블 이름이 `member` 이며 이름이 CodePin인 사람의 데이터를 추출하는 구문입니다.

## 명심하세요
SQL 키워드는 대소문자를 구분하지 않습니다. 따라서 SELECT 로 쓰든 select로 쓰든 둘다 명령문을 실행할 수 있습니다. (단, 테이블, 행, 열에 들어가는 값은 대소문자를 구분합니다.)
일부 데이터베이스 시스템에서는 각 SQL 문의 끝에 세미콜론이 필요합니다. 세미콜론은 서버에 대한 동일한 호출에서 둘 이상의 SQL 문을 실행할 수 있도록 하는 데이터베이스 시스템에서 각 SQL 문을 구분하는 표준 방법입니다.
