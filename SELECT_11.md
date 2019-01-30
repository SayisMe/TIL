# SELECT 문

### 여러 애트리뷰트들로 이루어진 릴레이션이 반환되는 경우
- 중첩 질의의 결과로 여러 애트리뷰트들로 이루어진 릴레이션이 반환
되는 경우에는 EXISTS 연산자를 사용하여 중첩 질의의 결과가 빈
릴레이션인지 여부를 검사함
- 중첩 질의의 결과가 빈 릴레이션이 아니면 참이 되고, 그렇지 않으
면 거짓
- 예) 영업부나 개발부에 근무하는 사원들의 이름을 검색하라
    - EXISTS를 사용한 질의
        SELECT      EMPNAME
        FROM        EMPLOYEE E
        WHERE       EXISTS
                    (SELECT     *
                     FROM       DEPARTMENT D
                     WHERE      E.DNO = D.DEPTNO
                                AND (DEPTNAME = '영업' OR DEPTNAME = '개발'));

### 상관 중첩 질의(correlated nested query)
- 중첩 질의의 WHERE절에 있는 프레디키트에서 외부 질의에 선언된 릴레
이션의 일부 애트리뷰트를 참조하는 질의
- 중첩 질의의 수행 결과가 단일 값이든, 하나 이상의 애트리뷰트로 이루
어진 릴레이션이든 외부 질의로 한 번만 결과를 반환하면 상관 중첩 질
의가 아님
- 상관 중첩 질의에서는 외부 질의를 만족하는 각 투플이 구해진 후에 중
첩 질의가 수행
- 상관 중첩 질의는 외부 질의를 만족하는 투플 수만큼 여러 번 수행될 수 있음
- 예) 자신이 속한 부서의 사원들의 평균 급여보다 많은 급여를 받는 사원들에 대해서 이름, 부서번호, 급여를 검색하라.
    - 상관 중첩 질의
        SELECT      EMPNAME, DNO, SALARY
        FROM        EMPLOYEE E
        WHERE       SALARY >
                    (SELECT     AVG(SALARY)
                     FROM       EMPLOYEE
                     WHERE      DNO = E.DNO);