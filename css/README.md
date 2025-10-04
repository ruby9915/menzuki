# CSS 구조 및 수정 사항 안내

이 문서는 `menzuki` 프로젝트의 CSS 구조와 주요 수정 사항에 대해 설명합니다.

## 레이아웃 수정: Hero 섹션 콘텐츠 정렬

### 문제점

기존에는 `.scroll-indicator` 요소의 위치를 `position: absolute`와 고정된 `bottom` 픽셀 값을 사용하여 조정했습니다. 이 방식은 다음과 같은 문제를 야기했습니다.

-   **반응형 문제**: 화면 크기나 해상도가 달라지면 텍스트의 높이가 유동적으로 변하기 때문에, 고정 픽셀 값으로는 `.hero-tagline`과의 일관된 간격을 유지할 수 없습니다. 이로 인해 요소가 겹치거나 너무 멀어지는 문제가 발생합니다.
-   **유지보수의 어려움**: 텍스트 내용이 변경될 때마다 CSS의 픽셀 값을 다시 계산하고 수정해야 하는 번거로움이 있습니다.

### 해결 방안: Flexbox를 이용한 동적 레이아웃

이 문제를 해결하기 위해 `.hero-content`에 Flexbox 레이아웃을 적용하여 내부 요소들이 동적으로 정렬되도록 수정합니다.

#### 주요 변경 사항 (`css/sections/hero.css`)

1.  **`.hero-content`**:
    -   `display: flex`
    -   `flex-direction: column` (수직 정렬)
    -   `align-items: center` (가운데 정렬)
    -   `justify-content: center` (수직 중앙 정렬)

2.  **`.scroll-indicator`**:
    -   `position: absolute` 및 관련 속성(`bottom`, `left`, `transform`)을 제거합니다. 이제 Flexbox의 흐름에 따라 자동으로 위치가 결정됩니다.

3.  **`.hero-tagline`**:
    -   `margin-bottom: 20px;`을 추가하여 아래 요소인 `.scroll-indicator`와의 간격을 항상 20px로 유지합니다.

### 기대 효과

-   **완벽한 반응형**: 디스플레이 크기에 상관없이 항상 일관된 레이아웃을 유지합니다.
-   **향상된 유지보수성**: 코드 구조가 더 직관적이 되고, 향후 디자인 변경이 용이해집니다.
-   **안정성**: 다른 요소에 영향을 주지 않고 독립적인 레이아웃을 구성하여 예기치 않은 버그를 방지합니다.
