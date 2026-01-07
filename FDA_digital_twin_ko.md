# FDA 준수 디지털 트윈 신약 개발: 종합 사례 분석

## 경영진 요약

디지털 트윈 기술은 이론적 개념에서 신약 개발 및 의료기기 계획을 위한 규제 승인 방법론으로 성숙했다. FDA와 EMA는 디지털 트윈을 유효한 과학적 증거로 인정하는 프레임워크를 확립했으며, Unlearn.AI의 PROCOVA 방법론은 임상시험 표본 크기를 줄이기 위한 첫 번째 ML 기반 규제 승인을 달성했다. 주요 제약회사(Johnson & Johnson, AbbVie, Merck KGaA, Trace Neuroscience)는 Phase 2 및 Phase 3 시험에서 디지털 트윈을 운영하고 있으며, 대조군 크기에서 19-33% 감소, 통계적 검정력에서 5-10% 개선을 입증했다.[1][2][7][21][41][44]

규제 경로는 이제 명확하게 정의되었으며, FDA의 위험 기반 신뢰도 평가 프레임워크(2023년 11월)와 2025년 1월 AI를 위한 규제 의사결정 지침에 정착했다. Eli Lilly와 Takeda의 제조 구현은 가시적인 운영상 이점을 보여준다: 공정 개발 시간 30% 단축 및 실시간 방출 검사 개선. 전자 기록 준수는 규제된 환경에서 디지털 트윈 적용을 위해 21 CFR Part 11에서 필수이다.

---

## I. 규제 프레임워크 & FDA 지침

### A. 위험 기반 신뢰도 평가 프레임워크

FDA의 2023년 11월 의료기기 제출물에서 계산 모델링 및 시뮬레이션(CM&S)에 관한 지침은 구조화된 신뢰도 평가 프로세스를 확립한다.[56] 이 프레임워크는 1차 원리(물리 기반 또는 메커니즘 기반) 모델에 적용되며 규제 제출물에서 사용되는 디지털 트윈을 평가하기 위한 표준이 되었다.

**프레임워크 구성 요소:**

1. **관심 질문 정의**: 해결할 의사결정 또는 우려사항을 명시—예: "이 기기 구조가 예상된 최악의 로딩을 견딜 수 있을까?"

2. **사용 맥락(COU) 진술**: 모델링할 대상, 출력값이 의사결정을 어떻게 알려줄지, 모델을 어떤 다른 증거(벤치 테스트, 임상 연구)로 보충할지에 대한 상세한 설명

3. **모델 위험 평가**: 두 가지 요소의 조합:
   - **모델 영향**: 다른 증거에 비한 계산 모델의 기여도(주요 의사결정 기반이면 높음; 여러 입력 중 하나이면 낮음)
   - **의사결정 결과**: 잘못된 의사결정으로부터의 해악 심각도, 기반 확률 및 부작용의 크기[2][56]

4. **신뢰도 증거 범주**:
   - 코드 검증 결과
   - 모델 보정 증거
   - 벤치 테스트 검증 결과
   - 생체내 검증 결과
   - 모집단 기반 검증 결과
   - 모델 타당성 분석

5. **적절성 평가**: 모델 위험을 고려할 때 신뢰도 증거가 충분한지 사전(모델 실행 전)과 사후(데이터 수집 후) 평가[56]

**디지털 트윈에 대한 적용**: 환자 결과를 예측하거나 합성 대조군을 생성하는 데 사용되는 디지털 트윈의 경우, 모델 영향은 일반적으로 높음(의사결정의 주요 근거)으로 평가되며, 의사결정 결과는 치료 맥락에 따라 다르다. FDA는 바이오마커나 임상 평가 등 다른 요소가 독립적인 검증을 제공하는지 평가한다.[2]

### B. 2023년 5월 FDA 신약 개발에서의 AI/ML 논의 문서

FDA는 2021년 한 해에 제출된 100개 이상의 신약 및 생물학적 제제 신청서에 AI/ML 성분이 포함된 것으로 인정했다.[59] 이 논의 문서는 다음을 위한 디지털 트윈을 명시적으로 승인했다:

- 위약 반응군을 예측하기 위해 모의 임상 기록 생성
- 환자 집단을 나타내는 가상 코호트 생성
- 임상 시험에서 위약 대조군을 대체하거나 증강
- 과학적 엄밀성을 유지하면서 타임라인 가속화[1]

FDA는 디지털 트윈이 "더 빠른" 치료 접근을 가능하게 하고 대표적인 가상 모집단을 통해 "건강 형평성"을 개선함으로써 신약 개발을 혜택할 수 있다고 지적했다—임상 시험에서 역사적 대표성 부족을 다루는 것이다.[1]

### C. 2025년 1월 지침: 신약 및 생물학적 제제용 AI

FDA-2024-D-4689 docket으로 공개된 이 지침은 AI/ML을 신약 규제 의사결정에 적용하기 위한 FDA의 가장 포괄적인 성명을 나타낸다.[70][73] 주요 특징:

