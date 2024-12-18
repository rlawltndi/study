### Hooks
- 함수형 컴포넌트에서 상태관리, 사이드 이펙트 처리 등 다양한 기능을 제공하는 기능이다.  
- react에서 제공하는 것과 동일하지만, 모바일 환경에 최적화된 일부 추가 기능도 있다.  
#
### useState
- useState는 값을 변경할 때마다 컴포넌트를 재렌더링합니다.
- 컴포넌트의 상태를 설정하고, 해당 상태를 업데이트 할 수 있는 함수를 반환한다.
- 함수형 컴포넌트 내에서만 사용이 가능하다.
- 상태 값을 변경하는 setter 함수가 제공됩니다.

```js
const [상태, 상태를갖는함수] = useState(초기값);

```
#
### useEffect

- 함수형 컴포넌트에서 사이드 이펙트를 처리할 수 있게 해준다.  
- 사이드 이펙트 : 데이터 가져오기 , 구독설정, DOM수정 조작 등 렌더링 외의 동작  
- 두 번째 매개변수로 의존성 배열을 전달하면 특적 값의 변화에 따라 효과를 실행 할 수 있다.  
- 컴포넌트가 언마운트 되거나, 의존성이 변경될 때 실행할 cleanUp함수도 반환 가능하다.  

```js
useEffect(() => {
  // 사이드 이펙트 로직

  // 선택적 정리 함수:
  return () => {
    // 정리 로직
  };
}, [dependencies]); //,[dependencies] : 이 배열이 값이 변경될 때만 useEffect 실행(산택사항) 

```

```js
useEffect(() => {
  console.log('컴포넌트가 마운트되었습니다.');
}, []); // 컴포넌트가 처음 마운트될 때 한 번만 실행된다.

```

```js
useEffect(() => {
  const intervalId = setInterval(() => {
    console.log('1초마다 실행');
  }, 1000);

  // 정리 함수는 컴포넌트가 언마운트되거나, 의존성 배열의 값이 변경될 때 호출됩니다.
  return () => clearInterval(intervalId);
}, []);

```

#
### useContext
-함수형 컴포넌트에서 Context 값을 쉽게 접근할 수 있게 해준다.  
- Context는 컴포넌트 트리에서 'props'를 통해 값을 전달하지 않고 전역적으로 공유할 수 있게 해주는 기능이다.  
- "props drilling"을 피할 수 있다.  
- props drilling : 상위 컴포넌트에서 하위 컴포넌트로 값을 여러 단계를 걸쳐 전달.  

- 사용 예시
```js
import React, { createContext, useContext, useState } from "react";

// Step 1: Context 생성
const MyContext = createContext();

const App = () => {
  const [message, setMessage] = useState("Hello from Context");

  return (
    // Step 2: Context 값 제공
    <MyContext.Provider value={message}>
      <Child />
      <button onClick={() => setMessage("Updated message from Context")}>
        Update Context
      </button>
    </MyContext.Provider>
  );
};

const Child = () => {
  // Step 3: Context 값 사용
  const contextValue = useContext(MyContext);

  return <div>{contextValue}</div>;
};

export default App;

```
#
### useRef
- 함수형 컴포넌트에서 변수값을 유지하거나 DOM 요소에 접근할 수 있도록 도와주는 기능이다.  
- ref 객체를 반환, 이 객체는 current라는 속성을 가지며 , 이 속성에 값을 저장할 수 있다.  
- useRef로 저장된 값은 컴포넌트가 리렌더링되어도 유지된다.

```js
import React, { useRef } from 'react';

function MyComponent() {
  const inputRef = useRef(null); // useRef를 사용하여 ref 객체 생성

  const handleClick = () => {
    // inputRef.current를 통해 DOM에 접근할 수 있음
    inputRef.current.focus();
  };

  return (
    <div>
      <input ref={inputRef} type="text" />
      <button onClick={handleClick}>Focus the input</button>
    </div>
  );
}

```
- useRef와 useState의 차이점  
  - useState는 상태를 변경하면 컴포넌트가 리렌더링된다.  
  - useRef로 저장된 값은 컴포넌트를 리렌더링하지 않고 계속 유지된다.  
  - useRef는 컴포넌트의 상태를 추적하거나 변경하지 않고, 참조값만 유지하고싶을 때 유용하다.  
#
### useCallback
- 메모이제이션(memoization)기법, 함수가 불필요하게 재생성되지 않도록 저장해두는 역할읗 한다.
- 첫 번째 인자로 함수, 두 번째 인자로 의존성 배열을 받습니다.

