# SELECT문

### 상이한 값들을 검색
- 예) 모든 사원들의 직급을 검색하라
    - DISTINCT절을 사용하지 않을 때
        SELECT      TITLE
        FROM        EMPLOYEE;
- 예) 모든 사원들의 상이한 직급을 검색하라
    - DISTINCT절을 사용할 때
        SELECT      DISTINCT TITLE
        FROM        EMPLOYEE;

### 특정한 투플들의 검색
- 예) 2번 부서에 근무하는 사원들에 관한 모든 정보를 검색하라
    - WHERE절을 사용하여 검색 조건을 명시
        SELECT      *
        FROM        EMPLOYEE
        WHERE       DNO = 2;
- 예) 이씨 성을 가진 사원들의 이름, 직급, 소속 부서번호를 검색하라
    - %를 사용하여 문자열 비교
        SELECT      EMPNAME, TITLE, DNO
        FROM        EMPLOYEE
        WHERE       EMPNAME LIKE '이%';    