- **범위**: 신약 및 생물학적 제제의 안전성, 유효성 및 품질(신약 발견이나 운영 효율성 아님)
- **기초**: 2023년 논의 문서에 대한 800개 이상의 이해관계자 의견 및 AI/ML 성분이 있는 300개 이상 제출물의 FDA 검토
- **프레임워크**: 각 규제 의사결정에 특정한 사용 맥락(COU) 강조와 위험 기반 신뢰도 평가
- **모델 감시**: 승인 후 AI 모델의 지속적인 생명주기 관리 및 인간 검토 요구

---

## II. 임상시험 적용: Unlearn.AI 디지털 트윈

### A. EMA 승인(2022년 9월)

Unlearn.AI는 피벗 시험에서 표본 크기를 줄이기 위한 ML 기반 방법의 첫 규제 승인을 달성했다.[21][25][84] EMA의 최종 호의적 승인 의견은 PROCOVA™(PRObabilistic COVariate Adjustment) 방법론을 승인했으며, 이는 다음을 수행하는 3단계 절차이다:

1. 기준선 데이터로부터 환자별 예측 점수 생성
2. 이 점수를 표준 ANCOVA 통계 모델에 통합
3. 1형 오류 통제를 유지하면서 검정력을 증가시키거나 표본 크기 감소[25][28]

**핵심 규제 소견**: EMA는 PROCOVA를 "ANCOVA의 특수한 경우"로 판단하여, 공변량 조정에 대한 기존 통계 지침 범위 내에 들어오도록 배치했다—이는 디지털 트윈을 새로운 ML 알고리즘보다는 방법론적 혁신으로 위치시킨 중요한 틀이다.[28][91]

### B. FDA CDER 합의(2024년 1월)

FDA는 이후 EMA 평가와의 일치를 확인하여 PROCOVA가 "현재 지침을 준수하며, EMA와 FDA 표준 모두에서 수용된 통계 방법론으로 인정"한다는 편지를 발급했다.[8][27][28]

주목할 점은 FDA가 Unlearn의 ISTAND 파일럿 프로그램 청원을 거절했다는 것인데, 그 이유는 PROCOVA가 이미 무작위배정 임상시험에서 공변량 조정에 관한 FDA의 기존 지침으로 다루어졌기 때문이다—이는 디지털 트윈 통합이 새로운 AI 특정 경로를 필요로 하지 않고 현재의 규제 수용을 충족한다는 증거이다.[28]

### C. 임상 파트너십 결과

#### Johnson & Johnson Innovative Medicine: 알츠하이머병 Phase 3 사후 분석

Unlearn은 경증에서 중등도 알츠하이머병의 3개 피벗 Phase III 시험에 대한 사후 분석을 수행했다.[41][44][46]

**결과**:
- **ADAS-Cog11 (18개월 평가)**: 대조군 크기 33% 감소
- **CDR-SB (12개월 평가)**: 대조군 크기 19% 감소  
- **대안적 검정력 증가**: ADAS-Cog11로 최대 10% 개선(80% → 90%)

**타임라인 영향**: 한 내부 분석에서 TwinRCT 3.0은 전통적 ANOVA와 동일한 통계 검정력을 23% 더 적은 참가자로 달성하여 등록 시간을 약 5개월 단축했다.[27]

#### AbbVie: 알츠하이머병 Phase 2 사후 분석

Unlearn은 완료된 Phase 2 알츠하이머병 시험 데이터셋에서 디지털 트윈의 통합을 입증했다.[41][44]

**결과**:
- **전체 표본 크기**: 96주차 CDR-SB 치료 효과 추정 시 10-15% 감소
- **검정력 강화**: ADAS-Cog11로 7% 개선(80% → 87%)
- **설계 효율성**: 더 작은 코호트로 동등한 통계 검정력 달성 능력 검증

[chart:114]

#### Trace Neuroscience: ALS Phase 1/2 임상시험(2025)

Trace Neuroscience는 ALS에서 UNC13A 표적 안티센스 올리고뉴클레오타이드 치료의 Phase 1/2 시험 설계를 최적화하기 위해 Unlearn과 파트너십을 체결했다.[42][47]

**디지털 트윈 생성기(DTG) 사양**:
- 13,000개 이상의 종단적 ALS 임상 기록에서 훈련
- 데이터 소스: APST 연구 플랫폼, PRO-ACT 데이터베이스, 미국 동북부 ALS 컨소시엄(NEALS)
- 표준 치료 및 위약 조건 하에서 질병 진행 예측

**적용**: 포함/제외 기준 및 치료 효과 감지 가능성을 최대화하기 위한 임상 종점 선택을 포함한 프로토콜 의사결정을 알린다.[42][47]

### D. 기술 아키텍처

#### 신경 볼츠만 기계(Neural Boltzmann Machine, NBM)

Unlearn의 독점 신경망 아키텍처는 중요한 임상 요구사항을 다룬다: 단일 종점 예측보다는 여러 동시 결과 예측.[22][34]

