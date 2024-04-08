---
layout: default
parent: Pages
title: 태그 모니터링
nav_order: 16
---

{: .no_toc }
# 태그 모니터링
실행 중인 프로젝트의 태그 값과 상태를 감시하거나 태그 값을 제어할 수 있습니다. 좌측 메인 내비게이션을 통해 해당 페이지로 이동할 수 있습니다.

- TOC
{:toc}

![Monitoring - Nav.](./monitoring-nav.png) 


## 1. 태그 목록
- 태그 목록은 태그 페이지와 구조가 거의 비슷합니다. 좌측의 서브 내비게이션 또는 테이블의 헤더를 통해 태그를 필터링할 수 있습니다.
- 태그 페이지와는 다르게 테이블은 툴바가 없으며, 모니터링을 위한 컬럼이 추가되어 있습니다.

![Monitoring](./monitoring.png) 


## 2. 태그 값/상태/업데이트 시간


### 2.1. 태그 값
- 현재 태그 값이 나타납니다.
<!-- TODO: `-` 에 대한 내용 작성하기 -->
- 태그 값에 시뮬레이션이 적용된 경우 다음과 같이 상태 앞에 아이콘 `SI`이 표기됩니다.

![Monitoring - Simulation Icon](./monitoring-simulation-icon.png) 


### 2.2. 태그 상태
- 
- 태그 상태에 대한 내용은 다음과 같습니다.

| 상태                         | 설명 |
| :--------------------------- | :-- |
| SCAN START : `[상세 내용]`    | |
| SCAN STOP                    | |
| -                            | |
| GOOD                         | |
| UNKNOWN                      | |
| IO BAD : `[상세 내용]`        | |
| ENG BAD : `[상세 내용]`       | |
| ANALOG ALARM : `[상세 내용]`  | |
| DIGITAL ALARM : `[상세 내용]` | |
| ALARM DELAY                  | |


### 2.3. 업데이트 시간
- 태그 값이 업데이트된 시간을 나타냅니다.


## 3. 태그 정보
- 테이블의 태그 아이템에 마우스를 올리면 태그 이름 컬럼의 우측에 `OPEN` 버튼이 나타납니다. 버튼을 클릭하면 우측 패널에서 태그 정보를 확인할 수 있습니다.

![Monitoring - Panel Open Button](./monitoring-panel-open-button.png) 

![Monitoring - Panel](./monitoring-tag-info-panel.png) 


## 4. 태그값 제어
- 태그 정보 패널에서 태그 정보 카드의 우측 하단에 있는 `태그값 변경` 텍스트 버튼을 클릭하면 태그값을 변경할 수 있습니다.

![Monitoring - Tag Value Edit Button](./monitoring-tag-value-edit-button.png) 

![Monitoring - Tag Value Edit Modal](./monitoring-tag-value-edit-modal.png) 

{: .note }
프로젝트가 실행 중일 때만 태그값을 제어할 수 있습니다.

