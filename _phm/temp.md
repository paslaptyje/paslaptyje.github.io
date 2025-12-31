---
title: "Introduction"
layout: single
toc: true
toc_sticky: true
---

---
# 기본 개념
---

- Prognostic and Health Management(PHM): 시스템의 실제 작동 조건 하에서 실시간으로 건전성 상태를 평가하고, 최신 정보를 바탕으로 미래 상태를 예측하는 새로운 엔지니어링 접근 방식

- Condition Based Maintenance(CBM): 장비의 실제 상태(Actual Condition)를 기반으로 정비를 수행하는 방식
 
다음의 순서로 유지보수 전략은 발전해왔다.

1. corrective maintenance(고장 정비): 고장 발생 후 수리
    장점: 예비 부품의 소모량이 가장 낮다 (고장난 부품만 교체).
    단점: 유지보수에 소모되는 시간이 가장 높다 -> 가동 중단으로 인한 비용이 가장 높다

2. time-based preventive maintenance(예방 정비): 주기적으로 유지보수를 실행
    장점: 부품들의 고장 시점이 비슷할 경우 효과적
    단점: 교체가 불필요한 부품들의 교체로 인해 낭비되는 비용이 발생할 수 있음
                

고장 부품이 적다 -> corrective maintenance(고장 정비)가 유리

고장 부품이 많다 -> time-based preventive maintenance(예방 정비)가 유리

---
PHM의 주요 단계
---

데이터 획득(data acquisition) -> 진단(diagnostics) -> 예지(prognostics) -> 건전성 관리(health management)

데이터 획득(data acquisition) : 센서로부터 데이터 획득 & 전처리
진단(diagnostics)            : 이상치를 데이터를 기반으로 결함 탐지, 결함들을 분류, 고장 임계값(failure threshold) 대비 심각도(severity)를 계산
예지(prognostics)            : 현재 운용 조건에서 고장까지의 시간 예측
건전성 관리(health management): 정비 일정, 물류 지원 관리


상태기반정비를 위한 개방형 시스템 아키텍처(Open System Architecture for Condition Based Maintenance, OSA/CBM)

아래와 같은 6계층으로 구성된다.

1. Data acquisition     : 센서로 데이터 측정/수집
2. Data manipulation    : 원시 데이터 전처리/가공(필터링, 변환, 특징 추출의 입력 준비 등)
3. Condition monitoring : 상태지표 계산, 이상 경보(alarm) 제공
4. Health assessment    : 상태지표로 건전성 상태를 정량화(“얼마나 나쁜가”)
5. Prognostics          : 미래 열화 진행 추정, RUL 등 예측
6. Decision-making      : 교체/정비 조치 및 계획 수립(정비 의사결정)



















---
# 용어 정리집
---
## PHM 및 정비 전략 관련

PHM (Prognostics and Health Management)
예지 및 건전성 관리. 센서/데이터/모델을 통해 현재 건전성 진단 + 미래 고장 예측 + 정비 의사결정까지 포함하는 프레임워크.

Maintenance strategy (정비 전략)
정비를 “언제/어떻게” 할지에 대한 운영 방식(사후/예방/상태기반 등).

Lifecycle cost (수명주기 비용, Life-cycle cost)
장비 도입~폐기까지 전체 기간에 걸친 총비용(정비·부품·다운타임·인력·기회비용 포함).

Corrective maintenance
고장정비/사후정비. 고장 발생 후 수리/교체(reactive, unscheduled, passive).

Preventive maintenance
예방정비/시간기반 계획정비. 상태와 무관하게 사전에 정한 주기대로 수행(scheduled, active).

Time-based maintenance: 예방정비를 “시간/주기”로 정의한 표현.

CBM (Condition-Based Maintenance)
상태기반정비. 설비 상태에 따라 “필요할 때만” 수행. PHM과 결합 시 predictive/proactive 성격이 강화됨.