**기능**:
- 20개 이상의 임상 결과 동시 예측(검사실 수치, 생활 징후, 바이오마커, 기능 평가)
- 결과 간의 관계 포착(상관관계, 인과관계)
- 미래 상태의 확률 분포 생성, 점 추정치 아님
- 생리 복잡성을 반영하는 포괄적인 "질병 궤적" 모델링 활성화[34]

#### 모델 검증 & 투명성

Unlearn은 FDA 준수 신뢰도 실행을 구현한다:[24]

1. **사전 명시**: 모델 아키텍처, 하이퍼파라미터 및 입력값이 시험 개시 전에 "직렬화되고 잠금"
2. **결정성**: ML 모델이 소프트웨어 테스트를 통해 동일한 입력에 대해 동일한 출력을 생성함을 증명
3. **추적 가능성**: 모든 모델 실행이 버전 관리되고, 타임스탐프 표시되며, 표준 소프트웨어 개발 생명주기(SDLC)를 통해 추적됨
4. **설명 가능성**: 예측 점수를 추진하는 주요 기준선 변수를 식별하기 위한 해석 가능성 기법 사용
5. **감사 추적**: 21 CFR Part 11에 따른 기준선 입력값에서 예측 공변량까지의 데이터 변환에 대한 전체 문서화[24]

---

## III. 의료기기 디지털 트윈 적용

### A. FEops HEARTguide: 구조 심장 중재시술

FEops HEARTguide는 임상 사용을 위한 가장 성숙한 FDA 승인 디지털 트윈 시스템으로, 중재시술 계획에 대한 여러 규제 승인을 달성했다.

#### 규제 승인

| **날짜** | **경로** | **적응증** | **기기** |
|:---:|:---:|:---:|:---:|
| 2021년 10월[87][89] | De Novo | LAAO 계획 | Boston Scientific WATCHMAN™ |
| 2022년 4월[85][87] | 510(k) | 여러 기기를 이용한 LAAO | Abbott Amulet, Boston Scientific Watchman FLX |
| 2023년 6월[100] | 510(k) | AI 지원 해부학적 분석 | TAVI & LAAO 워크플로우 |

**FDA 승인 전 임상 사용**: FDA 시장 진입 전 EU, 영국, 캐나다 및 호주에서 완료된 2,000개 이상의 LAAO 및 TAVI 사례로, 안전성 및 유효성의 실질적인 실제 증거를 확립.[85][87]

#### 기술 및 임상 워크플로우

FEops HEARTguide는 이미징(일반적으로 CT 또는 TEE)에서 파생된 심장 해부학의 환자별 디지털 트윈을 생성한다. 이 시스템은 다음을 가능하게 한다:

1. **가상 기기 모델링**: 다양한 기기 크기 및 임플란트 위치의 시뮬레이션
2. **해부학-기기 상호작용 예측**: 기기가 개별 환자의 해부학과 어떻게 상호작용할지의 시각화
3. **중재시술 계획 최적화**: 수술 전 최적의 기기 크기 및 위치 선택[85]

**보고된 임상 결과**:
- 기기 선택을 위한 강화된 중재시술 확신
- 재배치 필요성을 줄인 효율적이고 "문제없는" 중재
- "처음부터 올바르게" 기기 선택

#### 규제 경로: De Novo vs. 510(k)

FEops는 특이한 규제 진행 과정을 거쳤다: FDA는 초기에 De Novo 분류를 부여했고(진정으로 새로운 소프트웨어 기능 인정), 이후 추가 기기 조합과 강화된 AI 분석에 대한 510(k) 제출을 수락했다.[87][89] 이 경로는 실질적인 임상 성능 데이터가 안전성 및 유효성 주장을 뒷받침할 때 FDA의 유연성을 보여준다.

### B. inHEART AI: 심장 디지털 트윈 분할(2024년 3월)

inHEART는 심장 이미지 분할을 자동화하는 AI 기반 소프트웨어 모듈에 대해 FDA 510(k) 허가를 획득했다—심장학의 환자별 디지털 트윈 생성을 위한 기초 계층.[104]

**임상 영향**:
- 심실 빈맥(VT) 제거 수술 시간 60% 단축
- 기존 계획 방법과 비교하여 VT 재발률 38% 감소
- 적용: 심장 리듬 장애 치료 계획

이 허가는 AI 이미지 분석이 디지털 트윈 생성을 가능하게 하는 경로를 예시하며, 모델링을 넘어 반자동화된 환자 표현형까지 확장한다.

### C. Siemens Healthineers & Mayo Clinic 파트너십(2025년 9월)

최근 협력은 디지털 트윈과 실시간 임상 워크플로우의 새로운 통합을 보여준다: AI 강화 심혈관 모델이 환자별 치료 반응을 시뮬레이션하고, 실시간 EHR 데이터가 지속적인 모델 업데이트를 공급한다.[104]

---

## IV. 제조 디지털 트윈 구현

### A. Eli Lilly: 고형제 제조(2024 사례 연구)

Eli Lilly는 Siemens NX와 Aspen Hybrid Models를 사용하여 고형제 제조 라인의 디지털 트윈을 구축했다.[72]

