## 클로저(Closure)란

- 함수와 함수가 선언된 렉시컬 스코프(lexical scope)에 대한 참조가 저장된 객체다.
- 이 객체를 통해 함수가 선언된 렉시컬 스코프 외부에서도 해당 스코프 내에 선언된 변수에 접근할 수 있다.
- 즉, 클로저는 자신이 생성될 때의 환경(Lexical environment)을 기억하는 함수

```
function outerFunction() {
  let outerVariable = 1;
  function innerFunction() {
    console.log(outerVariable);
  }
  return innerFunction;
}

let closureFunction = outerFunction();
closureFunction(); // 1
```

> 위 코드에서 outerFunction 함수는 innerFunction 함수를 반환하고 있습니다. 이때 innerFunction 함수가 outerVariable 변수에 접근할 수 있는 이유는, innerFunction 함수가 클로저를 형성하여 outerFunction 함수의 렉시컬 스코프에 대한 참조를 유지하기 때문입니다.

## 렉시컬 스코프란(Lexical Scope)란

- 함수를 어디서 호출하는지가 아니라 어디에 선언하였는지에 따라 결정되는 것을 말한다.
- 즉, 함수의 선언에 따라 결정된다는 점이다.

```
var x = 1; // global

function first() {
  var x = 10;
  second();
}

function second() {
  console.log(x);
}

first(); // 1
second(); // 1
```