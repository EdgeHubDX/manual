---
layout: default
grand_parent: Pages
parent: 알람 매니저
title: 알람그룹 설정
nav_order: 2
---

{: .no_toc }
# 알람그룹 설정 
`알람그룹`은 태그를 논리적 집합으로 구분하고 관리 포인트 별로 일괄동작을 수행하기 위한 역할을 수행합니다.
`발생된 알람`은 유저가 알람그룹 별로 필터링하여 조회하거나 `LogicFlow`에서 처리 동작을 정의할 수 있습니다. 
메뉴 트리에서 `알람 매니저`를 선택합니다. 기존에 등록된 알람그룹이 있는 경우, 알람 매니저 트리의 하위 메뉴로` 알람그룹 리스트`가 표시됩니다.  
![ALARM_MANAGER]({{ site.url }}/docs/pages/alarm-manager/group/alarmmanger-1.png)

- TOC
{:toc}


## 알람그룹 속성 
`알람그룹 속성`은 다음과 같습니다.  

| 속성 | 설명 |
|----------|----|
|알람그룹 명| 필수 입력 항목으로서 알람그룹의 이름을 입력합니다.|
|알람그룹 설명| 알람그룹에 대한 설명을 입력합니다.|
|등급| 알람그룹의 등급을 입력합니다. `(1~10)`<BR/>태그 설정시 태그의 `알람 등급이 정해지지 않은 경우`에는 알람그룹의 등급을 사용합니다.|

{: .highlight }
하기 이미지는, `태그의 알람등급이 정해지지 않은 경우` 입니다.  

![ALARM_LEVEL]({{ site.url }}/docs/pages/alarm-manager/group/alarmlevel-1.png)

## 알람그룹 추가  

1. 알람그룹 `추가 버튼`을 클릭합니다.  

    ![ALARM_ADD]({{ site.url }}/docs/pages/alarm-manager/group/alarmadd-1.png)

2. 알람그룹 설정정보를 입력합니다.  

    ![ALARM_ADD_PANEL]({{ site.url }}/docs/pages/alarm-manager/group/alarmadd-panel-2.png)

3. 확인을 누르면 알람그룹이 저장됩니다.  


## 알람그룹 수정 

1. 알람그룹 수정은 `트리 더보기` 또는 `테이블 더보기` 또는 `Toggle Edit -> OPEN`으로 열 수 있습니다.  

![ALARM_EDIT]({{ site.url }}/docs/pages/alarm-manager/group/alarmedit-3.png)

2. 알람그룹 설정정보를 입력합니다.  

    ![ALARM_EDIT]({{ site.url }}/docs/pages/alarm-manager/group/alarmedit-panel-3.png)

3. 확인을 누르면 알람그룹 저장됩니다.  


## 알람그룹 정보  

1. 알람그룹 정보는 `트리 더보기` 또는 `테이블 더보기` 또는 `Toggle Lock -> OPEN`으로 열 수 있습니다.  

    ![ALARM_INFO]({{ site.url }}/docs/pages/alarm-manager/group/alarminfo-4.png)

2. 알람그룹 정보를 확인합니다.

    ![ALARM_INFO_PANEL]({{ site.url }}/docs/pages/alarm-manager/group/alarminfo-panel-4.png)


## 알람그룹 삭제

1. 알람그룹 삭제는 `트리 더보기` 또는 `테이블 더보기`에서 삭제할 수 있습니다.

    ![ALARM_DELETE]({{ site.url }}/docs/pages/alarm-manager/group/alarmdelete-5.png)

2. 버튼을 클릭하면, 삭제 확인 모달이 표시됩니다.

    ![ALARM_DELETE_PANEL]({{ site.url }}/docs/pages/alarm-manager/group/alarmdelete-panel-5.png)

3. 확인을 누르면 알람그룹 삭제 됩니다.
