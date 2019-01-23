# SELECT 문

### 그룹화
- GROUP BY절에 사용된 애트리뷰트에 동일한 값을 갖는 투플들이 각각 하나의 그룹으로 묶임
- 이 애트리뷰트를 그룹화 애트리뷰트(grouping attribute)라고 함
- 각 그룹에 대하여 결과 릴레이션에 하나의 투플이 생성됨
- SELECT절에는 각 그룹마다 하나의 값을 갖는 애트리뷰트, 집단 함수, 그룹화에 사용된 애트리뷰트들만 나타날 수 있음
- 다음 질의는 그룹화를 하지 않은 채 EMPLOYEE 릴레이션의 모든 투플에 대해서 사원번호와 모든 사원들의 평균 급여를 검색하므로 잘못됨
    SELECT      EMPNO, AVG(SALARY)
    FROM        EMPLOYEE;
- 예) 모든 사원들에 대해서 사원들이 속한 부서번호별로 그룹화하고, 각 부서마다 부서번호, 평균 급여, 최대 급여를 검색하라.
    SELECT      DNO, AVG(SALARY) AS AVGSAL, MAX(SALARY) AS MAXSAL
    FROM        EMPLOYEE
    GROUP BY    DNO;

### HAVING절
- 어떤 조건을 만족하는 그룹들에 대해서만 집단 함수를 적용할 수 있음
- 각 그룹마다 하나의 값을 갖는 애트리뷰트를 사용하여 각 그룹이 만족해야 하는 조건을 명시함
- 그룹화 애트리뷰트에 같은 값을 갖는 투플들의 그룹에 대한 조건을 나타내고, 이 조건을 만족하는 그룹들만 질의 결과에 나타남
- HAVING절에 나타나는 애트리뷰트는 반드시 GROUP BY절에 나타나거나 집단 함수에 포함되어야 함
- 예) 모든 사원들에 대해서 사원들이 속한 부서번호별로 그룹화하고, 평균 급여가 2500000원 이상인 부서에 대해서 부서번호, 평균 급여, 최대 급여를 검색하라.
    SELECT      DNO, AVG(SALARY) AS AVGSAL, MAX(SALARY) AS MAXSAL
    FROM        EMPLOYEE
    GROUP BY    DNO
    HAVING      AVG(SALARY) >= 2500000;6