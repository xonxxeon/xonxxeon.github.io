---
title: "[프로그래머스] 2016년 풀이"
excerpt: "본문의 주요 내용을 여기에 입력하세요"

categories:
  - programmers
tags:
  - [tag1, tag2]

permalink: /programmers/2016년

toc: true
toc_sticky: true

date: 2023-12-05
last_modified_at: 2023-12-05
---

## 🦥 본문

https://programmers.co.kr/learn/courses/30/lessons/12901

# 2016년

### **문제 설명**

2016년 1월 1일은 금요일입니다. 2016년 a월 b일은 무슨 요일일까요? 두 수 a ,b를 입력받아 2016년 a월 b일이 무슨 요일인지 리턴하는 함수, solution을 완성하세요. 요일의 이름은 일요일부터 토요일까지 각각 `SUN,MON,TUE,WED,THU,FRI,SAT`입니다. 

예를 들어 a=5, b=24라면 5월 24일은 화요일이므로 문자열 "TUE"를 반환하세요.

### 제한 조건

- 2016년은 윤년입니다.
- 2016년 a월 b일은 실제로 있는 날입니다. (13월 26일이나 2월 45일같은 날짜는 주어지지 않습니다)

### **입출력 예**

month = 5, day = 24   / 결과값 = "TUE"

```java
class Solution {
    public String solution(int month, int day) {
        String answer = "";
        String[] week = {"FRI", "SAT", "SUN", "MON", "TUE", "WED", "THU"};
        int[] dayOfMonth = {31, 29, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
        
        month = month - 1;
        int result = 0;
        for(int i = 0; i < month; i++){
            result += dayOfMonth[i];
        }
        result = (result + day) % 7 - 1;
        if(result < 0)  result = 6;
        
        answer = week[result];
        
        return answer;
    }
}
```

<aside>
💡 result 값이 -1이 되면 6으로 재설정

</aside>
