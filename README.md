# HR: 사람을 뽑고, 배치하고, 평가하고, 보상하고, 지키는 일 공부하기

HRD(사람을 키우는 일)에서 HR 전반으로 공부 범위를 넓히는 저장소입니다.
[AI-AX의 MCP 강의(mcp-class)](https://github.com/dhcoaud98/AI-AX/tree/master/mcp-class)에서 만든 구조를 그대로 가져와 HR 주제로 바꿨습니다.

## 🎯 이 저장소의 목적

기업교육(HRD) 담당자로 일하면서 "교육 밖의 HR"을 체계적으로 익히고, 나중에 HR 직무(HRBP, 피플 애널리틱스, 채용, 평가·보상)로 넓혀 갈 준비를 하려고 만들었습니다. 세 가지를 함께 합니다.

1. **매일 읽기:** 데일리 브리핑으로 노동법·채용 시장·HR 테크 흐름을 놓치지 않습니다.
2. **직접 만들어 보기:** 인사 데이터와 HR 뉴스를 다루는 MCP 서버를 만들며 "AI를 HR에 안전하게 쓰는 법"을 손으로 익힙니다.
3. **내 말로 정리하기:** 모든 소식과 실습에 "→ 나에게 의미" 한 줄을 남겨, HRD 경험이 HR의 어디에 연결되는지 기록합니다.

## 🗺 학습 로드맵

HR을 다섯 영역으로 나누고, HRD에서 가까운 것부터 넓혀 갑니다. ✅는 이 저장소에 실습이 있는 것, ⬜는 앞으로 채울 것입니다.

| 순서 | 영역 | HRD와 맞닿는 지점 | 공부할 핵심 | 이 저장소에서 |
|---|---|---|---|---|
| 1 | 📊 피플 애널리틱스·HR 테크 | 교육 효과 측정, 역량 진단 데이터 | 인원·이직률·근속 지표, 개인정보 보호, HRIS·ATS 구조 | ✅ `hr-analytics/` |
| 2 | ⚖️ 노무·노동정책 | 법정 의무교육, 취업규칙 안내 | 근로기준법(근로시간·연차·휴가), 퇴직급여, 정년·육아휴직 제도 변화 | ✅ `hr-news/`(노무), 브리핑 📈 / ⬜ 연차 외 계산 실습 |
| 3 | 💼 채용 | 신입 온보딩, 면접관 교육 | 채용 퍼널 지표, 구조화 면접, AI 채용의 공정성 | ✅ `hr-news/`(채용 AI), 브리핑 💼 / ⬜ 구조화 면접 질문 설계 |
| 4 | 🏆 평가·보상 | 역량 모델, 리더십 교육 | MBO·OKR·상시 피드백, 직무급·연봉 밴드, 성과급 설계 | ✅ `hr-analytics/`(평가 분포·연봉 통계) / ⬜ OKR·MBO 비교 |
| 5 | 🌱 조직문화·직원 경험 | 조직 활성화 프로그램, 사내 강사 | 펄스 서베이, 퇴사자 인터뷰 분석, 온보딩 설계 | ⬜ 서베이 분석 실습 |

**추천 순서:** 매일 브리핑 읽기 → `hr-analytics`로 HR 지표 감 잡기 → `hr-news`로 관심 주제 쌓기 → 아래 "앞으로 넓혀 볼 주제"를 하나씩 실습으로 추가하기

| 서버 | 한 마디 정의 | mcp-class에서 이어지는 단계 |
|---|---|---|
| [`hr-analytics/`](hr-analytics/) | 인사 데이터를 **집계만** 보여 주는 피플 애널리틱스 서버 | 4단계 📊 성적표 + 3단계 🔒 보안 |
| [`hr-news/`](hr-news/) | 노무·채용 AI·인사제도 뉴스를 매일 읽고 공부노트에 쌓는 서버 | 6단계 📰 뉴스 |

- **hr-analytics 핵심:** AI가 무엇을 볼 수 있는지는 프롬프트가 아니라 **도구 설계**가 정한다. 개인 단위 결과 없음, 3명 미만 집단 숨김, 모든 조회 기록.
- **hr-news 핵심:** 도구가 신문을 가져다주고, Claude가 골라 읽어 주고, 나는 "나에게 의미" 한 줄만 남긴다.

## 📬 HR 데일리 브리핑 → [`briefings/`](briefings/)

매일 아침 8시 45분(한국 시간), Claude 예약 작업이 웹에서 HR 소식을 모아 요약한 뒤 이 저장소에 올립니다.

- **영역:** 📈 HR 트렌드 / 💼 채용·취업 / 🏢 HR 업계 / 🛠 실무 툴
- **형식:** 소식마다 요약 2~3문장 + **"→ 나에게 의미"** 한 줄 + 출처 링크
- **위치:** `briefings/YYYY/MM/YYYY-MM-DD.md`
- **목록:** [briefings/README.md](briefings/README.md)

```
매일 08:45 → Claude 예약 작업(클라우드) → 웹 검색 → 브리핑 작성 → 이 저장소에 커밋·푸시
```

이 자동화를 왜, 어떻게 만들었는지는 AX 사례 보고서에 정리했습니다 → [docs/AX-보고서_HR데일리브리핑.md](docs/AX-보고서_HR데일리브리핑.md)

## 🧰 준비물

| 준비물 | 용도 | 확인 방법 |
|---|---|---|
| Python 3.10 이상 | 서버 실행 | `python --version` |
| [uv](https://docs.astral.sh/uv/) | 패키지 설치·실행 (필요한 `mcp` 패키지를 알아서 설치) | `uv --version` |
| Git | 저장소 내려받기 | `git --version` |
| [Claude Desktop](https://claude.ai/download) | 만든 서버를 Claude와 연결해 대화로 쓰기 | 앱 실행 |
| 인터넷 연결 | `hr-news`가 Google 뉴스 RSS를 읽을 때만 필요 (`hr-analytics`는 오프라인 가능) | |

uv가 없다면 아래 한 줄로 설치합니다.

```bash
# Windows (PowerShell)
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"

# macOS / Linux
curl -LsSf https://astral.sh/uv/install.sh | sh
```

## ▶️ 실행하기

### 1단계: 저장소 내려받기

```bash
git clone https://github.com/dhcoaud98/HR.git
cd HR
```

### 2단계: 테스트로 동작 확인

Claude 없이도 서버가 제대로 도는지 먼저 확인합니다. 처음 실행할 때 uv가 필요한 패키지를 설치하므로 조금 걸립니다.

```bash
cd hr-analytics
uv sync                 # 패키지 설치 (처음 한 번)
uv run test_client.py   # 도구 7개를 차례로 호출해 결과 출력

cd ../hr-news
uv sync
uv run test_client.py   # 뉴스 검색은 인터넷이 필요
```

테스트가 끝까지 오류 없이 출력되면 성공입니다. `hr-analytics`를 실행하면 조회 기록 파일 `access_log.txt`가 생깁니다.

### 3단계: Claude Desktop에 연결

1. Claude Desktop에서 **설정 → 개발자 → 설정 편집**을 눌러 `claude_desktop_config.json`을 엽니다.
2. `mcpServers` 안에 두 서버를 추가합니다. 경로는 **내 컴퓨터에 내려받은 실제 폴더 경로**로 바꿉니다.

```json
{
  "mcpServers": {
    "hr-analytics": {
      "command": "uv",
      "args": ["--directory", "C:\\Users\\내이름\\HR\\hr-analytics", "run", "server.py"]
    },
    "hr-news": {
      "command": "uv",
      "args": ["--directory", "C:\\Users\\내이름\\HR\\hr-news", "run", "server.py"]
    }
  }
}
```

3. Claude Desktop을 **완전히 종료했다가 다시 실행**합니다. 입력창의 도구 메뉴에 `hr-analytics`, `hr-news`가 보이면 연결된 것입니다.
4. 이렇게 물어보며 시작해 보세요.
   - "부서별 재직 인원과 2025년 이직률 알려 줘" → `hr-analytics`
   - "오늘 노무 뉴스 3개만 골라 줘" → `hr-news`

### 막힐 때

| 증상 | 확인할 것 |
|---|---|
| `uv: command not found` | uv 설치 후 터미널을 새로 열었는지 |
| Claude 도구 메뉴에 서버가 안 보임 | JSON 쉼표·따옴표 오류, 경로의 `\\` 두 번 쓰기, 앱 완전 재시작 |
| `uv`를 못 찾는다는 오류(Claude Desktop) | `"command"`에 uv 전체 경로 쓰기 (`where uv` / `which uv`로 확인) |
| `hr-news`에서 기사가 0개 | 인터넷 연결, 회사 방화벽이 Google 뉴스를 막는지 |

서버별 도구 설명과 실습 질문은 [hr-analytics/README.md](hr-analytics/README.md), [hr-news/README.md](hr-news/README.md)에 있습니다.

## 폴더 구조

```
HR/
├── README.md            ← 지금 보는 파일
├── docs/                ← 📝 AX 사례 보고서와 이미지
│   ├── AX-보고서_HR데일리브리핑.md
│   └── images/
├── briefings/           ← 📬 HR 데일리 브리핑 (매일 자동 추가)
│   ├── README.md
│   └── 2026/10/2026-10-28.md ...
├── hr-analytics/        ← 👥 피플 애널리틱스 + 개인정보 보호
│   ├── README.md
│   ├── server.py
│   ├── employees.csv    ← 가짜 직원 데이터
│   ├── test_client.py
│   └── pyproject.toml
└── hr-news/             ← 📰 HR 뉴스 (노무·채용 AI·인사제도)
    ├── README.md
    ├── server.py
    ├── test_client.py
    └── pyproject.toml
```

## 앞으로 넓혀 볼 주제

- 채용: 구조화 면접 질문 설계, AI 채용의 공정성과 편향
- 평가·보상: OKR·MBO 비교, 직무급과 연봉 밴드
- 조직문화·직원 경험: 펄스 서베이, 퇴사자 인터뷰 분석, 온보딩 설계
