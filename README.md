# ⚔️ 아이디어 배틀

두 아이디어를 입력하면 AI가 장단점을 분석하고 승자를 판정해주는 웹 서비스입니다.
사내 AI 스터디 산출물로 제작되었습니다.

---

## 주요 기능

- **AI 아이디어 분석** — 두 아이디어의 장점, 단점을 각각 분석
- **카테고리별 평가 기준** — AI 스터디 산출물, 플랫폼 서비스, 기획, 디자인, 개발, 마케팅, 사업, 워크샵, 일상생활 등 카테고리마다 다른 관점으로 평가
- **AI 심판 판정** — 분석 결과를 바탕으로 승자와 이유를 제시
- **팀 공유 히스토리** — Firebase Realtime Database를 통해 팀원 모두가 배틀 기록을 실시간 공유
- **개별 기록 삭제** — 히스토리 항목별 삭제 가능
- **다크모드 지원** — 시스템 설정에 따라 자동 전환

---

## 기술 스택

- **Frontend** — Vanilla JS / HTML / CSS (프레임워크 없음, 단일 파일)
- **AI** — Google Gemini API (`gemini-2.5-flash-lite`)
- **Database** — Firebase Realtime Database (REST API)
- **Hosting** — Vercel / GitHub Pages

---

## 시작하기

### 1. Google Gemini API 키 발급
1. [aistudio.google.com/app/apikey](https://aistudio.google.com/app/apikey) 접속 (개인 구글 계정)
2. **Create API Key** 클릭 후 키 복사

### 2. Firebase 설정
1. [console.firebase.google.com](https://console.firebase.google.com) 접속
2. 프로젝트 만들기 → **Realtime Database** 생성 → 테스트 모드로 시작
3. 규칙(Rules) 탭에서 아래와 같이 설정 후 게시

```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

### 3. 실행
`index.html`을 Vercel, GitHub Pages 등 웹 서버에 배포 후 접속
> ⚠️ `file://`로 직접 열면 API 호출이 차단되므로 반드시 웹 서버를 통해 접속해야 합니다.

---

## 카테고리별 평가 기준

| 카테고리 | 평가 기준 |
|---|---|
| 일반 | 실현 가능성, 독창성, 기대 효과 |
| AI 스터디 산출물 | 학습 효과, 구현 난이도, 활용 가능성 |
| 플랫폼 서비스 | 유저 경험, 플랫폼 적합성, 비즈니스 임팩트 |
| 기획 | 목표 명확성, 실행 가능성, 이해관계자 설득력 |
| 디자인 | 사용자 경험, 심미성, 일관성 및 확장성 |
| 개발 | 기술 구현 난이도, 유지보수성, 확장성 |
| 마케팅 | 타겟 도달력, 브랜드 임팩트, 비용 효율 |
| 사업 | 수익성, 시장 규모, 경쟁 우위 |
| 워크샵 | 참여 유도, 학습 효과, 현장 실행 가능성 |
| 일상생활 | 편의성, 지속 가능성, 삶의 질 향상 |

---

## 제작

사내 AI 스터디 (Claude + Gemini API 활용 실습)
