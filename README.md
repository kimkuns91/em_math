# 이엠수학 아임웹 카드 UI 프로젝트

아임웹 메인 화면에 들어가는 2행 4열 카드 네비게이션 UI를 관리하기 위한 **순수 HTML/CSS 코드 프로젝트**입니다.  
빌드 도구나 패키지 의존성 없이, 완성된 코드만 아임웹에 복사·붙여넣기 해서 사용하는 구조입니다.

## 📁 현재 구조

```text
emmath/
├── card.html          # 단일 카드 디자인용 미리보기 페이지
└── emmath-cards.html  # 아임웹에 붙여넣을 최종 카드 그리드 코드
```

### `card.html`

- 카드 1개만 있는 **디자인 전용 페이지**입니다.
- 폰트, 색상, 여백, 아이콘 크기 등을 조정해볼 때 이 파일만 열어서 작업하면 됩니다.
- 구조(요약):

```html
<a class="emmath-card">
  <div class="emmath-card__content">
    <div class="emmath-card__header-row">
      <div class="emmath-card__subtitle">ACADEMY INTRODUCTION</div>
      <h3 class="emmath-card__title">학원 소개</h3>
      <div class="emmath-card__icon"></div>
    </div>
    <div class="emmath-card__link">자세히보기 &gt;</div>
  </div>
</a>
```

### `emmath-cards.html`

- 실제 아임웹에 붙여넣을 **최종 코드**입니다.
- 8개의 카드를 2열 그리드로 배치하고, 각 카드가 `card.html`과 동일한 디자인을 따릅니다.
- 상단 `<style>` 안에 카드 스타일과 그리드 레이아웃이 모두 포함되어 있어, **이 파일 하나만 복사하면 동작**합니다.

## 🚀 아임웹에 적용하기

1. `emmath-cards.html` 파일을 엽니다.
2. 파일 **전체 내용을 복사**합니다.
3. 아임웹 관리자 페이지 접속 → 해당 페이지 편집.
4. `HTML` 위젯 추가 (또는 디자인 설정 > 공통 코드 영역).
5. 복사한 코드를 그대로 붙여넣고 저장합니다.

> 아이콘 자리에 실제 이미지가 필요하면, `div.emmath-card__icon` 안에 `<img>` 태그를 넣거나, `background-image`를 사용해 적용하면 됩니다.

## 🎨 커스터마이징 가이드

- **텍스트 변경**:  
  `emmath-cards.html` 하단 HTML에서 `학원 소개`, `입학안내` 등 텍스트만 수정하면 됩니다.
- **링크 변경**:  
  각 카드의 `href="#academy"` 부분을 원하는 URL로 교체합니다.
- **색상/폰트/간격 조정**:  
  `card.html`에서 먼저 스타일을 조정해보고, 만족스러우면 동일한 CSS를 `emmath-cards.html`의 `<style>`에 반영합니다.
- **레이아웃 조정**:  
  `grid-template-columns: repeat(2, minmax(0, 1fr));` 값을 변경하면 카드 열 수를 조절할 수 있습니다.

## ℹ️ 참고

- 이 프로젝트는 **아임웹 내에서만 사용되는 정적 코드**를 관리하기 위한 용도입니다.
- 빌드/배포 과정이 없으므로 `npm`, `Vite` 등은 전혀 필요하지 않습니다.
- 버전 관리를 위해 이 저장소에서만 코드를 수정하고, 변경이 생길 때마다 아임웹에 다시 붙여넣는 방식을 추천합니다.