Predictive maintenance / Proactive
예측정비 / 선제적. 단순히 상태를 보고 대응하는 수준을 넘어, 미래를 예측해 정비를 계획(스케줄링)하는 뉘앙스.

Traditional reliability engineering
전통적 신뢰성 공학. 고장률, MTBF, 과거 데이터/핸드북 기반으로 정비 주기 설계.

## 상태/열화 및 고장 관련

Health state (건전성 상태)
장비가 “정상에 얼마나 가까운지”를 나타내는 상태(정상/열화/고장 임박 등).

Degradation (열화)
시간에 따라 성능이 점진적으로 악화되는 과정. 고장(failure) 이전의 “진행”을 강조.

Stress / Load (응력/하중)
열화·고장에 영향을 주는 운용 조건의 부담 요소.

Fault (결함/고장 징후)
시스템 내부 이상 상태. 반드시 즉시 failure(기능 상실)로 이어지진 않음(결함→열화→고장으로 진행 가능).

Failure (고장, 기능 상실)
시스템/구성품이 의도된 기능을 더 이상 수행하지 못하는 상태.

Failure threshold (고장 임계값)
측정 지표가 이 값(또는 조건)을 넘으면 “고장으로 판단”하는 기준선.

Anomaly (이상, 이상 징후)
정상 패턴에서 벗어난 관측/행동. “결함 원인”일 수도 있고 “일시적 변동”일 수도 있어 진단이 필요.

Severity (심각도)
결함/열화가 임계값 대비 어느 정도 진행됐는지의 정도(경미~심각).

## 진단(Diagnostics) 관련

Detection (탐지)
이상/결함이 “있는지 없는지”를 찾아내는 단계.

Isolation (격리/분리/국소화)
이상이 발견되었을 때 어느 구성품/어느 원인인지 범위를 좁히는 과정.
(현장에서는 “원인(또는 부위) 식별” 의미로도 쓰임)

Identification (식별/동정)
무엇이 문제인지(모드/원인/고장 형태)를 구체적으로 규명하는 단계.
isolation보다 더 구체화된 표현으로 쓰이기도 함.

## 예지(Prognostics) 및 시간 지표

Prognostics (예지)
현재 상태와 운용 조건을 바탕으로 미래 열화 경향/고장 시점을 예측.

RUL (Remaining Useful Life)
잔여 유효수명. “지금부터 고장(임계값 도달)까지 남은 시간/사이클”.

Time to failure (TTF)
고장까지의 시간. 의미상 RUL과 유사하게 쓰이지만, 문맥에 따라 기준이 달라질 수 있어(임계값 정의) 문서 내 정의 확인이 중요.

Current operating condition (현재 운용 조건)
같은 상태라도 하중/속도/온도 등 운용 조건에 따라 RUL 예측이 달라짐(조건 의존성 강조).

## Health management(건전성 관리) 및 운영/정비 의사결정

Maintenance scheduling (정비 스케줄링)
“언제 정비할지” 계획(가동률, 생산계획, 위험도, 자원 제약 포함).

Logistics support (물류 지원)
부품 조달, 재고, 인력 배치, 정비 창구/도구 준비 등 정비 실행을 가능케 하는 지원 체계.

Risk mitigation (위험 완화)
고장으로 인한 시스템 수준 리스크(안전/비용/다운타임)를 사전에 줄이는 조치.

Extend useful life (유효 수명 연장)
불필요한 조기 교체를 줄이고, 안전 범위 내에서 장비 사용 기간을 늘리는 것.

## 용어 통일 “권장 번역” 요약(빠른 참조)

Diagnostics: 진단

Prognostics: 예지

Health management: 건전성 관리

Condition-based maintenance (CBM): 상태기반정비

Preventive maintenance: 예방정비(시간기반 계획정비)

Corrective maintenance: 고장정비(사후정비)

Anomaly: 이상(징후)

Fault: 결함/고장 징후

Failure: 고장(기능 상실)

Failure threshold: 고장 임계값

Severity: 심각도

RUL: 잔여 유효수명

