# 트리거

### 트리거
- 예) 새로운 사원이 입사할 때마다, 사원의 급여가 1500000 미만인 경우에는 급여를 10% 인상하는 트리거를 작성하라. 여기서 이벤트는 새로운 사원 투플이 삽입될 때, 조건은 급여<1500000, 동작은 급여를 10% 인상하는 것이다.
    CREATE TRIGGER RAISE_SALARY
    BEFORE INSERT ON EMPLOYEE
    FOR EACH ROW BEGIN
        IF (NEW.SALARY < 150000)
        THEN
        SET NEW.SALARY = NEW.SALARY * 1.1;
        END IF;
    END

- 예)
CREATE TRIGGER tri_employee_after_insert_high_salary
AFTER INSERT
ON mysql_study.employee
FOR EACH ROW
BEGIN
 INSERT INTO HIGH_SALARY(ename,sal,title) VALUES(NEW.empname, NEW.salary, NEW.title);
END;
SELECT * FROM EMPLOYEE;
SELECT * FROM HIGH_SALARY;
INSERT INTO EMPLOYEE VALUES(4000, '김태희', '사원', 3011, 1400000, 2);

- 예)
CREATE TRIGGER TRI_EMPLOYEE_AFTER_DELETE_HIGH_SALARY
 AFTER DELETE
 ON MYSQL_STUDY.EMPLOYEE
 FOR EACH ROW
BEGIN
 DELETE FROM HIGH_SALARY
 WHERE ENAME = OLD.EMPNAME;
END;
DELETE FROM EMPLOYEE WHERE EMPNAME='김태희';