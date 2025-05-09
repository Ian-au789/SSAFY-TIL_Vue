# Basic Syntax 2

## Computed()

: 미리 계산된 속성을 사용하여 템플릿에서 표현식을 단순하게 하고 불필요한 반복 연산을 줄임 

- 반환되는 값은 computed red이며 일반 refs와 유사하게 계산된 결과를 .value로 참조 가능 

- computed 속성은 의존된 반응형 데이터를 자동으로 추적

- 의존하는 데이터가 변경될 때만 재평가 

- computed vs method : computed 속성은 의존된 반응형 데이터를 기반으로 캐시 -> 데이터가 변경되지 않으면 이미 계산된 결과 재평가 필요 없이 즉시 반환 vs method 호출은 렌더링 발생 때마다 항상 함수 실행 (연산 낭비) 

예시)

        const { createApp, ref, computed } = Vue
        
        const todos = ref([
            { text: 'Vue 실습' },
            { text: '자격증 공부' },
            { text: 'TIL 작성' }
            ])

        const restOfTodos = computed(() => {
          return todos.value.length > 0 ? '아직 남았다' : '퇴근!'
        })


## 제어문

### v-if

: 표현식의 값이 true/false를 기반으로 요소를 조건부로 렌더링 

예시)

        <p v-if="isSeen">true일때 보여요</p>
        <p v-else>false일때 보여요</p>

        <div v-if="name === 'Alice'">Alice입니다</div>
        <div v-else-if="name === 'Bella'">Bella입니다</div>
        <div v-else-if="name === 'Cathy'">Cathy입니다</div>
        <div v-else>아무도 아닙니다.</div>


### v-show

: 표현식 값의 true/false를 기반으로 요소의 가시성을 전환 (항상 DOM에 렌더링 되어있고 CSS 속성만 전환)


### v-for

: 소스 데이터를 기반으로 요소 또는 템플릿 블록을 화면에 반복적으로 렌더링 (배열 반복, 객체 반복)

예시) 

        <div v-for="(item, index) in myArr">
        {{ index }} / {{ item.name }}
        </div>
        <div v-for="(value, key, index) in myObj">
        {{ index }} / {{ key }} / {{ value }}
        </div>

- 각 v-for의 하위 영역은 상위 영역에 접근 가능
- v-for 와 key를 함께 사용 : 내부 컴포넌트의 상태를 일관되게 하여 데이터의 예측 가능한 행동을 유지하기 위함 
- key : 각 항목이 서로 구분되는 고유 식별자 (number or string) 
- 동일 요소에서 v-if가 v-for 보다 우선순위가 높음 




