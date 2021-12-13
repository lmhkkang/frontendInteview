## Javascript 기술 질문 
##### > 참조 https://github.com/baeharam/Must-Know-About-Frontend

### 1.  Ajax
>AJAX (Asynchronous Javascript And XML)   비동기식 자바스크립트와 xml
- 자바스크립트를 이용해 서버와 브라우져가 비동기 방식으로 데이터를 교환할 수 있는 통신 기능
- 브라우져가 가지고 있는 XMLHttpRequest 객체로 페이지 새로고침을 하지 않고 페이지의 일부만 데이터를 로드하는 기법.
![ajax비동기통신](https://user-images.githubusercontent.com/45140764/145498412-d00a25f7-2e10-4849-a282-910aef710832.png)

#### 비동기 통신이란??
[그림1]
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

[그림2]
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

[그림3]
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
[그림4]
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
### 4. 실행 컨텍스트 (Execution Context)
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