# Introduction to Vue

: 클라이언트 측에서 UI와 상호작용을 개발하기 위해 사용되는 JavaScript 기반 프레임워크 

- 동적이고 반응적인 웹 애플리케이션 개발
- 코드 재사용성 증가 (컴포넌트 기반 아키텍처, 모듈화된 코드 구조)
- 개발 생산성 향상 

### SPA

: Single Page Application (단일 페이지에서 동작하는 웹 어플리케이션)

- 최초 로드 시 필요한 모든 리소스 다운로드
- 이후 페이지 갱신에 필요한 데이터만을 비동기적으로 전달 받아 화면의 필요한 부분만 동적으로 갱신 (AJAX)
- JavaScript를 사용해 클라이언트 측에서 동적으로 콘텐츠 생성 및 업데이트 (CSR)


### CSR

: Client-Side Rendering (클라이언트에서 콘텐츠를 렌더링하는 방식)

1. 클라이언트는 서버로부터 최소한의 html 페이지와 해당 페이지에 필요한 JavaScript 응답 받음
2. 그런 다음 클라이언트 측에서 JavaScript를 사용하여 DOM을 업데이트 하고 페이지를 렌더링
3. 이후 서버는 더 이상 HTML을 제공하지 않고 요청에 필요한 데이터만 응답

- 서버에 전송되는 데이터의 양 최소화 -> 빠른 페이지 전환
- 사용자 경험 (새로고침이 없음)
- Frontend와 Backend의 명확한 분리 (더 쉬운 개발 및 유지보수)

### Vue

1. 선언적 렌더링 : Vue 템플릿 구문을 사용하여 JavaScript 데이터를 기반으로 화면에 출력될 HTML을 선언적으로 작성

2. 반응성 : JavaScript 상태 변경을 추적하고, 변경사항이 발생하면 자동으로 DOM 업데이트 

- 반응형 데이터 바인딩 (데이터 변경 시 자동 UI 업데이트)
- 컴포넌트 기반 아키텍처 (재사용 가능한 UI 조각)
- 간결한 문법과 직관적인 API
- 유연한 스케일링 

예시)

        <!doctype html>
        <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <title>Document</title>
        </head>
        <body>
            <div id="app">
                <h1>{{ message }}</h1>
                <button v-on:click="count++">Count is {{ count }}</button>
            </div>
            
            <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
            <script>
            // console.log(Vue)
            // const createApp = Vue.createApp
            // console.log(createApp)
                const { createApp, ref } = Vue

                const app = createApp({
                    // setup 함수
                    setup() {
                        const message = 'Hello Vue!'
                        const count = ref(0)
                        console.log(count)

                        return {
                            message,
                            count 
                        }
                    }
                })

                app.mount('#app')
            </script>
        </body>
        </html>