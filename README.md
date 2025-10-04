# 멘즈키(Menzuki) 웹사이트 프로젝트 계획서

## 🎯 프로젝트 개요
부산 소재 츠케멘 맛집 "멘즈키"의 브랜드 아이덴티티를 담은 소개 웹 페이지

**컨셉**: 모던하고 강렬한 미니멀리즘  
**슬로건**: "츠케멘은 '멘즈키' 입니다!"  
**서브 카피**: "명/실/상/부 부산 1등 츠케멘 전문점"  
**설립**: MENZUKI SINCE 2017  
**대표**: 멘즈키 오너셰프 김종원

---

## 📋 페이지 구조 개요

```
┌─────────────────────────────────────────┐
│  1. Hero Section                        │
│  - "츠케멘은 '멘즈키' 입니다!"           │
│  - 전체 화면 임팩트                      │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  2. Navigation Bar (Fixed)              │
│  - Home / Story / Signature / Menu      │
│  - Location / Reservation               │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  3. Brand Story Section                 │
│  ① 멘즈키, 면을 사랑하는 사람            │
│  ② 저희는 다릅니다 (일본 수련)           │
│  ③ 정성이 만든 맛 (장인정신)             │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  4. Signature Section                   │
│  [비법 육수] | [오리지널 전용면]         │
│  - 10시간 육수 | 면 장인 커스텀          │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  5. Menu Section                        │
│  [메뉴1] [메뉴2] [메뉴3]                │
│  - 그리드 레이아웃 메뉴 카드             │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  6. Location & Info Section             │
│  - 지도 + 매장 정보                      │
│  - 영업시간 / 연락처                     │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  7. Reservation CTA                     │
│  - 예약하기 버튼 (빨간색 강조)           │
└─────────────────────────────────────────┘
           ↓
┌─────────────────────────────────────────┐
│  8. Footer                              │
│  - 사업자 정보 / 소셜 미디어             │
└─────────────────────────────────────────┘
```

---

## 📁 1. 전체 폴더 구조 설계

```
menzuki/
│
├── index.html                      # 메인 HTML 파일
│
├── assets/                         # 정적 리소스
│   ├── images/                     # 이미지 파일
│   │   ├── hero/                   # 메인 히어로 이미지
│   │   │   └── tsukemen-hero.jpg   # 👉 ex/츠케멘 사진.jpg 사용
│   │   ├── menu/                   # 메뉴 사진
│   │   │   ├── tsukemen-classic.jpg # 👉 ex/츠케멘 사진.jpg 사용 가능
│   │   │   ├── tsukemen-spicy.jpg
│   │   │   └── tsukemen-special.jpg
│   │   ├── story/                  # 브랜드 스토리 이미지
│   │   │   ├── yasubei-chef.jpg    # 👉 ex/사장님 야스베 시절 사진.jpg
│   │   │   ├── yasubei-tsukemen.jpg # 👉 ex/야스베 신즈쿠점 츠메켄 사진.jpg
│   │   │   ├── interior-1.jpg      # 매장 인테리어 (추가 필요)
│   │   │   └── ingredients.jpg     # 신선한 재료들 (추가 필요)
│   │   ├── signature/              # 시그니처 섹션 이미지
│   │   │   ├── broth-detail.jpg    # 육수 클로즈업 (추가 필요)
│   │   │   └── noodles-detail.jpg  # 면 클로즈업 (추가 필요)
│   │   └── icons/                  # 아이콘 파일
│   │       ├── location.svg
│   │       ├── clock.svg
│   │       ├── phone.svg
│   │       ├── pot.svg             # 육수 아이콘
│   │       └── noodle.svg          # 면 아이콘
│   │
│   ├── videos/                     # 동영상 파일
│   │   └── gwangan-promo.mp4       # 👉 ex/멘즈키 광안 직영점 오픈 홍보 영상.mp4
│   │
│   └── fonts/                      # 웹 폰트 (필요시)
│       └── NotoSansKR/
│
├── css/                            # 스타일시트
│   ├── reset.css                   # CSS 리셋
│   ├── variables.css               # CSS 변수 (색상, 폰트 등)
│   ├── common.css                  # 공통 스타일
│   ├── components/                 # 컴포넌트별 스타일
│   │   ├── header.css
│   │   ├── footer.css
│   │   ├── button.css
│   │   ├── card.css
│   │   └── navigation.css
│   └── sections/                   # 섹션별 스타일
│       ├── hero.css
│       ├── story.css
│       ├── signature.css
│       ├── menu.css
│       └── location.css
│
└── js/                             # JavaScript 파일
    ├── main.js                     # 메인 진입점
    ├── modules/                    # 모듈화된 기능
    │   ├── navigation.js           # 네비게이션 기능
    │   ├── scroll.js               # 스크롤 애니메이션
    │   ├── imageLoader.js          # 이미지 지연 로딩
    │   └── map.js                  # 지도 API 연동
    └── utils/                      # 유틸리티 함수
        └── helpers.js              # 헬퍼 함수들
```

