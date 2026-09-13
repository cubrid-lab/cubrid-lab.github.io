# 한국 공공시장 DBMS에 Python 문을 열다

> cubrid-lab 오픈소스 생태계 구축기 — 컨트리뷰션 프로그램에서 시작해 6년 만에 완성한 4개 패키지
>
> *2026년 9월 · cubrid-lab maintainers · [English summary](index.md)*

## 6년 전, 한 질문에서 시작했다

2020년, 공공 기관이 운영하는 오픈소스 컨트리뷰션 프로그램에서 두 사람이 멘토와 멘티로 만났다. 그때 다룬 기술은 SQLAlchemy였고, 커뮤니티에서 만난 사람은 Mike Bayer(SQLAlchemy 창시자)였다.

그러다 한 가지 사실을 발견했다:

**한국 공공부문 DBMS 점유율의 약 10%가 CUBRID인데, 공식 Python 드라이버의 마지막 릴리스는 2014년 5월이었다.**

12년 동안 Python 개발자들은 CUBRID를 제대로 사용할 수 없었다. CUBRID로 구축된 1,500개 이상의 공공 시스템을 유지보수하는 개발자들은 ORM, 웹 프레임워크, 데이터 분석 도구, AI 에이전트로 이어지는 현대적 Python 스택에서 배제되어 있었다.

## 무엇을 만들었나

4개의 패키지를 만들었다. 각 단계에서 드러난 갭이 다음 단계를 자연스럽게 낳았다.

### 1. sqlalchemy-cubrid (2021–22)

SQLAlchemy 창시자 Mike Bayer가 2012년에 만든 CUBRID 방언은 오래전 멈춰 있었다. SQLAlchemy 2.0을 기준으로 처음부터 재작성했다.

- 스키마 리플렉션 (테이블, 컬럼, PK, FK, 인덱스, 뷰, 코멘트)
- `MERGE`, `ON DUPLICATE KEY UPDATE`, `REPLACE`
- Native `ENUM` (CUBRID 10.2–11.4 실증 후 구현)
- Alembic 마이그레이션 지원
- SQLAlchemy 공식 테스트 스위트 통합

### 2. pycubrid (2025)

방언을 만들고 보니 드라이버가 문제였다. 2014년 이후 방치된 C 확장. 그래서 순수 Python으로 새로 만들었다.

CAS 바이너리 프로토콜 문서가 존재하지 않아, BSD 라이선스의 node-cubrid와 공식 C 드라이버 소스를 교차 분석해 프로토콜을 해독했다. 18개 패킷 타입, 27개 데이터 타입.

```bash
pip install pycubrid  # 한 줄 설치, C 컴파일러 불필요, 의존성 0개
```

### 3. cubrid-cookbook-python (2026)

75개 예제와 7개 프로덕션 템플릿 (FastAPI, Flask, Django, Streamlit, Celery, ETL, AI 에이전트).

단순한 예제집이 아니라 **dogfooding 플랫폼**이다. 매일 밤 45개 예제가 실서버 CUBRID 11.2 + 11.4에서 실행된다. 드라이버에 회귀가 생기면 cookbook이 가장 먼저 잡아낸다.

### 4. cubrid-mcp-server (2026)

MCP(Model Context Protocol)가 AI 애플리케이션과 데이터베이스를 잇는 표준으로 자리잡고 있다. 공개적으로 사용 가능한 최초의 CUBRID MCP 서버를 출시했다.

- 12개 도구 (11개 읽기 + 1개 옵트인 쓰기), 읽기 전용 화이트리스트
- AI 에이전트가 자연어로 CUBRID에 질의
- 도메인 지식 팩 내장 — LLM에게 CUBRID SQL 문법을 가르친다

```bash
uvx cubrid-mcp-server
# Claude: "부처별 문서량 상위 5개 보여줘"
```

## 어떻게 품질을 보장하나

모든 변경은 병합 전에 자동화된 게이트를 통과한다:

| 게이트 | 내용 |
|---|---|
| 타입 안전성 | `mypy --strict`, 0 에러 |
| 커버리지 | 95% 하한 (CI 강제) |
| 린트/포맷 | ruff (CI 강제) |
| 속성 기반 테스트 | hypothesis (난수 기반) |
| API 호환성 | api-baseline.json 게이트 |
| 골든 테스트 | 45개 예제 매일 밤 실서버 실행 |
| SQLAlchemy 스위트 | 공식 테스트 스위트 통합 |
| CI 매트릭스 | Python 5 버전 × CUBRID 4 버전 = 20조합 (라이브 DB) |

총 **2,200개 테스트**, **450개 병합된 PR**, **35회의 PyPI 릴리스**가 이 과정을 거쳤다. 모든 저장소는 MIT 라이선스이며, 모든 릴리스에 SPDX SBOM이 첨부된다.

## 숫자로 보는 성과 (2026년 9월 기준)

| 지표 | 값 |
|---|---|
| GitHub 스타 (4개 리포 합산) | 111 |
| 유니크 클론 (14일) | 822명 |
| 병합된 PR | 450개 |
| PyPI 릴리스 | 35회 |
| 테스트 | 2,200개 |
| 문서 사이트 | 4개 (영어 63페이지 + 한국어 34페이지) |
| CI 조합 | Python 5 × CUBRID 4 = 20 (라이브 DB) |

## 니치 시장에서 OSS를 키우는 방법

CUBRID는 니치 시장이다. PostgreSQL처럼 커뮤니티가 자발적으로 도구를 만들어주지 않는다. 그래서:

1. **직접 벤치마크한다** — [cubrid-benchmark](https://github.com/cubrid-lab/cubrid-benchmark) 저장소, 재현 가능한 실험과 자동 비교
2. **직접 쓴다** — dogfooding, 매일 밤 실서버 검증
3. **문서화한다** — 4개 사이트, 한국어 34페이지
4. **AI-ready하게 만든다** — MCP 서버 + 도메인 지식 팩

니치 시장의 OSS는 사용자가 찾아와주기를 기다리지 않고, 검증 가능한 결과를 스스로 축적하는 수밖에 없다고 믿는다.

## 앞으로

TypeScript, Go, Rust 생태계도 진행 중이다. Python에서 검증한 플레이북 — 프로토콜 수준 테스트, 라이브 DB CI 매트릭스, 번역 거버넌스, 레지스트리 게시 — 을 동일하게 적용한다. **CUBRID 4개 언어 생태계**가 목표다.

---

**링크**

- GitHub: <https://github.com/cubrid-lab>
- 드라이버 문서: <https://cubrid-lab.github.io/pycubrid/>
- PyPI: <https://pypi.org/project/pycubrid/> · <https://pypi.org/project/cubrid-mcp-server/>
- 벤치마크: <https://github.com/cubrid-lab/cubrid-benchmark>
