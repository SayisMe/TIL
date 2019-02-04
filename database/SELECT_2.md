# SELECT문

### 기본적인 SQL 질의
- SELECT절과 FROM절만 필수적인 절이고, 나머지는 선택 사항

    SELECT      [DISTINCT] 애트리뷰트(들)
    FROM        릴레이션(들)
    [WHERE      조건
                    [중첩 질의]]
    [GROUP BY   애트리뷰트(들)]
    [HAVING     조건]
    [ORDER BY   애트리뷰트(들)[ASC|DESC]];

### 릴레이션의 모든 애트리뷰트나 일부 애트리뷰트들을 검색
- 예) 전체 부서의 모든 애트리뷰트들을 검색하라.
        - *를 사용하여 모든 애트리뷰트들을 검색
        SELECT      *
        FROM        DEPARTMENT;
- 예) 모든 부서의 부서번호와 부서이름을 검색하라.
        - 원하는 애트리뷰트들의 이름을 열거
        SELECT      DEPTNO, DEPTNAME
        FROM        DEPARTMENT;
        
