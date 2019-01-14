# 데이터 정의어와 무결성 제약조건

### 참조 무결성 제약조건 유지
- ON DELETE reference_option
- ON UPDATE reference_option
- reference_option
    1. RESTRICT : 개체를 변경/삭제할 때 다른 개체가 이 개체를 참조하고 있을 경우 변경/삭제가 취소
    2. CASCADE : 개체를 변경/삭제할 때 다른 개체가 이 개체를 참조하고 있을 경우 함께 변경/삭제
    3. NO ACTION : 개체를 변경/삭제할 때 다른 개체가 이 개체를 참조하고 있을 경우 이 개체만 변경/삭제되고 참조하고 있는 개체는 변동이 없음.
    4. SET NULL : 개체를 변경/삭제할 때 다른 개체가 이 개체를 참조하고 있을 경우 참조하고 있는 값은 NULL로 세팅.

    CREATE TABLE employee (
        empno int(11) NOT NULL,
        empname varchar(20) unique,
        title varchar(10) DEFAULT '사원',
        manager int(11),
        salary int(11),
        dno int(11) DEFAULT 1,
        PRIMARY KEY (empno),
        FOREIGN KEY (manager) REFERENCES employee(empno),
        FOREIGN KEY (dno) REFERENCES department(deptno)
        ON DELETE CASCADE
    );
    - ON DELETE CASCADE 로 인해 자동적으로 함께 삭제된다.
    ![cascade](https://user-images.githubusercontent.com/46295659/51111409-546dd080-183f-11e9-8966-7f3dcb2c2535.JPG)
