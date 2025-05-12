# Single File Components

Component : 재사용 가능한 코드 블록 

- UI를 독립적이고 재사용 가능한 일부분으로 분할하고 각 부분을 개별적으로 다룰 수 있음
- 자연스럽게 애플리케이션은 중첩된 Component의 트리 형태로 구성됨

Single-File Components (SFC) : Component의 템플릿, 로직 및 스타일을 하나의 파일로 묶어낸 특수한 파일 형식 (*.vue 파일) = HTML + CSS + JavaScript 

- template - script - style 형식
- 각 vue 파일은 하나의 "script setup" 블록을 하나만 포함 <- 컴포넌트의 setup() 함수로 사용
- 여러 style 태그 포함 가능
- scoped가 지정되면 CSS는 현재 컴포넌트에만 적용 
  
## Vite 프로젝트

: 빠른 개발 환경을 위한 빌드 도구와 개발 서버 제공

1. Vue Project 생성 (Vite 기반 빌드) : npm create vue@latest 

2. Node Package Manager (NPM) : Node.js의 기본 패키지 관리자, 수많은 오픈 소스 패키지와 라이브러리를 제공 

3. Node.js : 기존 브라우저 안에서만 동작할 수 있던 JavaScript를 브라우저가 아닌 서버 측에서도 실행할 수 있게 함 

4. Module : 프로그램을 구성하는 독립적인 코드 블록 -> 애플리케이션이 점점 발전하면서 모듈 개수가 너무 증가 (병목 현상)

5. Bundler : 여러 모듈과 파일을 하나의 번들로 묶어 최적화해 애플리케이션에서 사용할 수 있게 만들어주는 도구 


### Vue Project 구조

1. public 디렉토리 : 소스코드에서 참조되지 않는 / 항상 같은 이름을 갖는 / import 할 필요 없는 정적 파일을 위치 시킴 (항상 root 절대 경로를 사용하여 참조 "public/icon.png" -> "/icon.png")

2. src 디렉토리 : 프로젝트의 주요 소스 코드를 포함하는 곳, 실제로 우리가 작업하게 될 대부분의 소스 코드가 위치 (컴포넌트, 스타일, 라우팅 등)

3. src/assets : 프로젝트 내에 사용되는 정적 자원 (이미지, 폰트, 스타일 시트 등)을 관리, 컴포넌트 자체에서 참조하는 내부 파일 저장

4. src/components : 실제로 페이지에서 사용하게 될 개별 Vue 컴포넌트들이 위치

5. src/Vue.vue : Vue 앱의 Root 컴포넌트, 다른 하위 컴포넌트들 포함, 애플리케이션 전체의 레이아웃과 공통 요소 정의

6. src/main.js : Vue 애플리케이션을 초기화하고, App.vue를 DOM에 마운트하는 시작점, 필요한 라이브러리를 import하고 전역 설정 수행 

7. index.html : Vue 앱의 기본 HTML 파일, main.js에서 App.vue 컴포넌트를 렌더링해 이 index.html의 특정 위치에 마운트 시킴 (Vue 앱이 SPA인 이유) 


### 패키지 관리

1. package.json : 프로젝트에 관한 기본 정보와 패키지 의존성을 정의하는 '설계도' 역할 (어떤 패키지를 사용하고, 어떤 스크립트를 실행할 수 있는가)

2. package-lock.json : 실제 설치된 패키지들의 정확한 버전 정보를 기록, 다른 환경에서도 동일한 패키지 구성을 재현 가능 

3. node_modules : package.json, package-lock.json에 따라 실제로 설치된 모든 패키지가 저장되는 곳 

