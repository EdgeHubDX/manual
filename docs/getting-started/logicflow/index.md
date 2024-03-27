---
layout: default
parent: Getting started
title: LogicFlow
nav_order: 3
---

<div style="border-left: 5px solid #20C997; backgroud: #868E96;">
    <blockquote> 
        <h1>11. LogicFlow</h1>
    </blockquote> 
</div>
LogicFlow는 DataWorX의 구성요소 중 하나입니다. 추가 가능한 다양한 노드(컴포넌트)를 활용하여 흐름관계로 구성하고, 이벤트 기반의 모델링을 통해 사용자가 필요로 하는 데이터 조회, 가공, 입력 등의 기능을 빠르게 구현할 수 있으며, 작성된 어플리케이션은 런타임 중 편집과 배포가 가능 하도록 되어 있습니다.
LogicFlow는 Nodejs런타임 환경에서 구동이 가능하며, Html5지원 브라우저에서 편집기 사용이 가능합니다.

## 11.1 LogicFlow 편집기

### 11.1.1 개요

1. 기능
   - 다양한 기능의 기본 노드를 제공하며, 필요시 추가로 노드를 설치할 수 있습니다
   - DataWorX의 태그 인터페이스를 사용할 수 있습니다.
   - LogicFlow의 실시간 데이터를 외부 DB로 내보낼 수 있습니다.
2. 구성
   LogicFlow편집기는 웹브라우저 상에서 동작하며, LogicFlow런타임에서 동작 할 플로우를 작성할 수 있는 다양한 기능을 제공합니다.

LogicFlow 편집기의 화면 구성에 대한 설명은 다음과 같습니다.
팔레트: 플로우 작성시 사용 가능한 노드의 목록이며, 작업영역에 마우스로 끌어넣어 사용할 수 있습니다.
작업영역: 추가된 노드의 위치, 속성, 흐름 연결 등을 작성할 수 있는 탭 영역으로, 플로우 단위로 이루어져 있습니다.
속성영역: 선택된 노드의 도움말 또는 속성 설정값을 변경하는 화면이 표시됩니다.
배포버튼: 플로우 내용을 편집 후 배포하기 버튼을 누르면, 변경내용이 반영된 런타임 동작이 수행됩니다.
메뉴버튼: 메뉴버튼을 눌러 팔레트관리 및 편집기 환경설정을 변경할 수 있습니다. 3. 실행 4. 다국어 지원 5. 추가 노드의 설치
추가 라이브러리 노드를 사용할 수 있으며, [메뉴] – [팔렛트 관리] – [팔렛트]에서 다운로드 및 설치가 가능합니다.

{: .note}

> LogicFlow 화면이 정상적으로 나타나지 않을 경우 브라우저의 새로고침(F5) 기능을 이용하여 화면을 다시 표시할 수 있습니다.
> LogicFlow 연동 설정 방법은 4.1.4의 (3)번 “LogicFlow 설정”을 참고해주시기 바랍니다.

## 11.2 DataWorX 전용노드

### 11.2.1 tag value 노드

1.  노드 개요<BR/>
    노드에 입력이 발생할 때 마다, DataWorX의 태그값을 읽어 플로우로 가져오는 노드입니다.
    태그 및 태그그룹을 선택할 수 있으며, 아래 형태의 실시간 태그값이 msg.payload로 출력됩니다.

    | 속성   | 내용         | 타입                                                                                                     |
    | :----- | :----------- | :------------------------------------------------------------------------------------------------------- |
    | name   | 태그이름     | string                                                                                                   |
    | value  | 태그값       | string OR number OR boolean                                                                              |
    | kind   | 태그종류     | string<BR/>(analog, digital, string, structure, block, group)                                            |
    | type   | 값타입       | string<BR/>(null, bool, int8, int16, int32, int64, uint8, uint16, uint32, uint64, float, double, string) |
    | status | 태그상태     | number                                                                                                   |
    | uptime | 업데이트시각 | date                                                                                                     |

2.  노드 사용<BR/>
    tag value노드를 마우스로 끌어 작업영역에 놓습니다.

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    - 태그 커넥션: DataWorX와 실시간 태그 값을 주고 받기 위해서는 연결 설정을 하여야 합니다.
    - 이름: 플로우 편집 화면에 표시될 이름을 설정합니다.
    - 출력형식: 출력으로 내보낼 태그값 모음의 형태를 설정합니다.
    - 태그목록: 가져올 태그 이름 목록입니다. “추가” 버튼을 클릭하여 태그를 선택할 수 있습니다.

    {: .note}

    > 태그값 출력 형식은 “오브젝트”,“연관배열” 두가지 형태가 있으며, 그림과 같은 경우
    >
    > “오브젝트’일때 “msg.payload.OBSERVER.Ana1”로,
    >
    > “연관배열’일때 “msg.payload[‘OBSERVER.Ana1’]”로 태그값을 읽을 수 있습니다.

3.  태그 선택기<BR/>
    “태그선택” 버튼을 클릭하면 태그선택 팝업이 표시됩니다.

    원하는 태그 또는 태그그룹을 선택 후 “목록에 추가” 버튼을 클릭하여 태그목록에 추가합니다.<BR/>
    태그목록의 정리가 완료되면 “선택확인” 버튼을 사용하여 설정에 적용합니다.<BR/>
    여러 항목을 선택하기 위해 “shift” 및 “ctrl”키를 사용할 수 있습니다.<BR/>

    {: .note}

    > 태그목록 항목에 태그를 지정하는 경우 태그값 오브젝트를 가져오며,
    > 태그그룹을 지정하는 경우 하위의 모든 태그 오브젝트를 가져옵니다.

4.  globalContext의 사용<BR/>
    tag value 노드는 흐름 연결과 별개로 업데이트 되는 실시간 태그값을 globalContext에 반영하며,
    “global.tag.태그이름”을 사용하여 다른 노드에서 태그 값을 참조 할 수 있습니다.