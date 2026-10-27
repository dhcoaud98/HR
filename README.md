# HR: 사람을 뽑고, 배치하고, 평가하고, 보상하고, 지키는 일 공부하기

HRD(사람을 키우는 일)에서 HR 전반으로 공부 범위를 넓히는 저장소입니다.
[AI-AX의 MCP 강의(mcp-class)](https://github.com/dhcoaud98/AI-AX/tree/master/mcp-class)에서 만든 구조를 그대로 가져와 HR 주제로 바꿨습니다.

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

## 실행하기

```bash
cd hr-analytics   # 또는 hr-news
uv sync
uv run test_client.py
```

Claude Desktop 연결 방법과 실습 질문은 각 폴더의 README에 있습니다.

## 폴더 구조

```
HR/
├── README.md            ← 지금 보는 파일
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
