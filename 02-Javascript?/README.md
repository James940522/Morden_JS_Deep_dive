# ECMAScript 버전별 특징
>💡 ES5 → ES6로 업데이트하면서 많은 변화가 발생 ( 중점적으로 확인할 것 )

| 버전 | 특징 | 출시 연도 |
|-----|------|---|
|ES1	|...	|1997|
|ES2|	...	|1998|
|ES3|	정규 표현식, try - catch	|1999|
|ES5|	HTML5와 함께 출현한 표준안, JSON, strict mode, 접근자 프로퍼티 ,프로퍼티 어트리뷰트 제어 ,향상된 배열 조작 기능(forEach, map, filter, reduce, some, every)|	2009|
|ES6(ECMAScript 2015)|	let/const, 클래스, 화살표 함수, 템플릿 리터럴, 디스트럭처링 할당, 스프레드 문법, rest 파라미터, 심벌, 프로미스, Map/Set, 이터러블 , for - of, 제너레이터, Proxy, 모듈 import/export	|2015|
|ES7(ECMAScript 2016)|	지수(**)연산자, Array.prototype.includes, String.prototype.includes	|2016|
|ES8(ECMAScript 2017)|	async/await, Object 정적 메서드 (Object.values, Object.entriesm Object.getOwnPropertyDescriptors)	|2017|
|ES9(ECMAScript 2018)|	...	|2018|
|ES10(ECMAScript 2019)|	...	|2019|
|ES11(ECMAScript 2020)|	...	|2020|

# 자바스크립트 발전과정
```
초기 자바스크립트

= 웹페이지의 보조적인 기능을 수행하기 위해 한정적인 용도로만 사용
```
- 대부분 로직은 웹 서버에서 실행
- 브라우저는 단지, 서버로부터 전달받은 HTML & CSS를 단순히 렌더링하는 수준이었다.
```
Ajax(Asynchronous Javascript and XML)

= 자바스크립트를 이용해 서버와 브라우저가 비동기(Asychronous) 방식으로 데이터를 교환할 수 있는 통신 기능
```
- `XMLHttpRequest` 라는 이름으로 등장
- Ajax 이전까지의 웹페이지는 HTML태그로 시작해서 HTML 태그로 끝나는 완전한 HTML 코드를 서버로부터 전송받아 웹페이지를 렌더링하는 방식으로 동작
  - 화면이 전환 → 서버로부터 새로운 HTML을 전송받아 웹페이지 전체를 리렌더링
  - 변경할 필요 없는 부분까지 리렌더링 → 불필요한 데이터 통신 발생 → 성능 면에서도 불리 → 화면이 순간적으로 깜빡이는 현상이 발생
- Ajax 등장 이후
  - 변경할 필요가 없는 부분은 다시 리렌더링 하지 않고, 서버로부터 필요한 데이터만 전송받아 변경해야 하는 부분만 한정적으로 렌더링하는 방식이 가능해졌다.
  - 이로써, 웹 브라우저에서도 데스크톱 애플리케이션과 유사한 빠른 성능과 부드러운 화면 전환이 가능해졌다.

```
JQuery

= DOM(Document Object Model)을 더욱 쉽게 제어할 수 있고, 크로스 브라우징 이슈도 어느 정도 해결해준 자바스크립트 라이브러리
```
```
V8 자바스크립트 엔진

= 자바스크립트가 데스크톱 애플리케이션과 유사한 사용자 경험(UX)을 제공할 수 있는 웹 애플리케이션 프로그래밍 언어로 정착되었음
```

- V8 자바스크립트 엔진으로 촉발된 자바스크립트의 발전
  - 과거 웹 서버에서 수행되던 로직들이 → 대거 클라이언트(브라우저)로 이동 → 웹 애플리케이션 개발에서 프론트엔드 영역이 주목받는 계기로 작용
