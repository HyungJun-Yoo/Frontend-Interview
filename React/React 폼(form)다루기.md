## 폼(form)다루기

- React에서 폼을 다루는 방법은 크게 제어 컴포넌트(Controlled Components)와 비제어 컴포넌트(Uncontrolled Components)로 나뉩니다.

### 제어 컴포넌트(Controlled Components)

- 제어 컴포넌트는 React 컴포넌트의 상태(State)와 이 상태를 업데이트하는 함수(Handler)를 사용하여 form 값을 관리하는 방법입니다.
- 예를 들어, input 요소의 값이 변경될 때마다 onChange 핸들러를 사용하여 상태를 업데이트하고, 이 상태 값을 다시 input 요소의 value에 할당합니다. 
- 이렇게 하면 React가 form 데이터의 상태를 관리하게 되므로 제어 컴포넌트를 사용하면 form 데이터를 쉽게 검증하거나, 수정하기 쉬워지는 등의 이점이 있습니다.

```
import React, { useState } from 'react';

function Form() {
  const [name, setName] = useState('');
  const [email, setEmail] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    console.log(`Name: ${name}, Email: ${email}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" value={name} onChange={(e) => setName(e.target.value)} />
      </label>
      <label>
        Email:
        <input type="email" value={email} onChange={(e) => setEmail(e.target.value)} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```

### 비제어 컴포넌트(Uncontrolled Components)

- 비제어 컴포넌트는 React가 form 데이터의 상태를 관리하지 않고, DOM에서 직접 값을 가져오는 방식입니다. 
- 예를 들어, DOM에서 폼을 전송할 때, onSubmit 이벤트에서 form 요소에 직접 접근하여 값을 가져옵니다. 
- 이 방식은 React 상태를 직접 수정하지 않으므로 구현하기 간단하지만, React가 form 데이터를 관리하지 않으므로 검증이나 수정이 어려워질 수 있습니다.

```
import React, { useRef } from 'react';

function Form() {
  const nameRef = useRef();
  const emailRef = useRef();

  const handleSubmit = (e) => {
    e.preventDefault();
    const name = nameRef.current.value;
    const email = emailRef.current.value;
    console.log(`Name: ${name}, Email: ${email}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" ref={nameRef} />
      </label>
      <label>
        Email:
        <input type="email" ref={emailRef} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```

### useRef

- React에서 제공하는 Hook 함수 중 하나로, DOM 요소 또는 컴포넌트에서 가리키고자 하는 값을 저장할 때 사용됩니다.
- useRef는 주로 다음과 같은 경우에 사용됩니다.
  - 이전 상태 값을 기억하고 싶을 때
  - setTimeout, setInterval 등의 함수에서 반환된 값을 기억하고 싶을 때
  - DOM 요소에 직접 접근해야 할 때

> useRef Hook은 상태 값의 변경을 추적하지 않으며, 값을 변경해도 컴포넌트를 다시 렌더링하지 않습니다. 