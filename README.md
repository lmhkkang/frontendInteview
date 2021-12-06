

## Frontend Developer Interview Q&A

1. 프런트엔드 빌드 시스템에 대해서 설명해보세요.
	1-1. 바벨이란?
	><b>Babel is Javscript Compiler</b><br/>
	javascript는 인터프리터 언어이지만 babel은 javascript로 결과물을 만들어주는 컴파일러이다. 브라우져가 다양해짐에 따라 특정 브라우져 (특히 fucking IE)에서 ES6+를 지원 할때 해당 코드를 지원 가능한 코드로 폴리필 해주는 것.  <br/> <br/> <em><b>그렇다면 폴리필이란?</b></em> 쉽게 말해 (fucking) IE에서 동작하지 않는 ES6+ 문법 또는 js 함수를 vanila javascript로 변환(ES5문법으로)하여 동작하도록 하게 해주는 것이다.
	
	1-2. 폴리필이란?
	>1-1번 질문에 답변이 있음.
	
	1-3. Node.js란?
	>웹 서버 등을 구축할 수 있는 javascript 런타임<br/><br/><em><b>그렇다면 런타임은 무엇이냐?</b></em> 컴퓨터 내에서 프로그램이 기동되면, 그것이 바로 그 프로그램의 런타임이다. 즉,  프로그래밍 언어가 구동되는 환경이라고 이해를 하면 된다. <br/> Javascript라면 Web Browser에서 작동하는 JavaScript 측면이 있고 Node.js라는 환경에서 구동되는 측면이 존재한다. 여기에서 Browser와 Node.js를 런타임이라고 볼 수 있다.
	
	1-4. NPM이란?
	>Node Package Manager</b><br/>개발자들이 개발한 오픈소스를 사용하거나 매니징할 수 있는 패키지 매니져
	
	1-5. ESLint란?
	>코드 상 에러를 표시해주는 라이브러리. 협업 할 때 에러, 코딩 규칙 혹은 스타일 보정을 해줄 수 있는 장점이 있다. 개인적인 경험 상, 주로 코딩 규칙을 정해 놓기 위해서 사용 하였다.
	
	1-6. Prettier란?
	>ESLint와 비슷한 라이브러리로서 정해진 코딩 규칙을 지키기 위해 사용되는 라이브러리. 코딩 스타일 통일 및 규칙을 커스터마이징 할 수 있음.(사용안해봄)
	
	1-7.웹 태스크 매니저란?
	><b>웹 개발 작업 자동화 도구</b>, Gulp나 Grunt같은 태스크 매니져. <br/>이전에는 웹서비스를 개발하고 웹서버에 배포할 때 HTML, CSS, JS 압축, 이미지 압축, CSS 전처리기 변환 같은 작업들을 수동으로 처리해야 했는데 이러한 일들을 자동화 해주는 도구들이 Grunt와 Gulp이다. (얼마나 예전인거임..?)
	
2. 웹팩이란? 모듈 번들러가 무엇인가요?
>웹팩이란 오픈소스 javascript 모듈 번들러로써 여러개로 나누어져 있는 파일들을 하나의 javascript 코드로 압축하고 최적화하는 라이브러리 이다. <br/><br/><b><em>그렇다면 모듈 번들러란?</em></b> 웹 어플리케이션을  구성하는 자원(HTML, CSS, Javascript, image)을 모두 각각의 모듈로 보고 이를 조합해서 병합된 하나의 결과물을 만드는 도구를 의미한다. <br/> 여기서 하나의 결과물이란 단어가 매우 fucking 추상적임. <br/>검색결과: 하나의 결과물= 하나의 js파일 or css파일 or  HTML  파일 -  BAMMN!! 
>
3. 자바스크립트 프레임워크를 써봤는지? 써봤다면 어떤 걸 쓰는지? 만약 쓴다면 쓰는 이유와 썼을 때의 장점?
>Yes, man~ React.js, Next.js를 사용 해봤음. <br/>웹앱 하이브리드 어플리케이션 개발을 해야했기 모바일 웹에서도 앱같이 동작하는 페이지를 제작하여야 했고 SPA가 이에 적합한 스펙으로 생각되었다. 그래서 React.js를 채택하였다. 그리고  SEO가 고객의 요구사항이었기 때문에 SSR이 가능하고 React와 호환이 되는 Next.js를 추가적으로 채택하게 되었음. </p>

4. “기획 - 디자인 - API 개발 - 프런트엔드 개발”의 서비스 절차에서 프런트엔드 개발자의 역할은 무엇이라고 생각하는지?
>야구의 4번 타자라고 생각합니다. 기획자가 (1번타자) 잘 만들어 놓은 기획안으로 디자이너가(2번타자) 멋지게 디자인을 하고 백엔드 개발자가(3번타자) 서버와 통신할 수 있는  API를 만들어서, 만들어진 결과물을 활용하여 화면에 보여주는 역할이 프론트 개발자(4번타자)의 역할이라고 생각합니다. <br/> 추가적으로 이 모두가 같은 팀이고 각자의 자기 역할을 해 내야 사용자(관객)의 만족을 이끌어 낼 수 있다고 생각합니다.

