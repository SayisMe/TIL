# SELECT 문

### SELECT절에서 산술 연산자 사용
- 예) 직급이 과장인 사원들에 대하여 이름과, 현재의 급여, 급여가 10% 인상됐을 때의 값을 검색하라.
    - 산술 연산자
        SELECT      EMPNAME, SALARY, SALARY * 1.1 AS NEWSALARY
        FROM        EMPLOYEE
        WHERE       TITLE = '과장';

### 널값
- 널값을 포함한 다른 값과 연산을 하면 결과는 널
- COUNT(*)를 제외한 집단 함수들은 널값을 무시함
- 어떤 애트리뷰트에 들어 있는 값이 널인가 비교하기 위해서 'DNO = NULL'처럼  나타내면 안됨
    SELECT      EMPNO, EMPNAME
    FROM        EMPLOYEE
    WHERE       DNO = NULL; (X)
  ->WHERE       DNO IS NULL;
- 다음과 같은 비교 결과는 모두 거짓
    NULL > 300
    NULL = 300
    NULL <> 300
    NULL = NULL
    NULL <> NULL
    