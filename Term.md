# 기본적인 용어와 사용

### 기본적인 용어
- 릴레이션 : 2차원의 테이블
- 레코드 : 릴레이션의 각 행
- 투플 : 레코드를 좀 더 공식적으로 부르는 용어
- 애트리뷰트 : 릴레이션에서 이름을 가진 하나의 열
![term](https://user-images.githubusercontent.com/46295659/51072605-ef7f7280-16a6-11e9-9781-0f226362f591.JPG)


## 응용

### 테이블 생성 예시

CREATE TABLE department (
    deptno int(11) NOT NULL auto_increment,
    deptname char(10),
    floor int(11) DEFAULT 0,
    PRIMARY KEY (deptno)
);

CREATE TABLE employee(
    empno int(11) NOT NULL,
    empname varchar(20) unique,
    title varchar(10) DEFAULT '사원',
    manager int(11),
    salary int(11),
    dno int(11) DEFAULT 1,
    PRIMARY KEY (empno),
    FOREIGN KEY (manager) REFERENCES employee(empno),
    FOREIGN KEY (dno) REFERENCES department(deptno)
    ON DELETE NO ACTION
    ON UPDATE CASCADE
);