5. CORS란? CORS를 해결하기 위한 방법을 아는 대로 모두 설명해 주시고 보통 어떤 방식으로 해결하는지 자주 사용하는 방법 1가지와 함께 실제 해결하신 경험을 공유해 주세요.
>보통은 CORS policy라고 불리우며 policy 즉 보안 정책이다. 기본 HTTP header 구성외의 추가적으로 구성해서 다른 origin 즉 다른 protocol, host, port를 사용하는 곳에서 나의 resource에 접근하지 못하도록 하는 정책 및 매커니즘이다. 주로 외부 API를 사용할 때,  Front와 Back이 명확히 나뉜 프로젝트를 진행할 때 Front에서 시뻘겋게 발생한다. Hell No!!<br/> CORS 극복방법: 프로젝트 내에서 발생이라면 Backend 개발자에게 요청하여 response Access-Control 수정을 부탁. 또는 webpack config 에서 proxy설정을 해준다. 

6. 프런트엔드 성능 최적화란? 프런트엔드 성능 최적화 경험이 있다면 자세하게 설명해달라.
>성능 최적화란 화면 구성 시 각종 자원의 비용을 줄이는 것이다. 고객이나 기획자의 요구사항 변경에 따라 화면의 구성이 바뀌고 틀이 바뀌기 때문에 처음부터 완벽한 설계를 하는 프론트 개발자는 많지 않을 것이다. 이에 따라 개발 완성 단계에서 화면 로드시 불필요한 자원을 줄이는 것을 성능 최적화라고 할 수 있다. <br/> 필자는 성능 최적화의 최종 목적을 '사용자에게 보다 빠르고 정확하게 원하는 화면을 보여주기 위함' 이라고 생각한다. 유난히 느린 화면은 불필요한 css import를 줄이거나 한번에 너무 많은 image들이 로드되면 이는 결국 '느린화면'이 되어버렸다. 필자는 이런 화면을 PM 컨펌하에 기획자와 상의하여 스크롤 시 순차적으로 불러올 수 있는 화면 설계로 바꾼적이 있다. (사실 통상적으로 화면의 css  import 줄인다고 크게 차이는 나지 않음)

7. 백엔드 개발 경험이 있는가?
>Yes, Java & Python man~

8. (꼬리 질문) REST API 구축 경험과 구현 관점에서의 간단한 REST API 설계 방식 설명해 보세요. 브라우저의 URL 요청을 받아서 서버의 데이터를 화면에 다시 뿌려주기까지의 백엔드 쪽의 플로우를 알고 있는지 확인하는 차원.
> REST API (Representational State Transfer Application Programming Interface) 
> 1. CRUD에 맞춰서 POST,GET,PUT,DELETE 어노테이션 활용하였다. 메소드 작명시 앞에 CRUD 중 하나의 동작을 붙였다. 
> 2. URL 명명시 공통개발자 지시에 따른 URL 명명을 하였음. 보통 메뉴 DEPTH 별로 URL 명명이 지어짐을 발견. EX) 고객서비스의 공지사항 -> /service/notice 
> 3.  Front는 axios 통신을 이용하고 backend 에서 정해준 url 호출 시 controller -> service -> dao ->  mapper DB query exec 순으로 호출되어 Front로 데이터를 전달해준다.
9.  Virtual DOM이 뭔지 아시는지? 썼을 때의 장점?
> Virtual Document Object Model (가상 문서 객체 모델)
> 그전에 <b> DOM (Document Object Model)</b> 이란 무엇인가? 
>  <em>DOM은 HTML, XML document와 상호작용하는 API이다.</em>  - MDN Official
>  MDN 오피셜이라지만 뭔말인지 와닿지 않는다. 그래서 내 나름대로의 정의를 내려보았다. 
>
>문서 객체 모델(DOM)중에 <b>문서 객체</b>란 각종 HTML 태그들을 Javascript가 이용할 수 있는 객체(object)로 만들면 그것을 문서 객체라고 한다. 그렇다면 <b>모델</b>은 틀, 형태라는 뜻을 내포하고 있다. 프로그래밍에서 틀, 형태를 내포하는 모델을 왜 만드는가?  생각해보면 쉽게 인식하기 위해서 이다. 
>정리하자면, <b>DOM은 웹 브라우져가 html 페이지를 인식하는 방식</b> 정도로 할 수 있을 것 같다.
>
><b>그러면 여기서 Virtual DOM 은 무엇인가?</b>
> 웹페이지에서 DOM은  
> 1. DOM tree 생성 
> 2. Render tree 생성
> 3. Layout계산
> 4. Paint

