# Insert, Delete, Update

### Insert
- 기존의 릴레이션에 투플을 삽입
- 참조되는 릴레이션에 투플이 삽입되는 경우에는 참조 무결성 제약조건의 위배되지 않으나
  참조하는 릴레이션에 투플이 삽입되는 경우에는 참조 무결성 제약조건에 위배될 수 있음
- 릴레이션에 한 번에 한 투플씩 삽입하는 것과 한 번에 여러 개 투플들을 삽입할 수 있는 것으로 구분
- 릴레이션에 한 번에 한 투플씩 삽입하는 Insert문
    INSERT
    INTO    릴레이션(애트리뷰트1, ..., 애트리뷰트n)
    VALUES (값1, ..., 값n);
- 삽입 순서 중요
- 예시(DEPARTMENT 릴레이션에서 부서번호 5, 부서명이 '연구'인 투플을 삽입하는 INSERT 문?)
    INSERT INTO DEPARTMENT(DEPTNO, DEPTNAME)
    VALUES(5, '연구');

### Delete
- 삭제 연산은 한 릴레이션으로부터 한 개 이상의 투플들을 삭제
- 참조되는 릴레이션의 삭제 연산의 결과로 참조 무결성 제약조건이 위배될 수 있으나
  참조하는 릴레이션에서 투플을 삭제하면 참조 무결성 제약조건을 위배하지 않음
- DELETE
  FROM    릴레이션
  WHERE   조건;
- 예시(DEPARTMENT 릴레이션에서 4번 부서를 삭제)
    DELETE FROM DEPARTMENT
    WHERE DEPTNO = 4;


### Update
- 한 릴레이션에 들어 있는 투플들의 애트리뷰트 값들을 수정
- 기본 키나 외래 키에 속하는 애트리뷰트 값이 수정되면 참조 무결성 제약조건을 위배할 수 있음
- UPDATE    릴레이션
  SET       애트리뷰트 = 값 또는 식[, ...]
  WHERE     조건;
- 예시(사원번호가 2106인 사원의 소속 부서를 3번 부서로 옮기고, 급여를 5% 올려라)
    UPDATE EMPLOYEE
    SET     DNO = 3, SALARY = SALARY * 1.05
    WHERE   EMPNO = 2106;