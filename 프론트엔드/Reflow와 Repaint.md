## Reflow와 Repaint

### 공통점
- Reflow와 Repaint는 브라우저에서 HTML 요소들의 변화가 일어났을 때 발생하는 과정

### 차이점
- Reflow는 렌더 트리를 다시 계산하여 레이아웃을 만드는 과정을 말합니다. 새로운 요소가 추가되거나 기존 요소의 위치나 크기가 변경되었을 때 발생하며, 브라우저는 전체 문서의 레이아웃을 다시 계산하여 화면을 업데이트합니다. Reflow는 비용이 많이 들어서 성능 저하를 일으키는 원인 중 하나입니다.

- Repaint는 렌더링된 요소의 스타일 변경 등이 일어났을 때 해당 요소를 다시 그리는 과정을 말합니다. 즉, 레이아웃은 변경되지 않고 색상 등의 시각적인 스타일만 변경된 경우에 발생합니다. Reflow보다는 비용이 적지만, 여러 번 발생하면 성능에 영향을 줄 수 있습니다.

> 따라서 웹 개발자는 Reflow와 Repaint를 최소화하는 방법을 고려해야 합니다. 예를 들어, 요소를 추가하거나 스타일을 변경할 때는 가능한 한 배치나 스타일 변경을 일괄적으로 처리하고, 요소의 크기나 위치 등을 변경할 때는 CSS의 transform 속성을 활용하는 것이 좋습니다.