**접근 방식**:
- 중요 공정 파라미터 모델링: 습도, 혼합기 속도, 과립 수분, 정제 압축
- 가상 "무엇-만약" 시나리오 테스트 수행
- 가상 예측을 실제 배치 데이터에 대해 검증

**결과**:
- **공정 개발 시간 30% 단축**
- 2024년에 3건의 스케일업 편차 회피
- 물리적 실패 없이 개발에서 제조로의 전환 가속화

**규제 이점**: 실험 편차 감소는 FDA 검사 조사결과를 지원한다; 가상 검증은 21 CFR Part 211(적절한 제조 관행) 기대와 일치하는 사전 예방적 Quality-by-Design(QbD) 구현을 입증한다.[55]

### B. Takeda: 실시간 방출 검사(오사카 제조)

Takeda는 일본의 의약품의료기기청(PMDA)으로부터 승인을 받은 오사카 시설에서 실시간 방출 검사(RTRT)를 위해 클라우드 기반 다변량 모델링을 구현했다.[72]

**기술 스택**:
- 인라인 근적외선(NIR) 분광계
- Raman 분광계 센서  
- 클라우드 기반 AI 다변량 모델
- 정제 방출을 위한 자동화된 의사결정 알고리즘

**성능**:
- **타임라인**: 압축 후 1시간 내에 압축실에서 정제 방출(전통적 48-72시간 분석 검사 대비)
- **운전자본 이점**: 약 €4백만 재고 해방(검사 대기 재고 감소)
- **규제 상태**: PMDA 승인 디지털 트윈이 실시간 제조 의사결정을 지원

**21 CFR Part 11 준수**: 클라우드 기반 모델은 감사 추적, 보안 접근 제어 및 데이터 백업/재해 복구를 포함한 검증된 전자 시스템이 필요하다—Takeda의 구현은 디지털 데이터 무결성과 함께 적절한 제조 관행을 유지한다.[102]

### C. Eli Lilly & Merck: Purdue 컨소시엄(2025년 1월)

Eli Lilly와 Merck는 Young Institute 제약 제조 컨소시엄을 발표했으며, "스마트 AI" 및 디지털 트윈을 통합하는 고급 제조에 대한 전략적 연구를 시작했다.[71][80]

**초점 분야**:
- 자율 생물약학 제조 시스템
- 디지털 모니터링이 있는 무균 충전 마무리 공정
- 공정 최적화를 위한 생성형 AI
- 예측 장비 유지 관리를 위한 기계 학습

**산업 맥락**: ABI Research는 디지털 트윈 및 데이터 분석에 대한 제약 지출이 7년 동안 27% 증가하여 2030년까지 $12억에 도달할 것으로 예상하며, 이는 산업 전반의 약속을 반영한다.[105]

---

## V. 규제 준수: 21 CFR Part 11 & 전자 기록

### A. 디지털 트윈 시스템에 대한 적용 가능성

21 CFR Part 11은 규제된 활동을 위해 디지털 트윈 모델 또는 그 출력이 전자 형식으로 생성, 유지 또는 보관될 때마다 적용된다.[102][108]

**촉발 조건**:
- 규제 제출물(IND, NDA, BLA, 기기 510(k), De Novo)을 지원하기 위해 사용된 전자 기록
- 기존 규칙(적절한 제조 관행, GLP, GCP) 하에서 유지되어야 하는 기록이 전자 형식으로 됨
- 규제된 활동을 수행하기 위해 의존하는 전자 기록(종이 출력물만 생성하는 경우가 아님)

**하이브리드 시스템**: 조직은 전자 및 종이 기록을 모두 유지할 수 있다; Part 11은 전자 버전에만 적용된다.[3][102]

### B. 핵심 기술 및 절차 요구사항

#### 전자 서명
- 최소 두 개의 별개 식별 구성요소(ID 코드 + 비밀번호)
- 고유한 로그인 필요—위임 서명 불가
- 각 서명에는 인쇄된 이름, 날짜/시간 및 서명 사유가 포함되어야 함[3]
- 서명할 때마다 비밀번호 입력 필요(지속적인 로그인 아님)[3]

#### 감시 추적
- 디지털 트윈 데이터에 대한 모든 수정사항의 컴퓨터 생성, 타임스탬프 기록
- 변경 순서, 사용자 신원, 날짜/시간 및 사유 문서화 필요
- FDA는 기존 선행 규칙이 동등한 정보를 문서화할 경우 특정 11.10(e) 및 (k)(2) 요구사항에 대해 집행 재량권을 행사한다[9]

#### 데이터 무결성
- 기록이 기록 생명주기 전체에 걸쳐 내용과 의미를 정확하게 반영해야 함
- 데이터 변환(모델 입력)이 무결성을 보존하는지 검증
- 전자 기록 보존을 위한 백업 및 재해 복구 절차

### C. 디지털 트윈 특정 준수 요소

**모델 신뢰도 문서화**:
- 특정 사용 맥락에 대한 모델 성능을 입증하는 검증 보고서(FDA 프레임워크에 따른 요구사항)[56]
- 수치 알고리즘이 올바른지 보여주는 코드 검증
- 모델 버전 및 배포의 추적 가능성

