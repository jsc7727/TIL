# 자바스크립트에서의 함수

##



## 메소드로 사용되는 화살표 함수
화살표 함수는 일반 함수와 다르게 메소드 형태로 사용 시 this가 window를 가리킵니다.
```javascript
'use strict';

var obj = { // does not create a new scope
  i: 10,
  b: () => console.log(this.i, this),
  c: function() {
    console.log( this.i, this)
  }
}
obj.b(); // prints undefined, Window {...} (or the global object)
obj.c(); // prints 10, Object {...}
```