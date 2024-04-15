---
layout: default
grand_parent: Pages
parent: 태그
title: 태그 / 그룹 관리  
nav_order: 4
---

{: .no_toc }
# 태그 / 그룹 관리  
태그 리스트 위의 다음과 같은 메뉴를 통해서 태그/그룹을 추가, 수정, 복사, 삭제, 정보확인 가능합니다.

- TOC
{:toc}

1. 추가 버튼  
  - 해당 버튼을 통해 `그룹` 또는 `태그`를 추가할 수 있습니다.   
  ![TAG_ADD]({{ site.url }}/docs/pages/tag/tag-and-group/tagaddbtn-1.png)

2. 테이블 더보기 버튼  
  - 더보기 메뉴에서 `정보, 수정, 삭제, 복제` 할 수 있습니다.  
  ![TAG_MORE]({{ site.url }}/docs/pages/tag/tag-and-group/tagmore-1.png)

3. Toggle & OPEN  
  - Toggle이 `Edit`인 경우, `OPEN` 클릭 시, Edit창이 표시됩니다.  
  - Toggle이 `Lock`인 경우, `OPEN` 클릭 시, Info창이 표시됩니다.  
  ![TAG_TOGGLE]({{ site.url }}/docs/pages/tag/tag-and-group/tagtoggle-1.png)

4. 트리 더보기 
  - `그룹정보, 그룹 수정, 그룹 삭제, 하위 그룹 추가, 하위 태그 추가` 사용가능 합니다.  
  ![TAG_TREE]({{ site.url }}/docs/pages/tag/tag-and-group/tagatree-1.png)

5. 리스트 삭제  
  - 복수개의 리스트를 선택하면, 삭제 버튼이 활성화 됩니다.  
  ![TAG_LIST]({{ site.url }}/docs/pages/tag/tag-and-group/taglist-1.png)

  {: .note }
  `CTRL + A`로 전체 선택을 사용할 수 있습니다.  
  `SHIFT + Click`으로 여러개를 선택할 수 있습니다.  
  `CTRL + Click`으로 다중선택할 수 있습니다.  
  `첫번째 행을 클릭` => `SHIFT + END` 로 전체선택할 수 있습니다.

## 그룹
태그를 논리적으로 폴더와 같은 그룹을 사용해 편리하게 관리할 수 있습니다. 

### 그룹 추가  
1. 그룹 `추가 버튼/데이블 더보기/트리 더보기`를 눌러 그룹을 추가할 수 있습니다.  

  ![GROUP_ADD]({{ site.url }}/docs/pages/tag/tag-and-group/groupadd-1.png)

### 그룹 수정  
1. 그룹 `Toggle Edit/테이블 더보기/트리 더보기`를 눌러 그룹을 수정할 수 있습니다.  

    ![GROUP_EDIT]({{ site.url }}/docs/pages/tag/tag-and-group/groupedit-2.png)

2. `확인` 버튼을 클릭하면 수정이 완료됩니다.

### 그룹 정보  
1. 그룹 `Toggle Lock/테이블 더보기/트리 더보기`를 눌러 그룹정보를 조회할 수 있습니다. 

  ![GROUP_INFO]({{ site.url }}/docs/pages/tag/tag-and-group/groupinfo-3.png)

### 그룹 삭제  
1. 그룹 `리스트 삭제/데이블 더보기/트리 더보기`를 눌러 그룹을 삭제할 수 있습니다. 

2. `확인` 버튼을 클릭하면 삭제가 완료됩니다.

    ![GROUP_DELETE]({{ site.url }}/docs/pages/tag/tag-and-group/groupdelete-4.png)


## 태그

### 태그 추가  

1. 태그 `추가 버튼/데이블 더보기/트리 더보기`를 눌러 태그를 추가할 수 있습니다.  
  ![TAG_ADD]({{ site.url }}/docs/pages/tag/tag-and-group/tagadd-5.png)  

2. 태그 타입별로 등록할 수 있습니다.  
  - Analog  
    ![TAG_ANALOG]({{ site.url }}/docs/pages/tag/tag-and-group/tag-analog-5.png)  
  - Digital  
    ![TAG_DIGITAL]({{ site.url }}/docs/pages/tag/tag-and-group/tag-digital-5.png)  
  - String  
    ![TAG_STRING]({{ site.url }}/docs/pages/tag/tag-and-group/tag-string-5.png)  