**데이터 소스 인증**:
- 디지털 트윈이 역사적 환자 데이터 또는 관찰 데이터셋을 통합하는 경우, 이러한 소스 기록도 Part 11 표준을 충족해야 함
- 데이터 조화 및 정리 단계는 감사 추적으로 문서화되어야 함
- 데이터의 제외 또는 수정 사항에는 동시적인 정당화가 필요함

**시스템 검증**:
- 상업용 소프트웨어(예: Unlearn Platform, Siemens NX, Aspen Hybrid Models)는 Part 11 준수 문서를 제공해야 함
- 사용자 정의 디지털 트윈 구현에는 IQ/OQ/PQ(설치/운영/성능 적격성) 필요

---

## VI. 경쟁 환경 및 산업 채택

[chart:115]

### A. 주요 디지털 트윈 개발자

**Unlearn.AI**는 임상시험 디지털 트윈에서 시장 리더로 남아 있으며, 다음을 보유하고 있다:
- EMA 승인 + FDA 일치
- $130M 이상의 총 자금 조달(Series A-C)
- 파트너십: J&J, AbbVie, Merck KGaA, Trace Neuroscience, ProJenX, QurAlis
- 질병별 모델: 알츠하이머병, ALS, 고혈압, 파킨슨병(개발 중)
- 기술: Neural Boltzmann Machines + PROCOVA 방법론

**FEops**는 구조 심장 기기 계획에서 지배적이다:
- 2,000개 이상의 FDA 승인 전 사례
- 여러 FDA 규제 승인
- 지리적 범위: EU, 영국, 캐나다, 호주, 미국

**inHEART**는 심장 이미지 분석 및 디지털 트윈 기초 생성에 특화

### B. 제약회사 채택 상태

| 회사 | 적용 | 단계 | 발표 연도 |
|:---:|:---:|:---:|:---:|
| Johnson & Johnson | 알츠하이머병 Phase 3 | 구현됨 | 2024 |
| AbbVie | 알츠하이머병 Phase 2 | 구현됨 | 2024 |
| Merck KGaA | 면역학 Phase 2/3 | 활성 협력 | 2022 |
| Trace Neuroscience | ALS Phase 1/2 | 계획 중 | 2025 |
| ProJenX | ALS Phase 1 | 파트너십 | 2024 |
| Roche | 여러 적응증 | 탐색/파일럿 | 2025 |

### C. 채택의 장애물

규제 명확성에도 불구하고 Roche 경영진은 2025년 후반에 참된 최종 게임 적용(완전히 환자 생리학을 시뮬레이션)이 여전히 "지평선상에" 있다고 강조했다.[107] 현재 제한 사항:

1. **데이터 이질성**: Unlearn의 기술 스택 중 상당한 노력(80%)이 필요한 연구 간 및 소스 간 데이터 조화[34]
2. **역사적 편향**: 훈련 데이터가 과거 환자 모집단을 반영할 수 있어 특정 인구통계의 대표성 부족을 지속할 수 있음[107]
3. **설명 가능성 문제**: "블랙박스" ML 모델에 대한 규제 수용이 개선되고 있지만 투명성은 여전히 복잡함[2]
4. **다중 오믹스 통합**: 임상 데이터와 함께 유전체, 단백체 통합은 아직 초기 단계[107]
5. **타임라인**: Roche는 임상시험 최적화를 위한 "견고하고 확장 가능한 디지털 트윈 도구"까지 5-7년으로 추정[107]

---

## VII. 비교 규제 접근 방식: EMA vs. FDA

### A. EMA의 사전 예방적 승인 프로그램

EMA가 먼저 움직였으며, PROCOVA에 대해 2022년 5월에 초안 승인 의견을 발급했고 2022년 9월에 최종 의견을 발급했다.[21][25][84] 이는 상업 배포 전에 방법론을 사전 승인하는 EMA의 의료기기 개발 도구(MDDT) 인접 접근 방식을 나타낸다.

**장점**:
- 산업에 명확한 수용 가능성 신호
- 규제 불확실성을 줄이는 사전 경쟁 지침
- 여러 후원사에게 서빙하는 단일 승인

**상태**: 피벗 시험에서 ML 기반 표본 크기 감소를 공식 승인한 첫 번째 규제 기관

### B. FDA의 위험 기반 지침 접근 방식

FDA는 다음을 통한 개별화되고 위험 기반 입장을 취한다:

1. **2023년 11월 CM&S 지침**: 모든 모델에 적용 가능한 프레임워크, 디지털 트윈에만 국한되지 않음
2. **PROCOVA 일치(2024년 1월)**: Unlearn의 방법론이 기존 공변량 조정 지침에 맞음을 확인
3. **Q-Submissions**: 제출 전 회의를 통한 초기 단계 규제 피드백
4. **2025년 1월 AI 지침 초안**: 사전 COU 정의 및 신뢰도 평가 강조

**장점**:
- 혁신에 대한 유연성(처방적이지 않음)
- 기존 통계 프레임워크와의 통합
- 투명성 및 검증 강조