```js
const memoizedCallback = useCallback(() => {
  // 실행할 코드
}, [의존성 배열]);
```
- 함수 전달: 부모 컴포넌트에서 자식 컴포넌트로 콜백 함수 등을 전달할 때,  
              매 렌더링마다 새로운 함수 객체가 생성되면 자식 컴포넌트가 불필요하게 리렌더링될 수 있습니다.  
              useCallback을 사용하면 함수가 메모이제이션되어 리렌더링을 최소화할 수 있다.
- 성능 최적화: 고차원 컴포넌트나 렌더링이 자주 발생하는 애플리케이션에서 성능 최적화가 필요할 때 유용하다.  
#
### useMemo
- 주어진 계산 결과를 기억하여, 의존성 배열에 있는 값들이 변경되지 않는 한 같은 값을 재사용한다.
- 매번 렌더링될 때 마다 계산을 다시 하지 않고, 이전에 계산이 된 값을 재사용할 수 있다.
- 성능 최적화가 필요한 경우에만 사용하고, 기본적인 성능 문제는 렌더링 최적화나 코드 구조 개선을 통해 해결하는 것이 좋다.
```
const memoizeValue = useMemo(()=>{
  //값이 변경될 때만 실행되는 계산
  return expensiveComputation(input)
},[input]) // 의존성 배열 : input이 변경될 때만 실행
```
- 첫 번째 인자 : 메모제이션 할 계산 함수
- 두 번째 인자 : 의존성 배열 , 이 배열 안에 있는 값이 변경될 때만 계산이 다시 실행
  
- 사용처
  - 불필요한 계산을 방지하고 싶을 때 , 복잡한 계산을 자주 실행해야 하는 경우 값이 변경되지 않으면 이전 결과 재사용
  - 성능 최적화가 필요한 경우, 큰 리스트를 필터링하거나 정렬하는 작업에서 성능 저하를 방지하기 위해 사용
 
- 주의사항
  - 성능 최적화를 위한 도구일 뿐 , 지나치게 사용하면 오히려 성능이 저하될 수 있다.
  - 값이 자주 변경되거나 비교 값이 복잡한 객체일 경우 효율적이지 않다.
    

#
### useReducer
- 세 가지 인자를 받는다.
  - reducer 함수 : 상태를 어떻게 업데이트할지 정의하는 함수이다.
  - 초기 상태 : 상태의 초기 값이다.
  - 초기화 함수(선택) : 초기 상태를 설정하는 함수이다.
```
const [state , dispatch] = useReducer(reducer, initialState)
```

- EX
1. reducer 함수
  - reducer 함수는 두 가지 인자를 받는다.
    - state : 현재 상태
    - action : 상태를 업데이트 하기 위한 액션 객체
     
  - reducer 함수는 새로운 상태를 반환해야 하고, 상태를 직접 변경하지 않고 , 항상 새로운 상태 객체를 반환한다.
```
const reducer = (state,action) =>{
  switch (action,type) {
  case "INCREMENT":
    return{count : state.count + 1}
  case "DECREMENT":
    return{count : state.count - 1}
  defalt:
    return state
}
}
``` 
2. useReducer 사용
- useReducer 훅을 사용하여 상태와 dispatch 함수를 얻는다. dispatch 함수는 액션 객체를 받아서 상태를 업데이트한다.
```
import React, { useReducer } from 'react';

const Counter=()=>{
  const initialState = {count : 0}

//useReducer 훅 사용
const [state, dispatch] = useReducer(reducer, initialState)

return (
  <div>
    <p>Count : {state.count}</p>
    <button onClick={() => dispatch({ type: 'INCREMENT' })}>Increment</button>
    <button onClick={() => dispatch({ type: 'DECREMENT' })}>Decrement</button>
  </div>
)
}
```
- userReducer를 사용하는 상황, 이유
  -  상태가 복잡할 때 : 여러 개의 상태 변수를 다뤄야 하는 경우, useState 보다 useReducer가 더 적합하다.
  -  상태 업데이트 로직이 복잡할 때 : 액션에 따른 상태 변화를 명확히 구분하고 , 상태 변경의 흐음을 쉽게
      관리할 수 있다.
  - 배경 작업을 처리할 때 : 여러 단계의 로직을 처리하는 복잡한 비즈니스 로직을 구현할 때 유리하다.

- useState와 useReducer 의 차이점
  - useState는 간단한 상태 관리를 할 때 사용한다. 상태가 간단하거나 하나의 값만 관리할 때 적합하다.
  - useReducer는 상태 관리가 복잡할 때 유용하고 , 액션을 통해 상태를 업데이트 하는 구조이기 때문에
    여러 가지 상태변화를 관리할 수 있다.

- useReducer는 복잡한 상태 업데이트 로직을 간결하게 관리하고 , 액션 기반의 흐름을 통해 상태를 제어할 수 있는
  훅이다.
  여러 상태를 처리하거나 상태 업데이트가 복잡할 때 useState 보다 더 적합하다.
  