3. Alarm Toggle 버튼을 On 하면, 하위 설정 정보가 활성화 됩니다.  
  ![TAG_ALARM]({{ site.url }}/docs/pages/tag/tag-and-group/tagalarm-5.png)  

    - 입력 제한 조건(Analog 타입 )

      | 태그 타입       | 입력가능 항목정의 |
      |----------|----|
      | 알람 이벤트 | 알람처리 플래그가 체크가 되어있어야 합니다. |
      | 지연시간 | 0이상의 숫자만 입력 가능합니다. |
      | 데드밴드 | 0이상의 숫자만 입력 가능합니다. |
      | 알람 레벨 | 선택 가능합니다. |
      | 발생 메시지 | 선택 가능합니다. |
      | 복구 메시지 | 선택 가능합니다. |
      | 사용자 지정 메시지1 | 선택 가능합니다. |
      | 사용자 지정 메시지2 | 선택 가능합니다. |
      | 사용자 지정 메시지3 | 선택 가능합니다. |
      | 사용자 지정 메시지4 | 선택 가능합니다. |
      | 경계알람 | 선택 가능합니다. |
      | HH 경계 | 숫자만 입력 가능합니다.<BR/>태그 최대값을 초과하거나, 최소값 미만일 수 없습니다.<BR/>HI값이 설정되어 있는경우 HI보다 작을 수 없습니다.<BR/>태그타입이 아날로그 타입이어야 합니다.|
      | HI 경계 | 숫자만 입력 가능합니다.<BR/>태그 최대값을 초과하거나, 최소값 미만일 수 없습니다.<BR/>HH값이 설정되어 있는경우 HH보다 클 수 없습니다.<BR/>LO값이 설정되어 있는경우 LO값보다 작을 수 없습니다.<BR/>태그타입이 아날로그 타입이어야 합니다.|
      | LO 경계 | 숫자만 입력 가능합니다.<BR/>태그 최대값을 초과하거나, 최소값 미만일 수 없습니다.<BR/>HI값이 설정되어 있는경우 HI보다 클 수 없습니다.<BR/>LL값이 설정되어 있는경우 LL값보다 작을 수 없습니다.<BR/>태그타입이 아날로그 타입이어야 합니다.|
      | LL 경계 | 숫자만 입력 가능합니다.<BR/>태그 최대값을 초과하거나, 최소값 미만일 수 없습니다.<BR/>LO값이 설정되어 있는경우 LO보다 클 수 없습니다.<BR/>HH, HI, LO 알람값이 하나라도 존재해야 합니다.<BR/>태그타입이 아날로그 타입이어야 합니다.|
      | 변화량 알람 | Analog 타입만 설정 가능합니다.<BR/>설정은 가능하나 변화값 입력은 필수가 아닙니다.|
      | 변화값 | 0이상의 숫자만 입력 가능합니다. |
      | 이격 알람 | 선택 가능합니다. |
      | 이격 기준 | 선택 가능합니다. |
      | 기준값 | 이격 알람 선택 시 문자/숫자 포함 입력가능합니다. |
      | 주 이격값 | 1이상의 숫자만 입력 가능합니다. |
      | 보조 이격값 | 1이상의 숫자만 입력 가능합니다.<BR/>주 이격값보다 작아야 합니다.<BR/>1부터 태그 최대값까지 유효합니다.|

    - 입력 제한 조건(Digital 타입)

      | 태그 타입       | 입력가능 항목정의 |
      |----------|----|
      | 지연시간 | 0이상의 숫자만 입력 가능합니다. |
      | 데드밴드 | 0이상의 숫자만 입력 가능합니다. |
      | 알람 레벨 | 선택 가능합니다. |
      | 발생 메시지 | 선택 가능합니다. |
      | 복구 메시지 | 선택 가능합니다. |
      | 사용자 지정 메시지1 | 선택 가능합니다. |
      | 사용자 지정 메시지2 | 선택 가능합니다. |
      | 사용자 지정 메시지3 | 선택 가능합니다. |
      | 사용자 지정 메시지4 | 선택 가능합니다. |
      | 알람 타입 | 선택 가능합니다. |