**제약**: 경우별 후원사 참여 필요; EMA 접근 방식보다 덜 예측적인 산업 신호

### C. 주요 일치

두 규제 기관은 중심 원칙에서 수렴한다:
- **사용 맥락 특수성**: 디지털 트윈은 정확한 의사결정을 위해 승인되어야 함
- **신뢰도 증거보다 신성성**: ML 알고리즘이 잘 검증되면 수용 가능
- **1형 오류 제어**: 통계적 무결성 유지(거짓 양성 비율 상승 없음)
- **인간 감시**: AI 모델이 규제 의사결정을 알려주지만 자동화하지는 않음

---

## VIII. 2025 전망: 새로운 표준 및 모범 사례

### A. 디지털 트윈 컨소시엄 제약 워킹 그룹

2024년 말에 출범한 Digital Twin Consortium의 제약 및 규제 워킹 그룹은 신약 생명주기 전반에 걸쳐 산업 표준을 확립하고 있다:[101]

**우선 사항**:
- 구현 모범 사례에 대한 백서
- 규제 고려사항 및 데이터 개인정보 보호 프레임워크
- 국제 조화(EU, 미국, 일본, 캐나다)
- 사용 사례 저장소 및 교훈

**범위**: 발견, 개발, 제조, 전달, 규제 준수

이 워킹 그룹은 FDA와 EMA 프레임워크만으로는 불충분함을 인정한다; 산업 주도 표준이 합의를 구축하면서 채택을 가속화한다.

### B. 새로운 적용(2025)

**헌팅턴병 시험**: Unlearn이 디지털 트윈을 외부 비교자 군으로 사용하는 명명되지 않은 글로벌 제약 회사와의 Phase 1b 시험에서 주요 참여를 발표했다—단순 대조군 강화를 넘어 합성 대조군 생성으로의 확장을 입증.[93]

**규제 연결 연구**: 디지털 트윈이 합성 비교자 군으로 기존 승인 의약품의 새로운 지역 시장으로의 도입을 가능하게 하는 표지판 확대 연구에 서빙.[93]

**종양학 초기 채택 프로그램**: Unlearn이 암 시험 설계 최적화를 위해 디지털 트윈을 사용하여 아집단 발견 및 저전력 분석에서 검정력 강화를 위한 이니셔티브 시작.[93]

### C. 제조 진화

Eli Lilly의 $270억 이상의 메가사이트 확장 전략은 NVIDIA Omniverse를 통합하여 제조 라인의 고해상도 디지털 트윈 시뮬레이션을 가능하게 하며, 물리적 구현 전 가상 공정 검증을 가능하게 한다.[55] 이는 디지털 트윈을 선택적 혁신이 아닌 표준 개발 도구로 사용하는 Pharma 4.0 채택을 나타낸다.

---

## IX. 제한사항 및 향후 연구 방향

### A. 알려진 격차

1. **장기 결과 예측**: 현재 디지털 트윈은 단기(12-18개월) 종점 예측에 우수; 시험 타임라인을 넘어선 연장 종단 예측은 아직 검증되지 않음

2. **메커니즘 모델링**: 디지털 트윈은 주로 통계적/상관적; 메커니즘(약동학/약력학) 모델과의 통합은 초기 단계

3. **비교 유효성**: 다양한 디지털 트윈 플랫폼의 직접 비교(Unlearn vs. 맞춤형 후원사 시스템 vs. 신흥 경쟁사)가 제한적

4. **실제 증거 통합**: 디지털 트윈이 역사적 시험 데이터를 활용하지만 전자 건강 기록의 실제 증거 통합은 방법론적으로 복잡

### B. 연구 우선순위(2025-2030)

- 국제 디지털 트윈 조화에 관한 FDA/EMA 협력 지침
- 다중 후원사 디지털 트윈 훈련을 위한 표준화된 데이터 형식
- 합성 디지털 트윈의 실제 시험 참가자에 대한 동의를 다루는 생의료 윤리 프레임워크
- 승인 후 모델 유지 관리를 위한 기계 학습 거버넌스

---

## 결론

FDA 준수 디지털 트윈 신약 개발은 실험적 개념 증명에서 확립된 규제 프레임워크, 실제 임상시험 구현 및 입증된 비용/시간 이점을 포함한 운영화된 방법론으로 전환되었다. EMA 승인(2022), FDA 지침 최종화(2023) 및 주요 제약 채택(2024-2025)의 수렴은 디지털 트윈을 임상 개발 최적화를 위한 표준 도구로 확립한다.

규제 준수는 세 가지 기둥에 달려 있다: (1) **위험 기반 신뢰도 평가**: FDA의 CM&S 프레임워크에 따라 모델 영향 및 의사결정 결과 정의; (2) **맥락 특정 검증**: 모델이 의도된 사용에 대해 안정적으로 수행함을 입증; (3) **21 CFR Part 11 준수**: 모델 생명주기 전체에 걸친 전자 기록 무결성 보장.

