# prototypes/

이 폴더는 **Wanted Montage (WDS) 디자인 시스템** 전용 작업 영역입니다.

## 왜 별도 규격인가

이 프로젝트는 두 개의 디자인 시스템을 **영역별로 분리**해서 공존시키고 있습니다.

| 영역 | 파일 | 디자인 시스템 |
|------|------|--------------|
| 메인 랜딩 + 상세페이지 | `../index.html` | visualize skill 규격 |
| 모바일 mockup, AS-IS/TO-BE 비교 화면 | `prototypes/*.html` | **Wanted Montage (WDS)** |

두 시스템은 **iframe 경계로 격리**되어 CSS가 서로 침범하지 않습니다. 상세페이지가 프로토타입을 iframe으로 임베드하므로, 이 폴더 안에서는 WDS 규칙만 신경쓰면 됩니다.

## 작업 규칙 (이 폴더 안)

### 반드시 지킬 것
- **폰트**: Wanted Sans (display) + Pretendard (base) — 상단 `@import` 유지
- **토큰 네이밍**: `--primary-*`, `--label-*`, `--background-*-*`, `--line-*-*`, `--fill-*`, `--fs-*`, `--lh-*`, `--radius-*`, `--space-*`, `--shadow-*` (WDS 컨벤션)
- **컴포넌트**: Button/Card/Badge 등 primitive는 `4-billing.html` 상단 React 컴포넌트 정의 재사용
- **뷰포트**: 모바일 375×812 기본

### 절대 하지 말 것
- visualize skill 토큰(`--bg`, `--surface`, `--accent`...)을 이 폴더 파일에 쓰지 않기 — 이름이 겹쳐 보여도 규격이 다름
- `.theme-dark`/`.theme-light` 클래스 기반 토글 쓰지 않기 — WDS는 `[data-theme="dark"]` 속성 기반
- `index.html`의 스타일을 복사해 오지 않기

## 메인 `index.html` 영역 규칙

반대로 **이 폴더 밖(`../index.html`)** 작업은 **visualize skill 규격** 따릅니다:
- 필수 토큰 11개: `--bg`, `--surface`, `--surface-hover`, `--border`, `--text`, `--text-secondary`, `--accent`, `--accent-secondary`, `--positive`, `--negative`, `--warning`
- 테마 클래스: `.theme-dark`, `.theme-light`
- 유틸리티 메뉴, Chart.js, html-to-image 등 skill 요구사항

## 파일 구조

```
prototypes/
├── README.md           ← 이 문서
├── _wds-tokens.css     ← (Phase 2에서 생성) 공용 WDS 토큰
└── 4-billing.html      ← 과제 #4 요금 납부 AS-IS/TO-BE
                         (향후 5-*.html, 6-*.html... 동일 규격)
```

## 신규 프로토타입 추가 시 체크리스트

1. 파일명: `{과제번호}-{슬러그}.html` (예: `5-orders.html`)
2. 상단에 `@import url("./_wds-tokens.css");` (Phase 2 이후)
3. Wanted 폰트 import 유지
4. 뷰포트 375×812 고정 프레임 사용
5. AS-IS 화면은 `--coolNeutral-*` 톤다운, TO-BE 화면은 `--primary-normal` 강조
