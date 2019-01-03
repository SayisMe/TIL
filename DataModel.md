# 데이터베이스

### 데이터 모델
- 컴퓨터에 데이터를 저장하는 방식을 정의해 놓은 개념 모형
1. 계층형
   - 트리 구조를 활용하여 부모 자식 관계 정의하고, 데이터 관리
   - 일대다 관계, 자식 개체가 여러 부모 개체 가질 수 X
   ![datamodel_1](https://user-images.githubusercontent.com/46295659/50637293-beaf8700-0f9c-11e9-9947-2ae8d4221847.jpg)

2. 네트워크형
   - 망형(그물형)데이터 모델이라고도 한다.
   - 그래프 구조를 활용하여 자식 개체가 여러 부모 개체 가질 수 O
   ![datamodel_2](https://user-images.githubusercontent.com/46295659/50637347-046c4f80-0f9d-11e9-98bb-09d81f18b7c4.jpg)

3. 객체 지향형
   - 객체지향 프로그래밍에서 사용하는 객체 개념을 기반으로 한 모델
   - 상속, 오버라이드 등 기능 활용 가능
   ![datamodel_3](https://user-images.githubusercontent.com/46295659/50637498-95432b00-0f9d-11e9-954d-bd9f24ddc93d.jpg)

4. 관계형
   - 현대에 가장 많이 사용하는 모델
   - 다른 모델과 달리 데이터 간 관계에 초점을 둔다. 중복이 발생 할 수 있는 데이터는 별개의 관계로 정의한 후 식별 가능한 '코드'를 이용해 데이터들을 연결한다.
   ![datamodel_4](https://user-images.githubusercontent.com/46295659/50637562-d63b3f80-0f9d-11e9-9599-7948481c8e35.jpg)
   ![datamodel_4_2](https://user-images.githubusercontent.com/46295659/50637593-f2d77780-0f9d-11e9-8d6d-a5582c0e4b50.jpg)
