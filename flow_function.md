# INSERT, DELETE, UPDATE 문

### 제어 플로우 함수
- 수식 1
    CASE value
        WHEN [compare_value] THEN result
        [WHEN [compare_value] THEN result...]
        [ELSE result]
    END
- value=compare_value 인 경우에 result를 리턴

- 수식 2
    CASE
        WHEN [condition] THEN result
        [WHEN [condition] THEN result...]
        [ELSE result]
    END
- 두 번째 수식은 처음의 조건이 트루일 경우에 값을 리턴. 만일 매칭되는 결과 값이 없는 경우에는 ELSE 다음의 값이 리턴이 되거나, 또는 ELSE 부분이 없는 경우에는 NULL 을 리턴

- SELECT empname, title,
    CASE 
        WHEN salary >= 4000000 THEN '3시 퇴근'
        WHEN salary >= 3000000 THEN '5시 퇴근'
        WHEN salary >= 2000000 THEN '7시 퇴근'
        ELSE '야근'
    END as '퇴근시간'
  FROM employee;
  ![flow](https://user-images.githubusercontent.com/46295659/51325644-bd0fb400-1ab0-11e9-9b14-ba0398e67f6b.JPG)
