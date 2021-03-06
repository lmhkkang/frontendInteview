## Javascript 기술 질문 
##### > 참조 https://github.com/baeharam/Must-Know-About-Frontend

### 1.  Ajax
>AJAX (Asynchronous Javascript And XML)   비동기식 자바스크립트와 xml
- 자바스크립트를 이용해 서버와 브라우져가 비동기 방식으로 데이터를 교환할 수 있는 통신 기능
- 브라우져가 가지고 있는 XMLHttpRequest 객체로 페이지 새로고침을 하지 않고 페이지의 일부만 데이터를 로드하는 기법.<br/>
![ajax비동기통신](https://user-images.githubusercontent.com/45140764/145498412-d00a25f7-2e10-4849-a282-910aef710832.png)

#### 비동기 통신이란??
[그림1]<br/>
![동기비동기](https://user-images.githubusercontent.com/45140764/145501197-2bed7a6e-610d-41ce-aafc-35d525411544.png)
<br/>
#### [그림1]과 같이 ABC의 업무 프로세스가 있다고 가정해보자.
<b>동기 방식</b>은 A B C 프로세스가 실행될 때 순차적으로 A의 프로세스가 끝나고 B 프로세스가 시작된다.<br/>
<b>비동기 방식</b>은 A B C 프로세스가 실행될 때 순차적으로 실행되나 B가 A의 프로세스를 기다리지 않고 시작된다. 

### 2. 이벤트 위임 (Event Delegation)
#### `이벤트 위임`을 알기 위해선 `이벤트 버블링`과 `이벤트 캡쳐링` 을 알아야 한다.
- **이벤트 버블링(Event Bubbling)**
> 이벤트 버블링은 특정 화면 요소에서 이벤트가 발생했을 때 해당 이벤트가 더 상위의 화면 요소들로 전달되어 가는 특성을 의미합니다.<br/>

 [그림1]<br/>
![event_bubbling](https://user-images.githubusercontent.com/45140764/145736547-50e426bd-69a0-499d-9627-36c407e68971.png)
<br/>
[그림1]과 같이 이벤트 버블링은 html 트리구조에서 하위 요소(element)에서 발생한 이벤트가 위 요소(element)로 이벤트를 전달하는 것을 의미한다.

- **이벤트 캡쳐링(Event Capturing)**
>이벤트 캡쳐는 이벤트 버블링과 반대 방향으로 진행되는 이벤트 전파 방식입니다.<br/>

[그림2]<br/>
![event_capturing](https://user-images.githubusercontent.com/45140764/145737558-4b82d600-064c-43fa-9ca9-ac304139c3f2.png)

[그림2]처럼 특정 이벤트가 발생했을 때 최상위 요소인 body 태그에서 해당 태그를 찾아 내려갑니다.<br/>
**[구현 문법]**
```js
div.addEventListener('click', logEvent, {
	capture: true // default 값은 false입니다.
});
```

- **이벤트 위임 (Evevnt Delegation)**
> 하위 요소에 각각 이벤트를 붙이지 않고 상위 요소에서 하위 요소의 이벤트들을 제어하는 방식<br/>

[그림3]<br/>
![event_delegation](https://user-images.githubusercontent.com/45140764/145750775-da119cc9-7982-4b25-9ce7-fa7d11db858c.png)
<br/>
[그림3]과 같이 html이 체크 박스가 두개 있는 트리구조 일때 input 태그에 `eventListner`를 추가하였다고
가정 해보자.<br/>
[코드1]
```js
var inputs = document.querySelectorAll('input');
inputs.forEach(function(input) {
	input.addEventListener('click', function(event) {
		alert('clicked');
	});
});
```

이후 동적으로 `<li><input type="checkbox"/> </li>`을  추가하였다고 가정해보자 (`append()`)<br/>
[그림4]<br/>
![event_delegation2](https://user-images.githubusercontent.com/45140764/145753652-0de32970-bbde-4f59-a817-3be1ffa3e8fc.png)

[그림4]와 같이 추가 되었을 때 [코드1]의 코드 만으로는 동적으로 새로 추가된 `체크박스`는 `eventListner`의 영향이 전혀 없다. 즉, 새로 추가된 `체크박스`를 클릭해도 `alert('clicked')` 코드가 동작하지 않는다.
<br/>
이때 등장하는 개념이 **이벤트 위임**이다.  
<br/>

[코드2]
```js
var ul= document.querySelector('ul');
ul.addEventListener('click', function(event) {
	alert('clicked');
});
```
[코드2]를 보면 상위 태그인 `ul`태그를 `eventListner`에 등록 시킨다. 이렇게 되면 **이벤트 버블링**을 이용하여 하위에서 발생된 이벤트를 상위 태그에서 감지 할 수 있다. <br/>
-- 결과적으로 동적으로 추가된 `체크박스`를 클릭하면  `alert('clicked');` 코드가 동작을 한다.

### 3. 스코프 (Scope)
>  JavaScript에서 스코프란 <b>변수를 찾기위한 범위</b>를 뜻한다.

#### 스코프의 종류
- 전역 스코프 (Global Scope)
	-  코드 어디에서든지 참조 가능
	- ex> window 객체, 그 외 전역으로 도 선언 가능.
- 지역 스코프 (Local Scope)
	- 지역(함수) 내에서 선언된 변수이며 그 지역과 그 지역의 하부 지역에서만 참조할 수 있다.

#### Scope에 대해 찾아보다가 흥미로운 특징 발견, 바로 렉시컬 스코핑
- **렉시컬 스코핑(lexical soping)**
	- 렉시컬 스코핑을 찾다보면 이런 아래와 같은 예제들이 나온다
<br/>

`wrapper()` 실행시 콘솔에 어떤 값이 찍힐까요?

```js
var name =  'zero';
function  log()  {
	console.log(name); 
} 
function  wrapper()  { 
	var name =  'nero'; 
	log(); 
} 
wrapper();
```

"정답은 `nero`일 것 같지만 `zero` 입니다~" 라고 한다. 어떤 똥멍청이가 `var name`을 변수로 선언 해놓고 아래에서 똑같은 변수명을 선언하겠냐만 `lexcial scoping`을 설명하려면 그럴듯한 예제가 저것 밖에 없는 것 같다. <br/>
결론: 함수 `wrapper`를 선언 할 때, 함순 내부 변수는 상위 범위부터 제일 가까운 변수를 참조하게 된다. 전역 변수가 제일 상위범위의 변수로부터 가깝기 때문에  전역 변수에 할당된 `zero`값을 참조하게됨.

### 4. 실행 컨텍스트 (Execution Context)
> 실행 컨텍스트란 **우리가 작성한 코드가 실행되는 환경**을 말하며, scope , hoisting, this, function, closure 등의 동작원리를 담고 있는 자바스크립트의 핵심원리를 말한다.
#### 실행 컨텍스트의 두종류
- 글로벌 실행 컨텍스트(Global Execution Context)
	- 함수 내에서 실행되는 코드가 아니라면 모두 `Global Context`에서 실행됨
	- `Global Context`에 있는 실행 가능한 코드는 모두 스택에 쌓이며 `LIFO(Last in First out)` 로 실행됨.
- 함수 실행 컨텍스트(Functional Execution Context)
	- 선언된 함수가 호출될 시 `Functional Context`가 생성되며 함수안의 코드가 모두 실행되고 종료되면 `Functional Context`가 소멸된다. (`Functional Context`를 가지고 있지만 호출시 **생성** 된다)
	- `closure`을 사용한다면 scope가 소멸하지 않고 이용할 수 있다.


### 5. 호이스팅 (Hoisting)
### 6. 클로저 (Closure)
### 7. 네이티브 객체 vs 호스트 객체
### 8. this의 바인딩
### 9. var vs let vs cons
### 10. IIFE (Immediately-Invoked Function Expression)
### 11. 모듈 시스템: CommonJS, AMD, UMD, ES6
### 12. 콜 스택(Call stack)과 힙(Heap)
### 13. 이벤트 루프 (Event loop)
### 14. 프로토타입 (Prototype))
### 15. vs
### 16. 엄격 모드 (Strict mode)new의 동작방식ES6 (2015) 의 특징들
### 17. ES7 (ES2016) ~ ES8 (ES2017) 의 특징들
### 18. ES9 (ES2018) ~ ES10 (ES2019) 의 특징들
### 19. ES11 (ES2020) 의 특징들