Eli Lilly의 제조 적용(공정 개발 가속화 30%) 및 Takeda(€4백만 재고 최적화)는 제약 운영에서 동등한 가치를 입증한다. 기기 적용(FEops, inHEART)은 디지털 트윈이 검증된 알고리즘으로 절차 계획을 향상시킬 때 빠른 FDA 허가 경로를 보여준다.

Roche가 인정한 "견고하고 확장 가능한" 도구까지의 5-7년 타임라인은 규제 장애가 아니라 데이터 조화, 편향 완화 및 생리 모델 완성에서의 공학 과제를 반영한다. 2025년에 디지털 트윈 프로그램을 시작하는 조직은 초기 FDA 참여, 데이터 거버넌스 인프라 및 입증된 규제 자격을 갖춘 기술 제공자(Unlearn.AI, Dassault Systèmes, FEops)와의 파트너십을 우선시해야 한다.

---

## 참고문헌

[1] Global Forum Diaglobal, "Virtual Patients, Real Results: How Digital Twins Are Reshaping Drug Development," 2024년 11월
[2] Hogan Lovells, "FDA's Evolving Regulatory Framework for AI Use in Drug & Device Clinical Trials," 2025년 1월
[3] Florence Healthcare, "FDA 21 CFR Part 11 Compliance," 2023년 4월
[4] NSF, NIH, FDA, "Digital Twin Biomedical Applications에 대한 $600만+ 자금," 2025년 8월
[5] BioXconomy, "Dassault Rolls Out FDA-Backed Guide on Using Virtual Twins in Device Trials," 2024년 11월
[6] Quality Magazine, "FDA 21 CFR Part 11 Complete Guide," 2025년 7월
[7] Clinical Trials Arena, "EMA Qualifies Unlearn's AI-Driven Approach for Smaller Trials," 2022년 9월
[8] Unlearn.AI, "How Unlearn Boosts Trial Power Using FDA's AI Framework," 2025년 6월
[9] FDA, "Part 11, Electronic Records; Electronic Signatures - Scope," 2018년 8월
[10] Government Technology Insider, "FDA Tackles Complex Mission with Digital Twin Technology," 2025년 6월
[11] Applied Clinical Trials, "New Regulatory Road in Clinical Trials: Digital Twins"
[12] FDA, "Using Artificial Intelligence & Machine Learning in Drug Development," 2023년 5월
[13] Stanford, "Using Real-World Data and Digital Twins," 2021
[14] Perceptive APC, "21 CFR Part 11 PharmaMV Compliance White Paper"
[15] Sciencedirect, "Transformative Roles of Digital Twins in Drug Development," 2025

[21] Clinical Trials Arena, "EMA Qualifies Unlearn's AI-Driven Approach," 2022년 9월
[22] Unlearn.AI Blog, "How Unlearn Boosts Trial Power," 2025년 6월
[23] LinkedIn, "How Unlearn.AI Using Digital Twins Disrupt Clinical Trials," 2025년 7월
[24] Unlearn.AI, "Establishing Credibility Whitepaper," 2025
[25] Unlearn, "Draft Qualification Opinion from European Medicines Agency," 2022년 5월
[26] Biopharma Trend, "Digital Twins in Rare Diseases," 2025년 9월
[27] Drug Discovery Trends, "Unlearn's Digital Twins Cut Clinical Trial Timelines," 2024년 3월
[28] Unlearn.AI, "US FDA Comments on PROCOVA Methodology," 2024년 1월
[29] Cromos Pharma, "Digital Twins in Clinical Research," 2024년 6월
[30] Drug Target Review, "AI Model Changing Clinical Trial Design," 2025년 6월
[31] Unlearn.AI, "Evidence: Case Studies and Collaborations," 2025
[32] Unlearn.AI Blog, "Reducing Placebo Burden: TwinRCTs," 2024
[33] Drug Discovery Trends, "Unlearn Slash Pharma Trial Costs," 2024년 10월
[34] Unlearn.AI, "Boosting Trial Efficiency with Generative AI," 2024년 10월
[35] Unlearn.AI Evidence Page, 2025
[36] Unlearn.AI Platform Overview, 2025년 4월
[37] LinkedIn, "FDA Comments on Unlearn's PROCOVA," 2024년 1월
[38] Unlearn Substack, "Digital Twin Generators for Hypertension," 2025
[39] Unlearn Blog, "FDA Comments on PROCOVA Methodology," 2025
[40] Unlearn, "Digital Twin Generators Overview," 2024년 12월

[41] Clinical Trial Vanguard, "Unlearn AI-Powered Clinical Trials with AbbVie and J&J," 2024년 7월
[42] ALS News Today, "Trace Plans ALS Trial with Unlearn AI Tools," 2025년 4월
[43] Neuroscience Central UK, "Digital Twin Brain Tech for Parkinson's," 2024년 12월
[44] Neuro-Central, "Unlearn Presents Studies on AI-powered Clinical Trials," Business Wire 프레젠테이션 인용
[45] MobiHealth News, "Digital Twin Company Unlearn Partners with Trace," 2025년 3월
[46] Neurology Live, "Utility of Digital Twin AI-Generated Models in Alzheimer's Trials," 2024년 8월
[47] Yahoo Finance, "Unlearn and Trace Neuroscience Partner to Optimize ALS," 2025년 4월
[48] PubMed Central, "Using AI-Generated Digital Twins to Boost Clinical Trial Power," 2024
[49] Alzheimer's Journal Wiley, "Using AI-Generated Digital Twins to Boost Clinical Trial," 2024
[50] PubMed Central, "Digital Twins for Health: Scoping Review," 2024년 3월

