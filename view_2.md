# 뷰

### 뷰의 정의
- 뷰를 정의하는 SQL문의 구문
    CREATE VIEW 뷰이름 [(애트리뷰트(들))]
    AS SELECT문
    [WITH CHECK OPTION];
- 뷰의 이름 다음에 애트리뷰트들을 생략하면 뷰를 정의하는데 사용된
SELECT문의 SELECT절에 열거된 애트리뷰트들의 이름과 동일한 애트
리뷰트들이 뷰에 포함됨
- 뷰를 정의하는 SELECT절에 산술식 또는 집단 함수에 사용된 애트리
뷰트가 있는 경우, 뷰의 정의에 조인이 포함되어 있고 두 개 이상의
다른 릴레이션으로부터 가져온 애트리뷰트들의 이름이 같아서 뷰에
서 두 개 이상의 애트리뷰트의 이름이 같게 되는 경우에는 뷰를 정
의할 때 모든 애트리뷰트들의 이름을 지정해야 함
- 예) EMPLOYEE 릴레이션에 대해서 "3번 부서에근무하는 사원들의 사원번호, 사원이름, 직책으로 이루어진 뷰"를 정의해보자. 아래의 뷰의 정의에는 뷰의 애트리뷰트들을 별도로 명시했기 때문에 뷰에는 EMPNO, EMPNAME, TITLE의 세 애트리뷰트가 포함됨
    CREATE VIEW EMP_DNO3 (ENO, ENAME, TITLE)
    AS SELECT EMPNO, EMPNAME, TITLE
        FROM EMPLOYEE
        WHERE DNO = 3;
- 예) EMPLOYEE와 DEPARTMENT 릴레이션에 대해서 "기획부에 근무하는 사원들의 이름, 직책, 급여로 이루어진 뷰" 정의해보자. 아래의 뷰의 정의에는 뷰의 애트리뷰트들을 별도로 명시하지 않았기 때문에 뷰에 속하는 애트리뷰트들의 이름은 기본 릴레이션의 애트리뷰트들의 이름과 같다. 즉 뷰에는 EMPNAME, TITLE, SALARY의 세 애트리뷰트가 포함된다.
    CREATE VIEW EMP_PLANNING
    AS SELECT   E.EMPNAME, E.TITLE, E.SALARY
        FROM    EMPLOYEE E, DEPARTMENT D
        WHERE   E.DNO = D.DEPTNO AND D.DEPTNAME = '기획';
