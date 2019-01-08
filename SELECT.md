# 데이터를 조회하는 3가지 방법
1. 셀렉션 : 행 단위로 조회
2. 프로젝션 : 열 단위로 조회
3. 조인 : 두 개 이상의 테이블로 조회

# SQL의 기본 뼈대, SELECT절과 FROM절
- SELECT문 : 데이터 조회하는 데 사용 (SELECT절+FROM절)
- FROM 절 : 조회할 데이터가 저장된 테이블 이름
- SELECT 절 : FROM절에 명시한 테이블에서 조회할 열이나 여러 열에 저장된 데이터의 조합 또는 연산식 지정
ex) SELECT [조회할 열1 이름], [열2 이름], ..., [열N 이름]
    FROM   [조회할 테이블 이름];

1. SELECT *FROM EMP;        -> EMP 테이블 전체 열 조회하기
![select](https://user-images.githubusercontent.com/46295659/50833005-44637600-1393-11e9-9acd-3599f1e71987.JPG)

2. SELECT EMPNOM ENAME, DEPTNO
        FROM EMP;
![from](https://user-images.githubusercontent.com/46295659/50833136-a8863a00-1393-11e9-8ebb-1caa7d6fd8c4.JPG)
