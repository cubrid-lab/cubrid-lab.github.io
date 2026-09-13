# CUBRID Lab — 조직 랜딩 사이트

[![Docs](https://img.shields.io/badge/site-cubrid--lab.github.io-FF6600)](https://cubrid-lab.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

이 저장소는 [cubrid-lab](https://github.com/cubrid-lab) 조직의 랜딩 사이트를 호스팅한다:
<https://cubrid-lab.github.io/>

## 구성

| 경로 | 용도 |
|---|---|
| `docs/` | MkDocs Material 소스 (홈, 패키지, 문서 허브, 시작하기, 로드맵, 커뮤니티, 소개) |
| `mkdocs.yml` | 사이트 설정 및 내비게이션 |
| `.github/workflows/docs.yml` | GitHub Pages 빌드/배포 (다른 cubrid-lab 저장소와 동일한 패턴) |

## 로컬 개발

```bash
pip install mkdocs-material pymdown-extensions
mkdocs serve
# http://localhost:8000 접속
```

빌드 검사 (CI 강제):

```bash
mkdocs build --strict
```

## 콘텐츠 정책

- **영어 우선**: 원문은 영어이며, 한국어 번역은 조직 공통
  `README.ko.md` 동기화 패턴을 따른다.
- **AI 저작 서술 금지**: 공개 콘텐츠는 검증 시스템(테스트, CI 게이트)을
  설명하며, 코드를 누가/무엇이 작성했는지에 대한 서술은 포함하지 않는다.
- **수치 위생**: 숫자는 검증된 메트릭 스냅샷에서 가져오고 릴리스 시점에
  재측정한다. 오래된 스타/다운로드 배지는 붙이지 않는다.
- 주장은 방어 가능하게 표현한다 (예: "세계 최초"가 아니라
  "공개적으로 사용 가능한 최초의 CUBRID MCP 서버").

## 기여

이슈-퍼스트 워크플로우, 커밋 컨벤션, 번역 거버넌스는
[커뮤니티 페이지](https://cubrid-lab.github.io/community/)를 참고한다.

## 라이선스

[MIT](LICENSE) — 안정화된 cubrid-lab 패키지들과 동일하다.
