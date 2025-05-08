# Basic Syntax

: DOM을 기본 구성 요소 인스턴스의 데이터에 선언적으로 바인딩할 수 있는 HTML 기반 템플릿 구문을 사용 

1. Text Interpolation : 이중 중괄호 구문을 사용한 가장 기본적인 형태, 인스턴스의 msg 속성 값으로 대체 후 변경될 때마다 업데이트

    <p>Message : {{ message }}</p>

2. Raw HTML : 데이터를 일반 텍스트로 해석하지 않고 실제 HTML을 출력하기 위해 v-html 태그 사용

    <div v-html="rawhtml"></div>

3. Attribute Bindings : HTML의 속성 내에서 이중 중괄호를 사용할 수 없기 때문에 v-bind 사용

    <div v-bind:id="dynamicId"></div> 

4. JavaScript Expressions : Vue는 모든 데이터 바인딩 내에서 JavaScript 표현식 기능 지원 


## Directive

: v- 접두사가 있는 특수 속성

- Directive의 속성 값은 단일 JavaScript 표현식이어야 함 (v-for, v-on 제외)
- 표현식 값이 변경될 때 DOM에 반응적으로 업데이트 
- 구조 -> Name:Argument.Modifiers=Value  예시) v-on:submit.prevent="onSubmit"


### v-bind

: 하나 이상의 속성 또는 컴포넌트 데이터를 표현식에 동적으로 바인딩

- HTML의 속성 값을 Vue의 상태 속성 값과 동기화 되도록 함 
- v-bind shorthand = : 
- 대괄호로 감싸서 directive argument에 JavaScript 표현식을 사용 가능 

- class와 style은 모두 HTML 속성이므로 v-bind 사용 가능 or 객체 또는 배열 활용 가능 
- 객체를 :class에 전달하여 클래스를 동적으로 전환 가능
- 객체에 더 많은 필드를 포함하여 여러 클래스를 전환할 수 있음 
- inline 방식이 아닌 반응형 변수를 활용해 객체를 한 번에 작성 


### v-on

: DOM 요소에 이벤트 리스너를 연결 및 수신 

- inline handlers : 이벤트가 트리거 될 때 실행 될 JavaScript 코드 -> $event 변수를 사용해 메서드에 전달
- Method handlers : 컴포넌트에 정의된 메서드 이름 
- v-on shorthand : @

### Modifiers

: 데이터에 관한 논리를 작성하기 위함 


