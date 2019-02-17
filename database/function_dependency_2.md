# 데이터 종속성과 정규화

### 함수 종속 다이어그램
![diagram](https://user-images.githubusercontent.com/46295659/52912028-19076b80-32ef-11e9-80ec-19a36caade36.JPG)

- 다이어그램이 표현하는 것과 같이 수강 릴레이션은 다음과 같
은 두 개의 함수 종속을 가지고 있다.
    - {학번, 과목번호} → 성적
    - 학번 → 학년

- 완전 함수 종속(full functional dependency)
    - 릴레이션 R의 어떤 애트리뷰트 Y가 다른 복합 애트리뷰트 X에 함수 종속이면서 X의 진부분 집합에는 함수 종속이 아닐때 Y는 X에 완전 함수 종속
    - 완전 함수 종속의 문제는 복합 애트리뷰트에서만 발생
    - 애트리뷰트 성적은 복합 애트리뷰트 { 학번, 과목번호 }에 완전 함수 종속
- 부분 함수 종속(partial functional dependency)
    - 애트리뷰트 학년은 애트리뷰트 학번에 완전 함수 종속이지만 복합 애트리뷰트 {학번, 과목번호}에는 완전 함수 종속이 아니라 부분 함수 종속
- 함수 종속에 대한 추론 규칙 (inference rule)
    - R1: (반사, reflexive) A ⊇ B이면 A → B이다.
    - R2: (첨가, augmentation) A → B이면 AC → BC이고 AC → B이다.
    - R3: (이행, transitive) A → B이고 B → C이면 A → C이다.
    - R4: (분해, decomposition) A → BC이면 A → B이다.
    - R5: (결합, union) A → B이고 A → C이면 A → BC이다.
