# 최우석 - Wooseok Choi

**평가 기준을 먼저 만들고, 모든 개선을 측정으로 판단하는 AI 엔지니어**

- 인공지능 석사, 생성모델 연구로 SCIE 제1저자 논문 2편 게재
- 연구와 프로젝트 모두 평가 기준부터 세우고, 개선 효과를 같은 기준의 측정으로 검증
- 생성모델 연구부터 LLM 에이전트 서비스의 설계, 서빙, 배포까지 모델과 서비스 모두 경험

---

## 대표 프로젝트

### [여담](https://github.com/100-hours-a-week/KTB4-2nd-AI) | 여행 사진 자동 정리, 자연어 검색 서비스

카카오테크 부트캠프 팀 프로젝트(6명, AI 파트 담당), 2026.08 - 2026.11

- 정리 200장, 검색 51문항 평가셋을 먼저 만들고 모든 개선을 같은 기준으로 재측정
- LangGraph 정리 에이전트로 위치 정보 없는 사진의 미분류 71장 → 1장
- 단계별 시간 분해로 정리 대기 33.2초 → 3.6초(에이전트 도입 전), vLLM MTP로 질의 해석 p50 2.75초 → 1.73초

Gemma 4 31B, Qwen3-VL-Embedding-2B, vLLM, LangGraph, Qdrant, FastAPI, Kafka, AWS EC2, RunPod | [개발 블로그](https://medium.com/yeodam-tech)

### [paper-Pilot](https://github.com/wooseok-98/paper-Pilot) | 논문 검색 질의응답 멀티 에이전트

개인 프로젝트, 2026.07 - 2026.08, AWS EC2 배포

- Orchestrator, Researcher(CRAG), QA(Self-RAG), Critic(Reflection) 4개 에이전트를 LangGraph로 구성
- 사람 라벨 골든셋으로 검색 precision 0.20 → 0.44(recall 1.00 유지), 프롬프트 수정의 회귀(recall 1.00 → 0.25)를 잡아 되돌림
- 되돌린 결정까지 남긴 [설계 결정 기록 27건](https://github.com/wooseok-98/paper-Pilot/blob/main/docs/decisions.md)

LangGraph, Claude API, FAISS, FastAPI, Docker, AWS EC2

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

## 기타 프로젝트

- [AI-study-chatbot](https://github.com/wooseok-98/AI-study-chatbot): 학습 노트 기반 한국어 RAG 챗봇, 프레임워크 없이 직접 구현한 RAG에서 LangChain, LangGraph 에이전트까지 4단계로 발전시키며 비교

---

## 기술 스택

| 영역 | 사용 |
| --- | --- |
| Language | Python |
| LLM / Agent | LangGraph, LangChain, Claude API, Gemma 4, RAG, self-RAG, CRAG |
| ML | PyTorch, Diffusion Models, CLIP, Qwen3-VL-Embedding, sentence-transformers |
| Vector / Data | Qdrant, FAISS, SQLite |
| Serving | vLLM, FastAPI, Docker, Kafka, Redis, AWS EC2, RunPod |
| Test | pytest |

---

## 기록

- [velog.io/@dan9872](https://velog.io/@dan9872), 프로젝트 회고와 설계 판단 정리
- [Medium 여담 팀 블로그](https://medium.com/yeodam-tech), 사진 정리 속도 개선 시리즈