>위와 일련의 동작 과정을 겪는다. 헌데 DOM이 바뀌면 위의 일련의 모든 과정을 다시 반복하게 된다.  이러한 환경에서 Virtual DOM은 비효율적인 과정을 조금도 효율적으로 동작할 수 있도록 해준다. 
>
> <b>Virtual DOM은 DOM 상태를 메모리에 저장하고 변경 전과 변경 후의 상태를 비교하여 최소한의 내용만 반영 하는 기능이다. (Layout계산을 한번만 할 수 있음)</b>
10.  (꼬리 질문) 브라우저 동작 원리 아는 만큼 설명
> 1. DOM tree 생성 
> 2. Render tree 생성
> 3. Layout계산
> 4. Paint
> 
> 브라우져의 여러 엔진중 렌더링 엔진은 html문서를 파싱하여 콘텐츠트리 내부에서 DOM tree로 변환한다. 그 다음 외부 CSS 파일과 함께 포함된 스타일 요소도 파싱. 스타일 정보와  HTML 표시 규칙은 Render tree 라고 불리는 또다른 트리를 생성한다. 
> 
>Render tree는 색상 또는 면적과 같은 시각적 속성이 있는 요소를 정해진 순서대로 화면에 표시한다.
>Render tree 배치시 Layout을 높이, 넓이, 위치가 계산되어 각 노드가 화면의 정확한 위치에 표시된다.  다음은 UI 백엔드에서 렌더 트리의 각 노드를 가로지르며 형사을 만들어내는 그리기 (Paint) 과정이다.
>
>중요한건 일련의 과정이 점진적으로 진행된다는 것이다. 렌더링 엔진은 좀 더  나은 사용자 경험을 위해 Html 파싱이 끝날때 까지 기다리지 않고 네트워크로 부터 먼저 받은 내용의 일부를 배치와 그리기 과정을 시작한다. 
11.  웹 서비스 배포 시스템 구축 경험?
yes~ AWS java project  배포 경험쓰~

12.  (꼬리 질문) CI, CD가 무엇인지 아는지? 구축해본 경험 혹은 사용해본 경험이 있는지 - 테스트 자동화 경험? 단위 테스트 또는 E2E 코드를 작성해 본적이 있는지?
>  CI (Continouse Integration) , CD(Continuouse Deployment)
>  CI: 형상관리 CD: 지속적인 배포 즉 배포 자동화
>  필자는 CI/CD 모두  경험이 있다.  CI는 github, svn을 사용해보았고, CD는 jenkins 구축 경험이 있다.
>   개인적으로 Agile 개발 환경을 겪어보진 못했지만 CI/CD 구축은 Agile 개발에서 필수 요소라고 생각한다.
>
> 아쉽지만 E2E는 작성해보지 않았다. 하지만 Front 단위테스트로 Jest 및 Mocha를 사용해 보았다.
> 유지보수 시 추가적으로 새로운 로직을 도입해야 하는 상황에서 로직을 위의 Javascript Test tool 로 먼저 실험해보았던 경험이 있다.
13.  (꼬리 질문) 테스팅 라이브러리와 프레임워크에 특화된 테스팅 라이브러리는 각각 어떤 걸 썼는지?
>Jest, Mocha 답변 끝.
14.  꼬리 질문) 테스트 대상과 커버리지는 보통 어떻게 잡는지?
> 테스트 커버리지가 무엇인지도 몰라서 테스트 커버리지의 정의를 적어보겠다. (내맘이다)
> <b>테스트 커버리지란 시스템 또는 S/W의 테스트를 논할때 얼마나 테스트가 충분한 가를 나타낸 것이다. 즉, 수행한 테스트가 테스트의 대상을 얼마나 커버했는지를 나타낸다.</b>

16.  웹 접근성과 시맨틱 마크업이란? 이 2가지를 지키기 위해 보통 어떤식으로 마크업을 작성하는지?
17.  웹 서비스를 기획부터 배포까지 모두 스스로 해본 경험이 있는가? 토이 프로젝트나 회사 서비스 등
18.  (꼬리 질문) 구체적으로 어떤 역할을 수행했는지 설명
19.  SEO(검색 엔진 최적화)란? 적용 사례가 있으면 구체적인 적용 방법도 같이 설명
20.  REST API로 받은 객체와 배열은 보통 어떤 자바스크립트 API나 로직을 이용해서 화면에 맞게 가공을 하는지?
21.  (꼬리 질문) map, filter, reduce API 사용 경험과 각각 설명
22.  (꼬리 질문) 자바스크립트 클로저란?
23.  서버 사이드 렌더링과 싱글 페이지 애플리케이션의 차이점?
24.  (꼬리 질문) 서버 사이드 렌더링이나 SPA로 각각 구현해 본 경험이 있는지?