### 폴더별 역할

- **assets/**: 모든 정적 리소스를 관리하며, 이미지와 폰트를 카테고리별로 분류
  - **images/**: 이미지 리소스
  - **videos/**: 동영상 리소스 (홍보 영상)
  - **fonts/**: 웹 폰트
- **css/**: 모듈화된 스타일시트로 유지보수성 향상
  - **components/**: 재사용 가능한 UI 컴포넌트 스타일
  - **sections/**: 페이지 섹션별 고유 스타일
- **js/**: 기능별로 모듈화하여 코드 재사용성 및 테스트 용이성 확보

### 📸 제공된 실제 이미지 파일 매핑

| 제공된 파일 (ex/) | 사용 위치 | 용도 |
|------------------|----------|------|
| `츠케멘 사진.jpg` | Hero Section, Menu Section | 메인 비주얼, 메뉴 카드 |
| `사장님 야스베 시절 사진.jpg` | Brand Story Section | 야스베 수련 증명 사진 |
| `야스베 신즈쿠점 츠메켄 사진.jpg` | Brand Story Section | 정통 츠케멘 레퍼런스 |
| `멘즈키 광안 직영점 오픈 홍보 영상.mp4` | Hero Section (옵션) | 배경 영상 또는 Story Section |

---

## 📄 2. 페이지별 기능 명세

### 2.1 Hero Section (메인 화면)
**목적**: 첫 인상으로 방문자의 시선을 사로잡고 브랜드 정체성 전달

**기능**:
- 전체 화면(100vh) 고품질 츠케멘 이미지 배경
- 중앙 정렬된 메인 카피 텍스트 애니메이션 (fade-in)
- 스크롤 다운 인디케이터 (bounce 애니메이션)
- Parallax 스크롤 효과

**배경 이미지**:
- 📸 **사용 파일**: `ex/츠케멘 사진.jpg`
- 젓가락으로 면을 들어올린 임팩트 있는 비주얼
- 진한 육수, 차슈, 멘마가 보이는 완벽한 구도

**배경 영상 활용** ⭐ 선택됨
- 🎬 **사용 파일**: `ex/멘즈키 광안 직영점 오픈 홍보 영상.mp4`
- 자동 재생, 음소거, 무한 루프
- **모바일에서도 영상 재생** (풍부한 사용자 경험 우선)
- `playsinline` 속성으로 iOS Safari 지원
- Preload 최적화로 초기 로딩 개선

**표시 콘텐츠**:
- 메인 카피: "츠케멘은 '멘즈키' 입니다!"
- 서브 카피: "명/실/상/부 부산 1등 츠케멘 전문점"
- 설립 연도: "MENZUKI SINCE 2017"

**기술 요소**:
- CSS: `background-size: cover`, `position: fixed` (parallax)
- JS: Intersection Observer API (스크롤 감지)
- HTML5 `<video>` 태그 (배경 영상 옵션)

---

### 2.2 Navigation Bar
**목적**: 페이지 내 섹션 간 빠른 이동 제공

**기능**:
- 스크롤 시 헤더 배경 변화 (투명 → 불투명)
- 현재 섹션 하이라이트 표시
- 모바일 반응형 햄버거 메뉴
- 스무스 스크롤 앵커 링크

**메뉴 항목**:
- HOME (홈)
- STORY (브랜드 스토리)
- SIGNATURE (시그니처)
- MENU (메뉴)
- LOCATION (위치)
- RESERVATION (예약)

**기술 요소**:
- CSS: `position: sticky`, `backdrop-filter`
- JS: Scroll event listener, `scrollIntoView({ behavior: 'smooth' })`

---

### 2.3 Brand Story Section
**목적**: 멘즈키의 철학과 차별성 전달

**기능**:
- 좌우 분할 레이아웃 (텍스트 + 이미지)
- 스크롤 시 페이드인 애니메이션
- 매장 내부/셰프 이미지 갤러리 (2-3장)
- 3개의 서브 섹션으로 구성

**콘텐츠 구성**:

#### 섹션 1: 멘즈키의 탄생
- 헤딩: "멘즈키, 면을 사랑하는 사람"
- 본문: 
  * 멘즈키의 뜻: '면을 아주 좋아하는 사람'을 칭하는 일본어
  * 창업주 김종원 오너셰프가 바로 '멘즈키'
  * 츠케멘이라는 음식은 면을 즐기기에 정말 끝판왕
  * 쫄깃한 식감과 미끄러지듯 넘어가는 목넘김
  * 스프와 함께 입속에서 폭발하는 감칠맛의 향연

#### 섹션 2: 우리는 다릅니다
- 헤딩: "저희는 다릅니다"
- 본문:
  * 일본 야스베[신주쿠점, 아카사카점]에서 실제 수련한 정통 츠케멘 (국내 유일)
  * 10년간 일본 거주, 조예가 깊은 오너셰프
  * 요리사 도합 경력 20년의 모든 역량을 넣은 궁극의 한 그릇
- **이미지**: 
  * 📸 `ex/사장님 야스베 시절 사진.jpg` - 야스베 매장 앞 인증샷
  * 📸 `ex/야스베 신즈쿠점 츠메켄 사진.jpg` - 정통 츠케멘 레퍼런스

#### 섹션 3: 장인의 손길
- 헤딩: "정성이 만든 맛"
- 본문:
  * 오너셰프가 직접 엄선한 신선한 재료를 10시간 동안 끓인 비법 스프
  * 20년간 면만 만들어온 면 장인과 협업한 멘즈키 오리지널 커스텀 면
  * 매일 아침 직접 뽑은 라유(고추기름)와 장유(타레소스)
  * 원재료 수급부터 제조까지 전 과정을 직접 만든 차슈와 멘마
  * 시판제품을 일체 사용하지 않고 직접 정성껏 제조
- **이미지**: 조리 과정, 재료 클로즈업 (추가 촬영 권장)

**기술 요소**:
- CSS: Flexbox/Grid 레이아웃, `opacity` 애니메이션
- JS: Intersection Observer (viewport 진입 시 애니메이션)

---

### 2.4 Signature Section (시그니처 소개)
**목적**: 멘즈키만의 차별화된 핵심 요소 강조

**기능**:
- 2열 그리드 레이아웃 (비법 육수 / 오리지널 면)
- 각 요소별 아이콘 또는 이미지
- 스크롤 시 좌우에서 슬라이드 인 애니메이션

**콘텐츠 구성**:

#### 비법 육수
- 아이콘: 냄비 또는 육수 이미지
- 제목: "10시간의 비법 육수"
- 설명:
  * 실제 10년간 일본 거주하며 안 가본 츠케멘 전문점이 없을 정도로 조예가 깊은 오너셰프
  * 신주쿠와 아카사카 야스베 2곳에서 직접 장기간 수련 (국내 유일)
  * 요리사 도합 경력 20년의 모든 역량을 넣어 만든 궁극의 한 그릇
  * 오너셰프가 직접 엄선한 신선한 재료를 10시간 동안 끓여 만든 진한 비법 스프

#### 멘즈키 오리지널 전용면
- 아이콘: 면 또는 제면 이미지
- 제목: "면 장인의 커스텀 면"
- 설명:
  * "진료는 의사에게, 약은 약사에게, 면은 면 장인에게!"
  * 20년간 면만 만들어온 면 장인과 머리를 맞대어 장기간 고심
  * 스프와 완벽히 조화를 이룬 멘즈키만을 위한 커스텀 면
  * 쫄깃한 식감과 미끄러지듯 넘어가는 목넘김

**기술 요소**:
- CSS: Grid layout, `transform` 애니메이션
- JS: Intersection Observer (스크롤 트리거)

---

### 2.5 Menu Section
**목적**: 시각적으로 메뉴의 매력을 전달하고 식욕 자극

**기능**:
- 그리드 레이아웃 메뉴 카드 (3열)
- 각 카드: 음식 사진 + 메뉴명 + 간단한 설명 + 가격
- 호버 시 이미지 확대 효과 (`transform: scale(1.05)`)
- 빨간색 강조 테두리 애니메이션

**메뉴 구성 예시**:
- 클래식 츠케멘
- 매운 츠케멘
- 스페셜 츠케멘
- 사이드 메뉴

**이미지**:
- 📸 `ex/츠케멘 사진.jpg` - 대표 메뉴 이미지로 활용 가능
- 추가 촬영 권장: 각 메뉴별 개별 사진 (매운맛, 스페셜 등)

**기술 요소**:
- CSS: Grid layout, `transition`, `hover` 효과
- JS: 이미지 지연 로딩 (Lazy Loading)

---

### 2.6 Location & Info Section
**목적**: 방문 유도를 위한 필수 정보 제공

**기능**:
- 카카오맵/구글맵 API 임베드
- 주소, 전화번호, 영업시간 표시
- 아이콘 기반 정보 디스플레이
- 길찾기 버튼 (외부 지도 앱 연결)

**콘텐츠**:
- 주소: 부산시 [구체적 주소]
- 전화: 051-XXX-XXXX
- 영업시간: 11:00 - 21:00 (브레이크타임 15:00-17:00)
- 정기휴무: 매주 월요일

**기술 요소**:
- JS: 카카오맵 JavaScript API
- CSS: Flexbox 레이아웃

---

### 2.7 Reservation CTA Section
**목적**: 예약 전환율 극대화

**기능**:
- 눈에 띄는 빨간색 CTA 버튼
- 전화 예약 링크 (`tel:`) 또는 외부 예약 시스템 연결
- 호버 시 버튼 확대 및 그림자 효과

**기술 요소**:
- CSS: `:hover` 애니메이션, `box-shadow`
- HTML: `<a href="tel:051XXXXXXX">`

---

### 2.8 Footer
**목적**: 법적 정보 및 소셜 미디어 연결

**기능**:
- 사업자 정보 (상호, 대표자명: 김종원, 사업자번호)
- 소셜 미디어 링크 (Instagram, Facebook)
- Copyright 표시 "© 2017 MENZUKI. All rights reserved."

**기술 요소**:
- CSS: Flexbox, 작은 폰트 크기

---

## 🗓️ 3. 개발 단계별 계획

### Phase 1: 기초 설정 및 구조 (1일차)
- [x] 프로젝트 폴더 구조 생성
- [ ] HTML 기본 구조 작성 (semantic tags: `<header>`, `<section>`, `<footer>`)
- [ ] CSS reset 및 변수 정의 (colors, fonts, spacing)
- [ ] 폰트 로드 (Google Fonts: Noto Sans KR, Montserrat 등)
- [ ] Git 저장소 초기화

---

### Phase 2: 공통 컴포넌트 개발 (2일차)
- [ ] Navigation Bar 구현
  - HTML 마크업
  - 기본 스타일링
  - 햄버거 메뉴 (모바일)
  - 스크롤 시 배경 변화 JS
- [ ] Button 컴포넌트 스타일
- [ ] Footer 구현

---

### Phase 3: 메인 콘텐츠 섹션 개발 (3-4일차)
- [ ] Hero Section
  - 배경 이미지 설정
  - 메인/서브 카피 텍스트 애니메이션
  - Parallax 효과
- [ ] Brand Story Section (3개 서브 섹션)
  - 멘즈키의 탄생 섹션
  - 우리는 다릅니다 섹션
  - 장인의 손길 섹션
  - 레이아웃 구성 및 스크롤 애니메이션
- [ ] Signature Section
  - 2열 그리드 (비법 육수 / 오리지널 면)
  - 아이콘 디자인 또는 이미지 선정
  - 슬라이드 인 애니메이션
- [ ] Menu Section
  - 그리드 레이아웃
  - 메뉴 카드 컴포넌트
  - 호버 효과

---

### Phase 4: 기능 구현 (5일차)
- [ ] 스무스 스크롤 구현
- [ ] Intersection Observer 설정 (애니메이션 트리거)
- [ ] 이미지 지연 로딩
- [ ] 카카오맵 API 연동
- [ ] 현재 섹션 하이라이트 기능

---

### Phase 5: 반응형 디자인 (6일차)
- [ ] 모바일 (< 768px) 최적화
- [ ] 태블릿 (768px - 1024px) 최적화
- [ ] 데스크톱 (> 1024px) 최적화
- [ ] 이미지 최적화 (srcset, WebP 포맷)

---

### Phase 6: 테스트 및 최적화 (7일차)
- [ ] 크로스 브라우저 테스트 (Chrome, Safari, Firefox, Edge)
- [ ] 성능 최적화
  - 이미지 압축
  - CSS/JS 미니파이
  - 불필요한 코드 제거
- [ ] SEO 최적화
  - meta tags 설정
  - Open Graph 태그
  - Schema.org 마크업
- [ ] 접근성 검사 (WCAG 2.1)

---

### Phase 7: 배포 (8일차)
- [ ] 호스팅 플랫폼 선택 (GitHub Pages, Netlify, Vercel 등)
- [ ] 도메인 연결 (선택사항)
- [ ] SSL 인증서 설정
- [ ] 최종 검수

---

## 🧩 4. 공통 컴포넌트 설계

### 4.1 Header Component
```
구조:
├── Logo (좌측 상단) - "MENZUKI" 또는 로고 이미지
├── Navigation Menu (우측)
│   ├── Home
│   ├── Story
│   ├── Signature (새 메뉴)
│   ├── Menu
│   ├── Location
│   └── Reservation (빨간색 강조)
└── Hamburger Menu Icon (모바일)

스타일 특징:
- 초기: 투명 배경
- 스크롤 후: 검은색 배경 (opacity: 0.95)
- Position: fixed (상단 고정)
- z-index: 1000
- "MENZUKI" 텍스트 로고 (Montserrat 폰트, 굵게)
```

---

### 4.2 Navigation Component
```
데스크톱:
- Horizontal flexbox
- 흰색 텍스트
- 호버 시: 빨간색 밑줄 애니메이션

모바일:
- 햄버거 아이콘 클릭 → 전체 화면 오버레이 메뉴
- Slide-in 애니메이션
- 각 메뉴 항목 stagger 애니메이션
```

---

### 4.3 Button Component
```
Primary Button (CTA):
- 배경: 빨간색 (#D32F2F)
- 텍스트: 흰색
- Padding: 16px 32px
- Border-radius: 4px
- 호버: 살짝 확대 + 그림자 강화
- 트랜지션: 0.3s ease

Secondary Button:
- 배경: 투명
- 테두리: 2px 흰색
- 텍스트: 흰색
- 호버: 배경 흰색, 텍스트 검은색
```

---

### 4.4 Card Component (메뉴 카드)
```
구조:
├── Image Container
│   └── Menu Image
├── Card Content
│   ├── Menu Name (H3)
│   ├── Description (P)
│   └── Price (Strong)

스타일:
- 배경: 진한 네이비 (#1A1A2E)
- 테두리: 1px solid rgba(255,255,255,0.1)
- Border-radius: 8px
- 호버: 이미지 확대, 빨간색 테두리
- 애니메이션: transform, box-shadow
```

---

### 4.5 Section Container
```
공통 구조:
- Max-width: 1200px
- Margin: 0 auto
- Padding: 80px 20px
- 배경: 검은색 또는 그라데이션

반응형:
- Mobile: padding 40px 16px
```

---

### 4.6 Footer Component
```
구조:
├── Info Section
│   ├── Business Info
│   └── Contact
├── Social Links
│   ├── Instagram Icon
│   └── Facebook Icon
└── Copyright

스타일:
- 배경: 완전 검은색 (#000000)
- 텍스트: 회색 (rgba(255,255,255,0.6))
- Flexbox 레이아웃
- Border-top: 1px solid rgba(255,255,255,0.1)
```

---

## 🎨 5. 재사용 가능한 CSS 클래스 설계

### 5.1 Color Utility Classes
```css
.bg-dark { background-color: #000000; }
.bg-navy { background-color: #0F3460; }
.bg-red { background-color: #D32F2F; }
.text-white { color: #FFFFFF; }
.text-gray { color: rgba(255, 255, 255, 0.7); }
.text-red { color: #D32F2F; }
```

---

### 5.2 Layout Utility Classes
```css
.container { max-width: 1200px; margin: 0 auto; padding: 0 20px; }
.section { padding: 80px 0; }
.flex-center { display: flex; justify-content: center; align-items: center; }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 30px; }
```

---

### 5.3 Typography Classes
```css
.heading-xl { font-size: 56px; font-weight: 700; line-height: 1.2; }
.heading-lg { font-size: 42px; font-weight: 700; }
.heading-md { font-size: 32px; font-weight: 600; }
.body-lg { font-size: 18px; line-height: 1.6; }
.body-md { font-size: 16px; line-height: 1.5; }
```

---

### 5.4 Spacing Classes
```css
.mt-1 { margin-top: 8px; }
.mt-2 { margin-top: 16px; }
.mt-3 { margin-top: 24px; }
.mb-1 { margin-bottom: 8px; }
.pb-1 { padding-bottom: 8px; }
/* ... (더 많은 spacing 클래스) */
```

---

### 5.5 Animation Classes
```css
.fade-in { animation: fadeIn 1s ease-in; }
.slide-up { animation: slideUp 0.6s ease-out; }
.scale-hover { transition: transform 0.3s; }
.scale-hover:hover { transform: scale(1.05); }
```

---

### 5.6 Button Classes
```css
.btn { padding: 16px 32px; border-radius: 4px; transition: all 0.3s; cursor: pointer; }
.btn-primary { background: #D32F2F; color: white; }
.btn-secondary { background: transparent; border: 2px solid white; color: white; }
.btn-large { padding: 20px 40px; font-size: 18px; }
```

---

## ⚙️ 6. JavaScript 모듈화 계획

### 6.1 main.js (진입점)
```javascript
역할:
- 모든 모듈을 import하고 초기화
- DOM 로드 완료 시 실행
- 전역 이벤트 리스너 설정

예시 구조:
import Navigation from './modules/navigation.js';
import ScrollAnimations from './modules/scroll.js';
import ImageLoader from './modules/imageLoader.js';
import MapHandler from './modules/map.js';

document.addEventListener('DOMContentLoaded', () => {
  Navigation.init();
  ScrollAnimations.init();
  ImageLoader.init();
  MapHandler.init();
});
```

---

### 6.2 modules/navigation.js
```javascript
기능:
- 햄버거 메뉴 토글
- 스크롤 시 헤더 배경 변경
- 현재 섹션 하이라이트
- 스무스 스크롤 앵커 링크

메서드:
- init(): 이벤트 리스너 등록
- toggleMenu(): 모바일 메뉴 열기/닫기
- handleScroll(): 스크롤 이벤트 처리
- highlightCurrentSection(): 현재 섹션 감지
- smoothScroll(target): 특정 섹션으로 스무스 스크롤
```

---

### 6.3 modules/scroll.js
```javascript
기능:
- Intersection Observer를 사용한 스크롤 애니메이션
- 요소가 viewport에 진입할 때 애니메이션 트리거
- Parallax 효과 (Hero Section)

메서드:
- init(): Observer 설정
- observeElements(selector): 관찰할 요소 등록
- handleIntersection(entries): 교차 시 콜백
- parallaxEffect(): Parallax 스크롤 계산
```

---

### 6.4 modules/imageLoader.js
```javascript
기능:
- 이미지 지연 로딩 (Lazy Loading)
- 성능 최적화
- 로딩 placeholder 처리

메서드:
- init(): IntersectionObserver 설정
- loadImage(img): 이미지 로드 실행
- handleImageError(img): 이미지 로드 실패 처리
```

---

### 6.5 modules/map.js
```javascript
기능:
- 카카오맵 또는 구글맵 API 초기화
- 마커 표시
- 정보 창 표시
- 길찾기 버튼 연결

메서드:
- init(): 지도 초기화
- setMarker(lat, lng): 마커 설정
- showInfoWindow(): 정보 창 표시
- getDirections(): 길찾기 외부 앱 연결
```

---

### 6.6 utils/helpers.js
```javascript
기능:
- 재사용 가능한 유틸리티 함수 모음

함수 예시:
- debounce(func, delay): 디바운스 함수
- throttle(func, limit): 쓰로틀 함수
- getElementOffset(el): 요소의 offset 계산
- isElementInViewport(el): viewport 내 존재 여부
- formatPhoneNumber(number): 전화번호 포맷팅
```

---

## 🎨 디자인 시스템

### Color Palette
```
Primary Colors:
- Black: #000000 (주 배경)
- Navy: #0F3460 (보조 배경)
- Red: #D32F2F (CTA, 강조)

Text Colors:
- White: #FFFFFF (주 텍스트)
- Light Gray: rgba(255, 255, 255, 0.7) (보조 텍스트)
- Dark Gray: rgba(255, 255, 255, 0.5) (비활성)

Accent:
- Bright Red: #FF5252 (호버 효과)
```

---

### Typography
```
Primary Font: 'Noto Sans KR', sans-serif (한글)
Secondary Font: 'Montserrat', sans-serif (영문, 숫자)

Font Sizes:
- Display: 56px (메인 슬로건)
- H1: 42px (섹션 타이틀)
- H2: 32px (서브 타이틀)
- H3: 24px (카드 제목)
- Body: 16px (본문)
- Small: 14px (캡션)

Font Weights:
- Bold: 700 (헤딩)
- Semi-bold: 600 (강조)
- Regular: 400 (본문)
```

---

### Spacing System
```
Base unit: 8px

Scale:
- xs: 8px
- sm: 16px
- md: 24px
- lg: 32px
- xl: 48px
- 2xl: 64px
- 3xl: 80px
```

---

### Border Radius
```
- Small: 4px (버튼)
- Medium: 8px (카드)
- Large: 16px (큰 컨테이너)
```

---

## 📱 반응형 브레이크포인트

```css
/* Mobile First Approach */

/* Extra Small (모바일) */
Default: < 768px

/* Small (태블릿) */
@media (min-width: 768px) { ... }

/* Medium (작은 데스크톱) */
@media (min-width: 1024px) { ... }

/* Large (큰 데스크톱) */
@media (min-width: 1440px) { ... }
```

---

## 🚀 성능 최적화 계획

### 이미지 최적화
- WebP 포맷 사용 (fallback으로 JPEG/PNG)
- Lazy Loading 구현
- 적절한 해상도 제공 (srcset 활용)
- 이미지 압축 (TinyPNG, ImageOptim)

### CSS 최적화
- Critical CSS 인라인 삽입
- 미사용 CSS 제거
- CSS 파일 미니파이

### JavaScript 최적화
- 비동기 로딩 (`defer`, `async`)
- 코드 스플리팅
- 미니파이 및 압축

### 로딩 성능
- 폰트 최적화 (font-display: swap)
- DNS Prefetch
- Preload 중요 리소스

---

## ♿ 접근성 (Accessibility) 고려사항

- Semantic HTML 사용 (`<nav>`, `<main>`, `<article>` 등)
- ARIA 레이블 추가
- 키보드 네비게이션 지원
- 충분한 색상 대비 (WCAG AA 기준)
- Alt 텍스트 작성
- Focus 스타일 명확히 표시

---

## 🔍 SEO 최적화

### Meta Tags
```html
<title>멘즈키 | 부산 츠케멘 맛집</title>
<meta name="description" content="부산에서 즐기는 정통 츠케멘. 멘즈키는 면의 자부심을 지킵니다.">
<meta name="keywords" content="츠케멘, 부산 맛집, 일본 라멘, 멘즈키">
```

### Open Graph
```html
<meta property="og:title" content="멘즈키 | 부산 츠케멘 맛집">
<meta property="og:description" content="부산에서 즐기는 정통 츠케멘">
<meta property="og:image" content="[츠케멘 대표 이미지 URL]">
<meta property="og:type" content="website">
```

### Structured Data (Schema.org)
- Restaurant schema 마크업
- LocalBusiness schema 마크업

---

## 📊 추후 개선 사항 (선택)

### Phase 2 기능 (추가 개발)
- [ ] 온라인 예약 시스템 연동
- [ ] 고객 리뷰 섹션
- [ ] 다국어 지원 (영어, 일본어)
- [ ] 다크모드 토글 (이미 다크 테마지만 라이트 모드 옵션)
- [ ] 로딩 애니메이션
- [ ] 이벤트/공지사항 섹션
- [ ] 메뉴 상세 모달 팝업
- [ ] 이미지 갤러리 라이트박스

### 분석 및 마케팅
- [ ] Google Analytics 연동
- [ ] Facebook Pixel
- [ ] 네이버 웹마스터 도구

---

## 🛠️ 개발 환경 설정

### 필수 도구
- 코드 에디터: VS Code
- 브라우저: Chrome (DevTools)
- 버전 관리: Git

### VS Code 확장 프로그램 권장
- Live Server
- Prettier
- ESLint
- Auto Rename Tag
- CSS Peek

### 브라우저 확장 프로그램
- Lighthouse (성능 측정)
- WAVE (접근성 검사)

---

## 📝 커밋 메시지 컨벤션

```
feat: 새로운 기능 추가
fix: 버그 수정
style: 스타일링 변경
refactor: 코드 리팩토링
docs: 문서 수정
test: 테스트 추가/수정
chore: 빌드 작업, 패키지 매니저 설정 등
```

---

## 📄 실제 콘텐츠 문구 정리

### Hero Section
```
메인 카피: "츠케멘은 '멘즈키' 입니다!"
서브 카피: "명/실/상/부 부산 1등 츠케멘 전문점"
설립 연도: "MENZUKI SINCE 2017"
```

### Brand Story Section

#### 섹션 1: 멘즈키, 면을 사랑하는 사람
```
멘즈키의 뜻: '면을 아주 좋아하는 사람'을 칭하는 일본어입니다.

창업주인 제가 바로 '멘즈키' 이기에 가게 이름을 멘즈키로 짓게 되었습니다.

제가 생각하기에 츠케멘이라는 음식은 면을 즐기기에 정말 끝판왕이 아닐까 합니다.

쫄깃한 식감과 미끄러지듯 넘어가는 목넘김! 
스프와 함께 입속에서 폭발하는 감칠맛의 향연! 
그 감동을 한번 느껴보세요!
```

#### 섹션 2: 저희는 다릅니다
```
일본 야스베[신주쿠점, 아카사카점]에서 실제로 수련하여 온 
찐 정통 츠케멘입니다.

실제 10년간 일본에 거주하며 안 가본 츠케멘 전문점이 없을 정도로 
조예가 깊으며 신주쿠와 아카사카 야스베 2곳에서 직접 장기간 수련한 
오너 셰프(국내 유일)가 요리사 도합 경력 20년의 모든 역량을 넣어 
만든 궁극의 한 그릇입니다.
```

#### 섹션 3: 정성이 만든 맛
```
오너셰프가 직접 엄선한 신선한 재료를 10시간 동안 끓여 
만들어낸 진한 비법 스프

20년간 면만 만들어 오신 면 장인과 머리를 맞대어 
고심 끝에 탄생한 멘즈키만의 오리지널 커스텀 면을 
사용하여 정성껏 만들었습니다.

매일 아침 직접 뽑은 라유[고추기름]와 장유[타레소스]
원재료 수급부터 제조까지 전 과정을 직접 만든 차슈와 멘마
시판제품을 일체 사용하지 않고 직접 정성껏 만들었습니다.
```

### Signature Section

#### 10시간의 비법 육수
```
제목: 비법 육수

실제 10년간 일본에 거주하며 안 가본 츠케멘 전문점이 없을 정도로 
조예가 깊으며 신주쿠와 아카사카 야스베, 2곳에서 직접 장기간 수련한 
오너 셰프(국내 유일)가 요리사 도합 경력 20년의 모든 역량을 넣어 
만든 궁극의 한 그릇입니다.

오너셰프가 직접 엄선한 신선한 재료를 10시간 동안 끓여 
만들어낸 진한 비법 스프
```

#### 면 장인의 커스텀 면
```
제목: 멘즈키 오리지널 전용면

진료는 의사에게 약은 약사에게! 
저희 면은 면만 수십 년간 고집해온 면 장인과 머리를 맞대어 
장기간 고심한 끝에 스프와 완벽히 조화를 이룬 
멘즈키만을 위한 커스텀 면을 생산하여 
손님 여러분께 제공하고 있습니다.
```

### Footer
```
대표: 김종원
상호: 멘즈키 (MENZUKI)
설립: 2017년
Copyright: © 2017 MENZUKI. All rights reserved.
```

---

## 📞 문의 및 협업

프로젝트 관련 문의사항이나 개선 제안은 Issues를 통해 남겨주세요.

---

**프로젝트 시작일**: 2025년 10월 4일  
**예상 완료일**: 2025년 10월 11일 (1주일)  
**작성자**: AI Assistant  
**버전**: 2.0.0 (실제 콘텐츠 반영)

---

## 📦 현재 보유 리소스 정리

### ✅ 사용 가능한 파일 (ex/ 폴더)

| 파일명 | 크기 | 용도 | 사용 섹션 |
|--------|------|------|----------|
| `츠케멘 사진.jpg` | 114KB | 메인 비주얼, 메뉴 이미지 | Hero, Menu |
| `사장님 야스베 시절 사진.jpg` | 120KB | 야스베 수련 증명 | Brand Story (섹션 2) |
| `야스베 신즈쿠점 츠메켄 사진.jpg` | 125KB | 정통 츠케멘 레퍼런스 | Brand Story (섹션 2) |
| `멘즈키 광안 직영점 오픈 홍보 영상.mp4` | 8.0MB | 배경 영상 (옵션) | Hero (배경 영상) |

### 📌 추가 촬영 권장 목록

개발 시작 전 또는 진행 중 추가하면 완성도를 높일 수 있는 이미지:

**우선순위 높음**:
1. 매장 내부 인테리어 사진 (1-2장)
2. 매장 외관 사진
3. 각 메뉴별 개별 음식 사진 (매운 츠케멘, 스페셜 츠케멘 등)

**우선순위 중간**:
4. 조리 과정 사진 (육수 끓이는 모습, 면 만드는 과정 등)
5. 재료 클로즈업 (신선한 재료들)
6. 차슈, 멘마 등 토핑 개별 사진

**우선순위 낮음** (있으면 좋음):
7. 오너셰프 김종원님 프로필 사진
8. 면 장인과의 협업 사진
9. 라유(고추기름), 장유(타레소스) 제조 과정

**대체 방안**:
- 부족한 이미지는 개발 완료 후 점진적으로 교체 가능
- 초기에는 제공된 3장의 이미지를 최대한 활용하여 레이아웃 완성
- Placeholder 이미지 또는 색상 블록으로 임시 처리

---

## ✅ 다음 단계

이 계획서를 기반으로 개발을 시작하려면:

1. **폴더 구조 생성**: 위의 폴더 구조대로 디렉토리를 생성합니다
2. **이미지 최적화 및 배치**: 
   - `ex/` 폴더의 이미지를 `assets/images/` 해당 위치로 복사
   - 이미지 최적화 (WebP 변환, 압축)
3. **HTML 구조 작성**: 시맨틱 HTML로 기본 뼈대를 만듭니다
4. **CSS 변수 설정**: variables.css에 색상, 폰트 등을 정의합니다
5. **섹션별 개발**: Hero → Navigation → Story → Signature → Menu → Location 순서로 진행합니다

### 🎬 개발 시작 옵션

**옵션 A: 이미지만 사용** (빠른 개발)
- 3장의 이미지로 레이아웃 완성
- 홍보 영상은 추후 추가

**옵션 B: 영상 포함** (풍부한 경험)
- Hero Section에 배경 영상 적용
- 모바일 최적화 필요

**권장**: 옵션 A로 시작 → 완성 후 옵션 B로 업그레이드

---

준비가 되셨다면 개발을 시작하겠습니다! 🚀

