# SELECT문

### 다수의 검색 조건
- 잘못된 예시)
    SELECT      FLOOR
    FROM        DEPARTMENT
    WHERE       DEPTNAME='영업' AND DEPTNAME='개발';

- 예) 직급이 과장이면서 1번 부서에서 근무하는 사원들의 이름가 급여를 검색하라.
    - 부물 연산자를 사용한 프레디키트
        SELECT      EMPNAME, SALARY
        FROM        EMPLOYEE
        WHERE       TITLE = '과장' AND DNO = 1;
- 예) 직급이 과장이면서 1번 부서에 속하지 않은 사원들의 이름과 급여를 검색하라.
    - 부정 연산자
        SELECT      EMPNAME, SALARY
        FROM        EMPLOYEE
        WHERE       TITLE = '과장' AND DNO <> 1;
### 범위를 사용한 검색
- 예) 급여가 3000000원 이상이고, 4500000원 이하인 사원들의 이름, 직급, 급여?
    - 범위 연산자
        SELECT EMPNAME, TITLE, SALARY
        FROM EMPLOYEE
        WHERE SALARY BETWEEN 3000000 AND 4500000;
        (==   SALARY >= 3000000 AND SALARY <= 4500000;)
### 리스트를 사용한 검색
- 예) 1번 부서나 3번 부서에 소속된 사원들에 관한 모든 정보를 검색하라
    - IN
        SELECT      *
        FROM        EMPLOYEE
        WHERE       DNO IN (1,3);
