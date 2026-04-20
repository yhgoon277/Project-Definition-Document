# visualizer-skill

SKT Next Channel 과제정의서 통합 시각화 + 과제별 mobile 프로토타입 프로젝트.

## 세션 시작 시 필독

`.claude/HANDOFF.md` 를 먼저 읽고 **직전 세션의 맥락**(미결·진행중·결정 대기)을 파악한다. 맥락이 작업 방향에 영향을 준다고 판단되면 첫 응답에 한 줄로 언급.

## 영역별 디자인 시스템 (영역 혼용 금지)

| 영역 | 파일 | 규격 |
|------|------|------|
| 메인 랜딩 + 상세페이지 | `index.html` | visualize skill 토큰 (`--bg`, `--surface`, `--text`, `--accent`...) + `.theme-dark`/`.theme-light` |
| 프로토타입 (모바일 mockup) | `prototypes/*.html` | Wanted Montage (WDS) — `prototypes/README.md` 참고, 공용 토큰 `prototypes/_wds-tokens.css` |

두 시스템은 iframe 경계로 격리되어 있음. 파일 경로가 `prototypes/` 로 시작하면 WDS, 아니면 visualize skill 규격.

## 세션 종료 전

사용자가 `/handoff` 를 입력하면 `.claude/HANDOFF.md` 를 덮어쓴다. 규칙은 `.claude/commands/handoff.md` 참고.

## 관련 문서

- `prototypes/README.md` — WDS 작업 체크리스트
- `~/.claude/plans/*.md` — 최근 계획 (plan 모드 산출물)
- 사용자 레벨 memory — 영구 규칙 (feedback/project/reference/user 타입)