[55] LinkedIn, "Pharma's Virtual Future: Digital Twins in R&D and Manufacturing," 2025년 11월
[56] FDA, "Assessing the Credibility of Computational Modeling and Simulation in Medical Device Submissions," 2023년 11월
[57] Pharmanow Live, "Why Digital Twins Are Future of Pharma Manufacturing," 2024년 6월
[58] MDIC, "Landscape Report on Computational Modeling in Medical Device Development," 2023년 1월
[59] Covington Digital Health, "FDA Releases Discussion Paper on AI in Drug Development," 2023년 9월

[70] CenterWatch, "FDA's Role of AI in Regulatory Decision-Making for Drugs & Biologics," 2025년 10월
[71] Purdue University, "Purdue, Lilly, Merck Launch Young Institute Pharmaceutical Manufacturing Consortium," 2025년 2월
[72] Pharmaceutical Online, "Small Molecule Pharma Companies Employing Advanced Technologies," 2025년 5월
[73] FDA, "Considerations for the Use of Artificial Intelligence," 2025년 1월
[74] Merck Group, "Digital Twins: Accelerating R&D, Manufacturing & Supply Chains," 2023년 2월
[75] FDA News, "FDA Eliminates Major Barrier to Using Real-World Evidence," 2025년 12월
[76] Covington Digital Health, "FDA Medical Product Centers Continue Focus on AI," 2024년 3월
[77] Intuition Labs, "Pharma Digital Transformation: Industry Leaders," 2026년 1월
[78] Axtria, "FDA's Final Guidance on RWE/RWD for Drug Regulatory," 2023년 11월
[79] FDA News, "FDA Proposes Framework to Advance Credibility of AI Models," 2025년 5월
[80] Fierce Pharma, "Lilly, Merck Team with Purdue on Drug Production Methods," 2025년 1월
[81] FDA, "Use of Real-World Evidence for Medical Device," 2025년 12월
[82] Federal Register, "Considerations for Use of AI to Support Drug Approval," 2025년 1월
[83] GMPP Academy, "European Medicines Agency Qualifies AI-Powered Method," 2022
[84] GMPP Academy, "EMA Qualifies AI-powered Method for Smaller Trials," 2022
[85] FEops, "FEops HEARTguide Receives FDA Clearance for LAAO," 2022년 4월
[86] Health Economics, "Unlearn and Merck Collaborate on Medical Twins Trials," 2022년 3월
[87] Cardiovascular News, "FEops Heartguide Receives FDA Clearance," 2022년 4월
[88] Clinical Trials Arena, "Unlearn and Merck KGaA Collaborate to Expedite Immunology Trials," 2022년 7월
[89] FEops, "FEops Authorized by FDA for LAAO Planning," 2021년 10월
[90] Radical VC, "Unlearn.AI: Transforming Clinical Trials," 2024년 1월
[91] MRCT Center, "Use Cases Digital Twins and Synthetic Data," 2025년 11월
[92] FDA, "K223855 FEops HEARTguide 510(k)," 2022
[93] Unlearn.AI Blog, "Driving Clinical Trial Innovation with Partners," 2025년 10월
[94] FEops, "Press Releases," 2022년 11월
[95] BioSpace, "Unlearn Signs Multi-Year Collaboration with Merck KGaA," 2022
[96] Unlearn Blog, "Reflecting on EMA Draft Qualification Opinion," 2022

[101] Digital Twin Consortium, "Pharma & Regulatory Working Group," 2024년 12월
[102] Leica Microsystems, "Introduction to 21 CFR Part 11," 2025년 1월
[103] Quality Magazine, "How to Launch Digital Twin Strategy for Quality Control," 2023년 3월
[104] Delve Insight, "Digital Twins in Healthcare Industry," 2025년 10월
[105] Azilen, "Digital Twins for Optimizing Pharmaceutical Production," 2025년 6월
[106] The BioScan, "Digital Twin in Pharma Manufacturing," 2025
[107] Clinical Trials Arena, "Digital Twins for Clinical Trials: Early Days, Rapid Momentum," 2025년 11월
[108] Critical Manufacturing, "How MES Enhances Manufacturing Efficiency with FDA 21 CFR," 2025년 5월
[109] Wiley Online Library, "Digital Twin Under Regulatory Quality-by-Design," 2025
[110] Applied Clinical Trials, "Power of Digital Twins in Predicting Clinical Trial Outcomes"
[112] Clinical Leader, "How Digital Twins Are Rewriting Clinical Trials," 2025년 9월
[113] Dassault Systèmes, "21 CFR Part 11 EU Annex 11 Position Paper," 2024