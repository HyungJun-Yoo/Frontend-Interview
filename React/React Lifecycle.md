## React Lifecycle

- React Lifecycle은 컴포넌트가 생성될 때부터 소멸될 때까지의 단계를 의미합니다. 이 단계를 이해하고 활용하면 컴포넌트의 동작 방식과 성능을 최적화할 수 있습니다.

- React 컴포넌트의 라이프사이클은 크게 세 가지 카테고리로 나뉩니다.
  - 마운트(Mounting)
  - 업데이트(Updating)
  -  언마운트(Unmounting)

![LifeCycle](/React/image/LifeCycle.png)

### Mounting
- 컴포넌트가 생성되고 DOM에 삽입되는 과정
- componentDidMount()
  - 컴포넌트가 마운트(화면에 나타나기)된 후에 실행되는 메서드입니다.
  - 주로 API 요청, 이벤트 등록 등 초기화 작업을 수행합니다.

### Updating
- 컴포넌트의 props 또는 state가 변경되어 다시 렌더링되는 과정
- componentDidUpdate()
  - 컴포넌트의 props나 state가 변경되어 다시 렌더링이 되었을 때 실행되는 메서드입니다.
  - 이전의 props와 state값을 파라미터로 받아와서 이전 값과 비교하여 업데이트 작업을 수행합니다.

### Unmounting
- 컴포넌트가 DOM에서 제거되는 과정
- componentWillUnmount() 
  - 컴포넌트가 언마운트(화면에서 사라지기)되기 전에 실행되는 메서드입니다.
  - 주로 이벤트 등록 해제, 타이머 해제 등 리소스 반환 작업을 수행합니다