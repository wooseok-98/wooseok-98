# 최우석 - Wooseok Choi

**AI 모델을 서비스로 만들고, 그 결과가 쓸 만한지 검증할 기준을 함께 만듭니다**

- 인공지능 석사, 생성모델 연구로 제1저자 논문 2편 게재
- LLM 응용 시스템을 기획부터 배포까지 단독 구현
- 무엇을 왜 그렇게 정했는지 문서로 남기는 습관

---

## 대표 프로젝트

### [paper-Pilot](https://github.com/wooseok-98/paper-Pilot) · 논문 검색 질의응답 멀티 에이전트

논문을 검색해 초록을 근거로 답하는 LangGraph 기반 에이전트 시스템
정해진 순서를 따르는 대신 각 에이전트가 자기 결과를 보고 다음 행동을 결정하는 구조

| 문제 | 해결 |
| --- | --- |
| 검색 결과에 무관한 논문이 섞임 | 검색어 제외 조건이 불가능해 결과 필터링(CRAG)으로 전환, precision 0.20 → 0.44 (recall 1.00 유지) |
| 개선 여부를 판단할 근거 부재 | 사람이 직접 라벨링한 골드셋 20건 구축, LLM 자기 채점 배제 |
| 근거 없는 답변 생성 | 답변이 초록에 실제 근거하는지 검증하는 Critic, 검출 3/3 · 오탐 0/3 |
| 판단이 휘발됨 | [설계 결정 기록 27건](https://github.com/wooseok-98/paper-Pilot/blob/main/docs/decisions.md) — 되돌린 결정과 그 이유 포함 |

LangGraph · Claude API · FAISS · sentence-transformers · FastAPI · Docker · AWS EC2(ARM)

### [AI-study-chatbot](https://github.com/wooseok-98/AI-study-chatbot) · 근거 기반 RAG 챗봇

학습 노트 450여 조각과 위키 문서를 근거로 답하고 출처를 함께 제시하는 한국어 챗봇
같은 챗봇을 4단계로 발전시키며 RAG와 LangChain, LangGraph를 비교

| 버전 | 내용 |
| --- | --- |
| v1 | Claude 기본 대화, SQLite 멀티턴 |
| v2 | 프레임워크 없이 RAG 직접 구현 — 소스별 청킹 기준 분리 |
| v3 | 동일 기능을 LCEL 체인으로 재구성해 답변 일치 확인 |
| v4 | ReAct 에이전트 — 노트/위키/웹 중 모델이 직접 선택 |

근거가 없으면 답하지 않도록 설계, 답변마다 출처 문단 제시

---

## 논문

제1저자, SCIE 등재지 *Electronics*, 오픈액세스라 전문 열람 가능

| 제목 | 게재 | 링크 |
| --- | --- | --- |
| A Style-Adapted Virtual Try-On Technique for Story Visualization | Electronics 2026, 15(3), 514 | [10.3390/electronics15030514](https://doi.org/10.3390/electronics15030514) |
| A Diffusion Model-Based Character Synthesis Using a Blank Face | Electronics 2025, 14(1), 11 | [10.3390/electronics14010011](https://doi.org/10.3390/electronics14010011) |

두 편 모두 자동 지표와 사용자 평가를 함께 설계해 검증
통계적으로 유의하지 않은 지표는 그 사실을 결과에 그대로 기술

---

## 기술 스택

| 영역 | 사용 |
| --- | --- |
| Language | Python |
| LLM / Agent | LangGraph, LangChain, Claude API, RAG, self-RAG, CRAG |
| ML | PyTorch, Diffusion Models, CLIP, sentence-transformers |
| Vector / Data | FAISS, Qdrant, SQLite |
| Serving | FastAPI, Docker, AWS EC2, RunPod |
| Test | pytest |

---

## 기록

[velog.io/@dan9872](https://velog.io/@dan9872) — 프로젝트 회고와 설계 판단 정리
