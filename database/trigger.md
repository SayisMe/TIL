# 트리거

### 트리거
- 명시된 이벤트(데이터베이스의 갱신)가 발생할 때마다 DBMS가 자동적으로 수행
하는, 사용자가 정의하는 문(프로시저)
- 데이터베이스의 무결성을 유지하기 위한 일반적이고 강력한 도구
- 테이블 정의 시 표현할 수 없는 기업의 비즈니스 규칙들을 시행하는 역할
- 트리거를 명시하려면 트리거를 활성화시키는 사건인 이벤트, 트리거가 활성화되
었을 때 수행되는 테스트인 조건, 트리거가 활성화되고 조건이 참일 때 수행되
는 문(프로시저)인 동작을 표현해야 함
- 트리거를 이벤트-조건-동작(ECA) 규칙이라고도 부름
- E는 Event, C는 Condition, A는 Action을 의미
- SQL3 표준에 포함되었으며 대부분의 상용 관계 DBMS에서 제공됨
![trigger](https://user-images.githubusercontent.com/46295659/52326593-93510980-2a2c-11e9-9979-d39f026533fb.JPG)

1. 트리거의 형식
    CREATE TRIGGER <트리거이름>
    trigger_time trigger_event
    ON table_name
    FOR EACH ROW <SQL문(들)>
2. Trigger_time 트리거 동작 시간
- BEFORE
- AFTER
3. trigger_event
- INSERT
- UPDATE
- DELETE

- 동일한 트리거 동작 시간 및 이벤트를 갖는 테이블에 대해서는 두 개의 트리거를 가질 수 없다.
- 어떤 이벤트가 발생했을 때 조건이 참이 되면 트리거와 연관된 동작이 수행되고, 그렇지 않으면 아무 동작도 수행되지 않음