4. Operation(연산식) Toggle On 하면, 하위 설정 정보가 활성화 됩니다.
  - Class가 Memory(메모리 태그)인 경우에만 설정 가능합니다.

    ![TAG_OPERATION]({{ site.url }}/docs/pages/tag/tag-and-group/tagoperation-5.png)  

5. Event Toggle On 하면, 하위 설정 정보가 활성화 됩니다.  
    ![TAG_EVENT]({{ site.url }}/docs/pages/tag/tag-and-group/tagevent-5.png)  

    - 입력 제한 조건

    | 태그 타입       | 입력가능 항목정의 |
    |----------|----|
    | 조건 | 선택 가능합니다.<BR/>없음: 기본값<BR/>값 변경시: Analog/Digital/String<BR/>값 증가시: Analog/Digital<BR/>값 감소시: Analog/Digital<BR/>조건식: Analog/Digital/String|
    | 조건식1 | `조건`에서 조건식이 선택되어야 합니다.|
    | 연산자 | `조건식1`을 설정할 경우 설정 가능합니다.|
    | 조건식2 | `연산자`가 `AND, OR` 일 경우 설정 가능합니다.<BR/>콤보내용은 `조건식1`과 동일합니다. |

6. TAG 정보를 각각의 그룹별로 입력 후 `확인` 버튼을 눌러 태그 정보를 저장합니다  
  - 저장된 TAG정보는 태그관리 TREE 영역과 태그목록에 실시간 반영되어 Display 됩니다.
  - 등록된 TAG 정보는 엔지니어링에 활용되어 이후 모니터링 대상 자료로 활용됩니다.


### 태그 수정
1. 태그 `Toggle Edit/테이블 더보기/트리 더보기`를 눌러 태그를 수정할 수 있습니다.  

    ![TAG_EDIT]({{ site.url }}/docs/pages/tag/tag-and-group/tagedit-6.png)

### 태그 정보
1. 태그 `Toggle Lock/테이블 더보기/트리 더보기`를 눌러 태그정보를 조회할 수 있습니다. 

    ![TAG_INFO]({{ site.url }}/docs/pages/tag/tag-and-group/taginfo-7.png)

### 태그 삭제
1. 태그 `리스트 삭제/데이블 더보기/트리 더보기`를 눌러 태그를 삭제할 수 있습니다. 

    ![TAG_DELETE]({{ site.url }}/docs/pages/tag/tag-and-group/tagdelete-8.png)

### 태그 복제
1. 태그 `테이블 더보기`에서 태그 복제 버튼을 클릭하여 태그를 복제할 수 있습니다.

2. 해당 기능을 활용하여, `기존 태그 설정정보`에서 `태그명`만 변경하여 `다른 태그로 저장`할 수 있습니다.

![TAG_COPY]({{ site.url }}/docs/pages/tag/tag-and-group/tagcopy-9.png)

### 태그 옵션 설정  
1. 테이블 상단의 `더보기` 버튼을 클릭합니다.  

2. `태그 옵션 설정` 버튼을 클릭합니다.  

    ![TAG_OPTION]({{ site.url }}/docs/pages/tag/tag-and-group/tagoption-10.png)

3. `ANALOG TAG DATA, DIGITAL LABELS, ALARM MESSAGES` 3가지 탭이 있습니다.  

  ![TAG_OPTION]({{ site.url }}/docs/pages/tag/tag-and-group/tagoption-pop-10.png)

  {: .highlight }
  ✅ **ANALOG TAG DATA**: `Analog Data Units(데이터 단위)`를 추가하고 삭제할 수 있습니다.   
  ✅ **DIGITAL LABELS**: `Digital On Labels, Digital Off Labels`를 추가하고 삭제할 수 있습니다.  
  ✅ **ALARM MESSAGES**: `Alarm Occurence Messages(알람 발생 메시지), Alaram Recovery Messages(알람 복구 메시지), Alarm Custom Messages(사용자 지정 메시지)` 를 추가하고 삭제할 수 있습니다. 
