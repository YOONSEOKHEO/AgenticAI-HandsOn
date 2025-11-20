# Part 3. ADK & MCP 기반 Agentic AI   
**Building Agentic AI Systems with ADK + MCP**

본 실습은 ADK(Agent Development Kit)와 MCP(Model Context Protocol)를 활용하여  
지능형 에이전트, Tool 기반 상호작용, A2A(Agent-to-Agent) 구조,  
그리고 Web 데모 배포까지 직접 구현해보는 실무 중심 과정입니다.

> 총 6개 세션(각 50분) + 휴식 15분 + 점심 60분  
> **09:30 ~ 16:30**

---

## 📝 사전 참여 요청  
### 👉 [Google Form 바로가기](https://forms.gle/YBRmi5shNTNnvfVy8)

---

# ⏰ 전체 시간표

| 세션 | 시간 | 내용 |
|------|------|------|
| **Session 1** | **09:30 – 10:20** | ADK & MCP 개념 이해 |
| 휴식 | 10:20 – 10:35 |  |
| **Session 2** | **10:35 – 11:25** | A2A 실습 (1) |
| 휴식 | 11:25 – 11:40 |  |
| **Session 3** | **11:40 – 12:30** | A2A 실습 (2) |
| **점심** | **12:30 – 13:30** | 60분 |
| **Session 4** | **13:30 – 14:20** | ADK & MCP 실습 (1) |
| 휴식 | 14:20 – 14:35 |  |
| **Session 5** | **14:35 – 15:25** | ADK & MCP 실습 (2) |
| 휴식 | 15:25 – 15:40 | |
| **Session 6** | **15:40 – 16:30** | Web 데모 배포 + 총정리 |

---

# 📚 세부 커리큘럼

## **Session 1 — ADK & MCP 개념 (09:30 – 10:20)**

### 🎯 학습 목표
- ADK의 구조와 철학 이해  
- MCP(Model Context Protocol)의 목적 및 구성 요소 파악  
- Agent / Tool / Instruction / Model 간 관계 구조 분석  
- 개발 환경 구성 및 필수 라이브러리 설치

### 📘 주요 내용
- ADK Overview (Runner, SessionService, Agent, Tool)
- MCP Overview (Tool Registry, stdio 기반 서버 개념)
- Tool Docstring 기반 Tool 활용 전략
- 단일 Agent의 최소 구성 예제 분석

---

## **Session 2 — A2A 실습 (1): Agent-to-Agent Interaction (10:35 – 11:25)**

### 🎯 학습 목표
- A2A 통신 구조 이해  
- Tool 기반의 요청-응답 흐름 파악  
- ADK에서 에이전트 간 상호작용 구현

### 🛠️ 실습
- Weather Agent & Info Agent 만들기  
- A2A 요청 플로우 구성  
- Runner & SessionService 활용하여 Agent-to-Agent 메시지 처리

---

## **Session 3 — A2A 실습 (2): 멀티 모델 기반 실행 (11:40 – 12:30)**

### 🎯 학습 목표
- LiteLLM을 통한 다양한 모델(Gemini, GPT, Claude) 연결  
- 동일한 Agent Logic을 다른 모델에서 실행  
- 모델별 응답 스타일 비교

### 🛠️ 실습
- LiteLLM 설정  
- Multi-Model Weather Agent 구성  
- Gemini → GPT → Claude 결과 비교

---

## **Session 4 — ADK & MCP 실습 (1): Tool 정의 & MCP 연동 (13:30 – 14:20)**

### 🎯 학습 목표
- Python Tool 정의 및 Docstring 설계  
- MCP 서버 구성 및 Tool 노출 방법 이해  
- ADK Agent가 MCP Tool을 자동 로딩하는 과정 학습

### 🛠️ 실습
- MCP Server(Stdio 기반) 직접 실행  
- SQLite 또는 Custom Tool MCP 서버 구성  
- ADK Agent에서 MCP Toolset 연결  
- Tool 호출 결과 및 event 로그 분석

---

## **Session 5 — ADK & MCP 실습 (2): 복합 Tool 활용 & 실전 시나리오 (14:35 – 15:25)**

### 🎯 학습 목표
- ADK Agent가 외부 MCP Tool을 실제 활용하는 시나리오 구성  
- Tool 입력/출력 및 예외 처리 구조 이해  
- ToolContext 기반 고급 Tool 사용 패턴 학습 (상태 기반 요소 제외)

### 🛠️ 실습
- Query Tool, Insert Tool 등 다양한 MCP Tool 호출  
- Tool 호출 흐름 추적 및 디버깅  
- A2A + MCP Tool 조합 실습  
- 실서비스용 Tool 모듈 구성 방법 논의

---

## **Session 6 — Web 데모 배포 및 총정리 (15:40 – 16:30)**

### 🎯 학습 목표
- ADK Web UI 기반 데모 서비스 배포  
- main.py 기반 코드 통합 및 구조 정리  
- 실습 결과물 전체 흐름 복습

### 🛠️ 실습
- `adk web` 명령으로 Web UI 실행  
  ```bash
  adk web main.py --port=8080
