# SELECT 문

### 자체 조인
- 한 릴레이션에 속하는 투플을 동일한 릴레이션에 속하는 투플들과 조인하는 것
- 실제로는 한 릴레이션이 접근되지만 FROM절에 두 릴레이션이 참조되는 것처럼 나타내기 위해서 그 릴레이션에 대한 별칭을 두 개 지정해야 함
- 예) 모든 사원에 대해서 사원의 이름과 직속 상사의 이름을 검색하라
    - 자체 조인
        SELF E.EMPNAME AS 사원, M.EMPNAME AS 직속상사
        FROM EMPLOYEE E, EMPLOYEE M
        WHERE E.MANAGER = M.EMPNO;
- 예) 모든 사원에 대해서 소속 부서이름, 사원의 이름, 직급, 급여를 검색하라. 부서 이름에 대해서 오름차순, 부서이름이 같을 경우에는 SALARY에 대해서 내림차순으로 정렬하라.
    - 조인과 ORDER BY의 결합
        SELECT DEPTNAME, EMPNAME, TITLE, SALARY
        FROM EMPLOYEE E, DEPARTMENT D
        WHERE E.DNO = D.DEPTNO
        ORDER BY DEPTNAME, SALARY DESC;

### 중첩 질의
- 외부 질의의 WHERE절에 다시 SELECT ... FROM ... WHERE 형태로 포함된 SELECT문
- 부질의라고 함
- INSERT, DELETE, UPDATE문에도 사용될 수 있음
- 중첩 질의의 결과로 한 개의 스칼라값(단일 값), 한 개의 애트리뷰트로 이루어진 릴레이션, 여러 애트리뷰트로 이루어진 릴레이션이 반환될 수 있음
- 예) 박영권과 같은 직급을 갖는 모든 사원들의 이름과 직급을 검색하라.
    - 한개의 스칼라 값이 반환되는 경우
        SELECT   EMPNAME, TITLE
        FROM     EMPLOYEE
        WHERE    TITLE =
                
                (SELECT     TITLE
                 FROM       EMPLOYEE
                 WHERE      EMPNAME = '박영권');
