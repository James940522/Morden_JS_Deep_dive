# 제어문
> 제어문(control flow statement)은 조건에 따라 `코드 블록`을 실행(조건문)하거나 반복 실행(반복문)할 때 사용한다.
- 제어문은 코드의 실행 흐름을 인위적으로 제어할 수 있다. -> 순차적으로 진행하는 직관적인 코드의 흐름을 혼란스럽게 만든다.
- 즉, 제어문은 코드의 흐름을 이해하기 어럽게 만들어 `가독성을 해치는 단점`이 있다. -> 가독성이 좋지 않은 코드는 `오류를 발생시키는 원인`

```js
forEach()
map()
filter()
reduce()
```
같은 고차 함루를 이용한 함수형 프로그래밍 기법에서는 제어문의 사용을 억제하여 복잡성을 해결하려고 노력한다.

## 블록문
> 블록문(block statement/compound statemnet)은 0개 이상의 문을 중괄호로 묶은 것으로 코드 블록 또는 블록이라고 부른다.

```js
// 블록문
{
  var foo =10;
}

// 제어문
var x = 1;
if (x < 10) {
  x++;
}

// 함수 선언문
function sum(a, b) {
  return a + b;
}
```

## 조건문
> 조건문(conditional statement)은 주어진 조건식(conditional expression)의 평가 결과에 따라 코드 블록(블록문)의 실행을 결정한다.
자바스크립트는 if ... else 문과 switch 문으로 두 가지 조건문을 제공한다.

- 조건식의 평가가 true일 경우 if 문의 코드 블록이 실행되고, false일 경우 else 문의 코드 블록이 실행된다.

```js
if (조건식) {
  // 조건식이 참이면 이 코드 블록이 실행된다.
} else if (조건식) {
  // 첫 조건식이 거짓이고, 해당 조건식이 참이면 이 코드 블록이 실행된다.
} else {
  // 모든 조건식이 거짓이면 이 코드 블록이 실행된다.
}
```
if 문의 조건식은 불리언 값으로 평가되어야 한다.<br>
만약 if 문의 조건식이 불리언 값이 아닌 값으로 평가되면 자바스크립트 엔진에 의해 암묵적으로 불리언 값으로 강제 변환된다.
<br>
- 대부분의 if ... else문은 삼항 조건 연산자로 바꿀 수 있다.
```js
var x = 2;

var result = x % 2 ? '홀수' : '짝수'
```

## switch 문
> `swtich` 문 은 주어진 표현식을 평가하여 그 값과 일치하는 표현식을 갖는 case 문 으로 실행 흐름을 옮긴다.

```js
swtich (표현식) {
	case 표현식1:
		실행문1;
		break;
	case 표현식2:
		실행문2;
		break;
	...
	default:
		default시 실행문;
}
```

- 만약 `if - else` 문으로 해결할 수 있다면 → `switch` 문보다 `if - else` 문을 사용하는 편이 좋다.
조건식이 너무 많아서 `if - else` 문보다 `switch` 문을 사용했을 때 가독성이 더 좋다면 → `switch` 문을 사용하는 편이 좋다.

## 반복문
> 반복문(loop statement)은 조건식의 평가 결과가 참인 경우 코드 블록을 실행한다.<br>
> 그 후 조건식을 다시 평가하여 여전히 참인 경우 코드 블록을 다시 실행한다.<br>
> 이는 조건식이 거짓일 때까지 반복된다.

```
// 💡 반목문을 대체할 수 있는 다양한 Javascript 기능이 있다. ( 일단은 인지정도만 할 것 )

자바스크립트는 "배열 순회 시" 사용하는 = forEach() 메서드
"객체의 프로퍼티를 열거 시" 사용하는 = for - in 문
"ES6에서 도입된 이터러블을 순회 시" 사용하는 = for - of 문
```

- while 문 = 반복 횟수가 "불명확"할 때 주로 사용
- for 문 = 반복 횟수가 "명확"할 때 주로 사용

``` js
// 💡 for 문 무한루프
// 초기식 | 조건식 | 증감식 을 아무것도 작성하지 않을 경우 -> while(true) 와 같다.

for( ; ; ) { ... }
```

## break 문
> `break` 문은 코드 블록 을 탈출하는 것

```js
/*
💡 레이블 문(label statement) = "식별자"가 붙은 문을 말한다.

+ 레이블 문은 프로그램 실행 순서를 제어하는 데 사용
+ switch 문의 case 문과 default 문도 사실 "레이블 문"
+ 레이블 문을 탈출 시 -> break 문에 식별자를 지정 필요

*/

// 1️⃣ foo 라는 레이블 식별자가 붙은 문
foo: console.log("foo");

// 2️⃣ foo라는 식별자가 붙은 레이블 블록문
foo: {
  console.log(1);
  break foo; //  foo 레이블 블록문을 탈출한다.
  console.log(2);
}
```
- 레이블 문은 중첩된 for 문 외부로 탈출 할 때 유용하지만 그 외에는 일반적으로 권장하지 않는다.
- 레이블 문 사용시 → 프로그램의 흐름이 복잡해져서 가독성이 나빠지고 오류를 발생시킬 가능성이 높아지기 때문 ( 존재 정도만 인지할 것 )

## continue 문
> `continue` 문 은 반복문의 코드 블록 실행을 `현 시점에서 중단하고` , `반복문의 증감식으로 실행 흐름을 이동시킨다.` ( break 문처럼 반복문을 탈출하지는 않는다. )

```js
// if문 내에서 여러 코드 작성해야 할 경우 -> continue 문을 사용하지 않았을 경우
var arr = [1, 2, 3, 4, 5];
var target = 3;
var count = 0;

for (var i = 0; i < arr.length; i++) {
  // arr[i] 가 target 이하라면 count 증감
  if (arr[i] <= target) {
    count++;
    // code...
    // code...
    // code...
  }
}

// if문 내에서 여러 코드 작성해야 할 경우 -> continue 문을 사용한 경우 -> depth가 하나 줄어들었다.
var arr = [1, 2, 3, 4, 5];
var target = 3;
var count = 0;

for (var i = 0; i < arr.length; i++) {
  // arr[i] 가 target 초과이면 count 증감하지 않는다.
  if (arr[i] > target) continue;

  count++;
  // code...
  // code...
  // code...
}
```
