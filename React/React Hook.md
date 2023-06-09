## React Hook

- React 버전 16.8에서 새롭게 추가된 기능으로, 함수형 컴포넌트에서도 상태(state)와 생명주기(lifecycle) 메소드를 사용할 수 있도록 해주는 기능
- React Hook은 useState, useEffect, useContext, useReducer 등 다양한 Hook 함수를 제공

### React Hook 장점

1. 코드가 간결해진다
> React Hook은 함수형 컴포넌트를 사용하면서도 Class 컴포넌트에서 사용되던 기능들을 사용할 수 있도록 해줍니다. 이를 통해, 코드가 간결해지고 가독성이 향상됩니다.

2. 상태 로직의 재사용성이 높아진다
> React Hook을 사용하면 상태 로직을 컴포넌트 외부에 작성할 수 있습니다. 이를 통해 상태 로직의 재사용성이 높아지며, 코드의 중복을 줄일 수 있습니다.

3. Class 컴포넌트의 단점을 보완한다
> React Hook을 사용하면 Class 컴포넌트에서 발생하는 this 바인딩 문제나 생명주기 관련 문제 등을 해결할 수 있습니다.

4. 코드의 가독성과 유지보수성이 높아진다
> React Hook을 사용하면 함수형 컴포넌트를 사용하면서도 상태와 생명주기를 관리할 수 있습니다. 이를 통해 코드의 가독성과 유지보수성이 높아집니다.

### React Hook 단점

1. Class 컴포넌트와 호환되지 않는다
> React Hook은 Class 컴포넌트에서 사용되는 this나 생명주기 메서드 등과 같은 기능을 사용할 수 없습니다. 따라서, 기존에 작성된 Class 컴포넌트와의 호환성이 떨어질 수 있습니다.

2. Hook 사용 규칙을 잘 지켜야 한다
> 1. 컴포넌트 함수에서만 Hook을 호출해야 합니다. 일반 JavaScript 함수에서 Hook을 호출하면 동작하지 않습니다.
> 2. 항상 최상위 레벨에서 Hook을 호출해야 합니다. 반복문, 조건문 또는 중첩된 함수 내에서 Hook을 호출하지 마세요.
> 3. useState, useEffect, useContext와 같은 기본 제공 Hook을 사용하세요. 직접 만든 Hook은 use로 시작하는 함수 이름으로 정의해야 합니다.
> 4. 모든 Hook은 동일한 순서로 호출되어야 합니다. 이것은 렌더링의 순서가 동일하기 때문에 Hook 호출 순서를 변경하는 것이 안전하지 않기 때문입니다.
> 5. 조건문 내에서 Hook을 사용하면 안됩니다. 대신 조건문이 필요한 경우 컴포넌트를 나누어 사용하세요.
> 6. React Hook을 사용하는 경우, 함수 컴포넌트를 사용하세요. 클래스 컴포넌트에서는 Hook을 사용할 수 없습니다.