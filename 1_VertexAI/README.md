# 1차시 교육: 클라우드 기반 예측 모델 API 구축 (Vertex AI)

## Ⅰ. 과정 개요 (Overview)

본 과정은 클라우드 환경에서 머신러닝 모델을 서비스로 배포하는 End-to-End 파이프라인을 경험하는 첫 번째 단계입니다. Google Cloud의 통합 AI 플랫폼인 **Vertex AI**를 활용하여 금융 데이터를 학습시키고, 실시간 예측이 가능한 REST API를 직접 구축합니다. 이 과정에서 완성된 'AI 대출 심사 API'는 2차시에서 구축할 지능형 에이전트의 핵심 '전문가 도구(Tool)'로 활용됩니다.

---

## Ⅱ. 학습 목표 (Learning Objectives)

본 과정을 수료한 수강생은 다음을 할 수 있게 됩니다:

- ✅ **Vertex AI**를 활용하여 MLOps의 핵심 파이프라인(개발 → 저장 → 등록 → 배포)을 설명할 수 있습니다.
- ✅ 정형(Tabular) 데이터를 전처리하고 **Scikit-learn**을 이용해 예측 모델을 학습시킬 수 있습니다.
- ✅ 학습된 모델을 **Cloud Storage**에 저장하고 **Vertex AI Model Registry**에 등록하여 관리할 수 있습니다.
- ✅ 등록된 모델을 **Vertex AI Endpoint**에 배포하여 외부에서 호출 가능한 **REST API**를 생성할 수 있습니다.
- ✅ 생성된 API를 Python SDK를 통해 호출하고 실시간 예측 결과를 검증할 수 있습니다.

---

## Ⅲ. 최종 결과물 (Final Deliverable)

- **AI 대출 심사 API Endpoint:** GCP 프로젝트에 배포된, 고유 URL을 가진 실시간 예측 API
- **API 호출 및 검증 코드:** 새로운 대출 신청자 데이터를 API로 전송하여 '승인(Y)' 또는 '거절(N)' 결과를 성공적으로 반환하는 Python 코드 및 실행 결과

---

## Ⅳ. 기술 스택 (Tech Stack)

| 구분 | 기술 / 서비스 | 활용 목적 |
|:---:|:---|:---|
| **Cloud Platform** | Google Cloud Platform (GCP) | 전체 인프라 환경 |
| **AI Platform** | Vertex AI | AI 개발, 학습, 배포, 서비스의 통합 관리 |
| **Development** | ↳ Vertex AI Workbench | JupyterLab 기반의 클라우드 통합 개발 환경 |
| **Storage** | ↳ Google Cloud Storage (GCS) | 학습된 모델 파일(`.pkl`) 저장 및 관리 |
| **MLOps** | ↳ Vertex AI Model Registry | 모델 버전 관리 및 공식 등록 |
| **Serving** | ↳ Vertex AI Endpoint | 모델을 REST API로 배포 및 서빙 |
| **Library** | Scikit-learn, Pandas | 데이터 처리 및 머신러닝 모델 학습 |

---

## Ⅴ. 세부 커리큘럼 (Detailed Curriculum)

### Session 1: Vertex AI 개요 및 환경 설정
- **🎯 목표:** 클라우드 AI 플랫폼의 개념을 이해하고, 실습을 위한 Vertex AI 환경을 초기 설정합니다.
- **🔑 핵심 내용:** 클라우드 ML vs 로컬 ML, Vertex AI의 주요 구성요소, GCP 프로젝트 설정
- **🛠️ 실습:** GCP 콘솔 접속, Vertex AI API 활성화, IAM 권한 확인, 결제 예산 및 알림 설정

### Session 2: Vertex AI Workbench - 클라우드 통합 개발 환경
- **🎯 목표:** Vertex AI 내에서 코드 개발, 실험, 터미널 사용이 모두 가능한 JupyterLab 환경을 구성합니다.
- **🔑 핵심 내용:** Managed Notebooks의 개념, 인스턴스 생성 및 사양 설정
- **🛠️ 실습:** `asia-northeast3(Seoul)` 리전에 Workbench 인스턴스 생성, JupyterLab 접속 및 기본 환경 테스트

### Session 3: 모델 학습 - AI 대출 심사관 만들기
- **🎯 목표:** 금융 데이터를 사용하여 대출 신청의 승인/거절을 예측하는 머신러닝 모델을 학습시킵니다.
- **🔑 핵심 내용:** 정형 데이터 분석(Pandas), 특성(Feature)과 목표(Target), 분류(Classification) 모델
- **🛠️ 실습:** Workbench 노트북에서 대출 심사 데이터(CSV) 로드, `RandomForestClassifier` 모델 학습, 학습된 모델을 `.pkl` 파일로 저장

### Session 4: 모델 등록 - GCS 연동 및 버전 관리
- **🎯 목표:** 개발 환경에 생성된 모델 파일을 영구적인 클라우드 스토리지로 옮기고, Vertex AI에 공식 모델로 등록합니다.
- **🔑 핵심 내용:** GCS Bucket/Object 개념, `gsutil` 명령어, Model Registry의 역할
- **🛠️ 실습:** Workbench 터미널에서 `gsutil`을 사용해 `.pkl` 파일을 GCS 버킷에 업로드, Vertex AI UI에서 GCS 경로를 지정하여 모델 등록

### Session 5: 모델 배포 - Endpoint 생성을 통한 서비스화
- **🎯 목표:** 등록된 모델을 실제 서비스 요청을 처리할 수 있는 서버에 올려 외부 접근이 가능한 API를 생성합니다.
- **🔑 핵심 내용:** 모델 서빙(Serving)의 개념, Endpoint와 Deployed Model의 관계
- **🛠️ 실습:** Vertex AI UI에서 등록된 모델을 선택하여 '엔드포인트에 배포' 실행, 머신 타입 설정 및 배포 시작

### Session 6: API 테스트 - 실시간 예측 및 검증
- **🎯 목표:** 완성된 API Endpoint에 가상의 고객 데이터를 전송하여 실시간으로 예측 결과를 받아보는 최종 테스트를 수행합니다.
- **🔑 핵심 내용:** REST API 요청/응답 구조, Vertex AI SDK를 활용한 API 호출
- **🛠️ 실습:** Workbench 노트북에서 Python SDK를 사용하여 자신의 Endpoint에 예측 요청, '승인'/'거절' 결과가 정상적으로 반환되는지 확인 및 프로젝트 최종 완성

---

## 🚀 다음 차시 예고 (Next Step)

본 과정에서 완성한 **`AI 대출 심사 API`**는 2차시 **`Agentic AI & A2A Collaboration`** 과정에서 Gemini 기반의 '매니저 에이전트'가 사용하는 핵심 **`Tool`**이 됩니다.
