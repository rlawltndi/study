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
#
### useMemo
#
### useReducer
