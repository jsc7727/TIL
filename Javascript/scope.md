자바스크립트를 공부하다보면 **스코프(scope)** 라는 단어를 많이 볼 수 있습니다.

그렇다면 **스코프** 란 무엇일까요?



프로그래밍에서 스코프는 현재 실행중인 **컨텍스트** 를 의미합니다.

변수나 다른 표현식이 해당 스코프 안에 있지 않다면 사용할 수 없습니다. 

스코프는 계층적인 구조를 가지고 있기에 하위 스코프에서 상위 스코프에 접근이 가능하지만,

상위 스코프에서 하위 스코프로의 접근이 불가능합니다.

예시로 보겠습니다.

```code
