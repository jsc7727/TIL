# 커링 (Currying)

## 커링이란? 

커링은 함수화 함께 사용할 수 있는 기술입니다.

자바스크립트 뿐만 아니라 다른 언어에서도 사용되고 있습니다.

ex) [파이썬](https://www.geeksforgeeks.org/currying-function-in-python/)

<br/>

## 커링 함수 예제

예를들어 함수 큰 함수 안에 작은함수 여러개를 넣었다고 생각해보겠습니다. 

```javascript
// 일반적인 함수
const normal = (a,b,c)=> a*b*c;
console.log(normal(1,2,3));

// 커링을 사용한 함수
const currying = a => b => c => a*b*c;
console.log(currying(1)(2)(3));

// 결과 값
// 6
// 6
```

arrow function 을 통해 일반적인 함수와 currying 함수를 만들었습니다.

둘 함수의 결과값은 같지만 함수의 인자를 받는 부분의 차이가 있습니다.

<br />

## 커링 함수를 사용하는 이유는 무엇일까요?

함수가 여러개의 인자를 받을때 특정인자를 고정 할 수 있습니다.

그로인해 재사용성이 증가 할 수 있습니다.

예시로 설명하겠습니다 : )

```javascript
// 커링을 사용한 함수
const currying = a => b => c => a*b*c;
console.log(currying(1)(2)(3));

// 인자 값 고정으로 재사용성 높여보기
const alwaysMultiple2 = currying(1)(2);
console.log(alwaysMultiple2(3));

// 결과 값
// 6
// 6
```
<br/>

## 함수 인자가 많을때는 어떻게 해야할까요?

하나씩 붙여주는것 보다는 자동으로 고정할 수 있다면 편할 것입니다.

이것도 예시로 설명하겠습니다.

```javascript
const curry = (func) => {
  return curried = (...args) => {
    if (args.length >= func.length) {
      return func.apply(null, args);
    } else {
      return (...args2) => {
        return curried.apply(null, args.concat(args2));
      }
    }
  };
}

const mul = (a, b, c) => {
  return a*b*c;
}

const curriedSum = curry(mul);

console.log(curriedSum(1, 2, 3) ); // 6, 보통때 처럼 단일 callable 형식으로 호출하기
console.log(curriedSum(1)(2,3) ); // 6, 첫 번째 인수를 커링하기
console.log(curriedSum(1)(2)(3) ); // 6, 모두 커링하기
```

코드를 볼때 필요한 지식

 [Function.prototype.apply() - JavaScript | MDN developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply)

 [Arrow function expressions - JavaScript | MDN developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions)