# papig.dev — 지원/마케팅 사이트

papig(개발자 papig-dev)의 앱 지원·마케팅용 GitHub Pages 사이트입니다. 커스텀 도메인 `papig.dev`, Jekyll `jekyll-theme-hacker`(다크 터미널 + 그린 액센트 #b5e853) 테마.

## 구조

- `index.md` — 홈. 상단에 앱 카드 그리드(`.app-grid`), 이어서 kmong 활동.
- `<app>/index.md` + `<app>/privacy.md` — 앱별 고객지원 / 개인정보처리방침 (permalink `/<app>/`, `/<app>/privacy/`).
- `assets/css/style.scss` — 테마 import + 앱 카드 CSS(`.app-card`, `.app-icon img` 등). 2열 / 640px 이하 1열 반응형, JS 불필요.
- `assets/images/<app>-icon.*` — 홈 카드용 앱 아이콘(512px). App Store 아트워크 또는 Xcode 에셋에서 추출.
- 앱 아이콘은 이모지가 아니라 **실제 앱 아이콘**을 사용한다.

## 앱 목록 (설명의 소스 오브 트루스)

카드 설명이나 지원 페이지 문구를 바꿀 때는 아래 "핵심"을 기준으로 한다. 추측으로 기능을 지어내지 말 것. 각 앱의 실제 프로젝트가 `~/dev/`에 있으니 불확실하면 그쪽 README/CLAUDE.md/스토어 문구를 확인한다.

| 앱 | 상태 | 프로젝트 | 아이콘 | 지원 경로 |
|----|------|----------|--------|-----------|
| Riffle | 출시 | `~/dev/riffle_v3` | `riffle-icon.jpg` | `/riffle/` |
| 지출달력 (ExpenseCal) | 출시 | `~/dev/ExpenseCal` | `expensecal-icon.jpg` | `/expensecal/` |
| KeepStreak | 준비중 | `~/dev/KeepStreak` | `keepstreak-icon.png` | `/keepstreak` |
| 차곡로그 (Chagok) | 준비중 | `~/dev/carlife` | `chagoklog-icon.png` | `/chagoklog/` |

### Riffle
- **핵심**: 곡을 재생하기 **전에 제목을 음성(TTS)으로 읽어줘서** 노래 제목을 자연스럽게 익히게 하는 iPhone 음악 플레이어. 원래 아이들이 노래 제목을 기억하게 하려고 만든 앱.
- iPhone 음악 보관함 재생, 셔플/반복, 제목 읽기(TTS, 제목→아티스트 순) 설정.
- App Store: https://apps.apple.com/app/riffle/id6759858871

### 지출달력 (ExpenseCal)
- **핵심**: 매달 나갈 지출을 **달력에 미리 올려두고**, 이번 달 지출 예정과 실제가 예정대로 나갔는지 한눈에 확인하는 **월간 지출 관리** 앱. (매일 기록하는 일반 가계부가 아님.)
- "이번 달 총 지출 예정", 예정 지출을 날짜에 배치(휴일이면 다음 평일로), 계좌 설정.
- App Store: https://apps.apple.com/kr/app/지출달력/id6751044457

### KeepStreak
- **핵심**: 의지를 숫자로 남기는 습관 챌린지. "며칠째 지켜냈는지"를 큰 숫자(연속 기록)로 보여줌.
- "안 하기"형 챌린지(탄산·야식·담배 등)는 매일 자동으로 연속 일수 증가, 실패한 날만 리셋. 홈 화면 위젯 지원. 데이터는 기기에만 저장.

### 차곡로그 (Chagok)
- **핵심**: "세상에서 가장 빠른 주유 기록"을 목표로 한 차(車)계부. 주유소에서 몇 초면 기록 끝. 이름은 "**차**곡**차**곡 쌓인다" + "**차**(車)"의 말장난.
- 주행거리 위주 빠른 입력(금액·단가는 지난 기록 참고, 리터 자동 계산), 연비 자동 계산, 오피넷 주변 주유소 실시간 판매가, 통계/위젯/iCloud 동기화. 오프라인 우선.

## 배포

`main` 푸시 시 GitHub Actions가 자동 빌드·배포. 로컬 Ruby(2.6)로는 Jekyll 빌드 불가 → 원격 빌드에 의존. 배포 확인은 `gh run watch` 후 `/browse`로 라이브(https://papig.dev) 확인.

## 공용 설정

- `app-ads.txt`(루트) — AdMob 인증, 전 앱 공용 `pub-9079463377322704`.
- 문의 이메일: 전 페이지 `papig.dev@gmail.com`으로 통일.
