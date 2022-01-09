# 자바스크립트 - 함수

함수의 메소드 중에서 중요한 것은 call, apply, bind 입니다.

먼저 call과 apply를 알아보겠습니다.

call 과 apply는 크게 차이점이 없습니다.

예시로 살펴보겠습니다.
```javascript
var example = function (a, b) {
  return a + b;
};
example(0, 1);
example.call(null, 0, 1);
example.apply(null, [0, 1]);
```
call과 apply 각각 인자가 서로 다른 것을 알 수 있습니다.

call은 일반적인 함수와 비슷하게 인자를 받고 apply는 배열로 인자를 받는것을 알 수 있습니다.

<br/>

**공통으로 들어가는 null은 무엇일까요?**

null 자리에 다른 객체를 넣는다면 해당 함수의 this를 바꿀 수 있습니다.

다른 예시로 알아보겠습니다.
```javascript
const obj1 = {
    data:"obj1Data",
    func:function(){
        console.log(this.data);
    }
}
const obj2 = {
    data:"obj2Data",
}
obj1.func();
obj1.func.call(obj2);

// obj1Data
// obj2Data
```
obj1.func.call(obj2) 결과로 obj2Data가 나오는 것을 알 수 있습니다.



