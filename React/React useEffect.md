## React useEffect

### useEffect란 무엇인가요?
- useEffect는 React component가 렌더링 될 때마다 특정 작업(side effect)을 실행할 수 있도록 하는 리액트 Hook입니다.
- side effect는 component가 렌더링 된 이후에 발생하는, 비동기로 처리되어야 하는 부수적인 효과들을 뜻합니다.
- 함수형 컴포넌트에서도 클래스형 컴포넌트에서 사용되었던 라이프사이클 메서드의 역할을 대체할 수 있게 되었습니다.

<br />

### useEffect 형태

```
useEffect(callback, dependencies)
```

- callback: useEffect 함수에 전달하는 첫 번째 인자로 실행할 작업을 정의하는 콜백 함수입니다.
- dependencies: useEffect 함수에 전달하는 두 번째 인자로, useEffect가 실행될 조건을 설정하는 배열입니다.

<br />

### useEffect 라이프사이클
<br />

- 마운트: 컴포넌트가 처음으로 DOM에 렌더링될 때 실행됩니다. useEffect 함수에 전달하는 dependencies 배열이 빈 배열([])일 때, 콜백 함수는 컴포넌트가 마운트될 때 한 번만 실행됩니다.

```
useEffect(() => {
  // 마운트 때만 실행되는 작업
}, []);
```

<br />

- 업데이트: 컴포넌트가 업데이트될 때마다 실행됩니다. dependencies 배열이 전달되면, 배열에 포함된 값이 변경될 때마다 콜백 함수가 실행됩니다.

```
useEffect(() => {
  // 업데이트 때마다 실행되는 작업
}, [dependency1, dependency2]);
```

<br />

- 언마운트: 컴포넌트가 DOM에서 사라지기 전에 실행됩니다. 이 때, useEffect 콜백 함수에서 반환하는 함수가 호출됩니다. (cleanup)

```
useEffect(() => {
  // 마운트 때만 실행되는 작업
  return () => {
    // 언마운트 때 실행되는 작업
  };
}, []);
```

<br />

### 의존성 배열에 빈 배열([])을 전달하는 경우와 전달하지 않는 경우의 차이는 무엇인가요?

- 의존성 배열([])을 전달하는 경우
  - 컴포넌트가 처음 마운트될 때(componentDidMount) 한 번만 실행됩니다.

- 의존성 배열을 전달하지 않는 경우
  - 컴포넌트가 처음 마운트될 때(componentDidMount)와 컴포넌트의 state나 props가 변경될 때(componentDidUpdate)마다 매번 실행됩니다.