---
layout: default
grand_parent: Pages
parent: 로직 플로우
title: Common 노드
nav_order: 2
---

{: .no_toc }
# Common 노드

- TOC
{:toc}

## inject
1. 노드 개요  
    수동 또는 일정 간격으로 메시지를 전송하여 flow를 시작 시키는 역할을 수행합니다.  
    메시지 페이로드에는 문자열, 현재 시각, JavaScript 객체 등 다양한 값을 지정할 수 있습니다.  

2. 노드 사용  
    Inject 노드를 마우스로 끌어 작업영역에 놓습니다.  

    ![INJECTNODE]({{ site.url }}/docs/pages/logic-flow/common/injectnode-1.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.  

    ![INJECTNODE_EDIT]({{ site.url }}/docs/pages/logic-flow/common/injectedit-1.png)

    - 페이로드: 지정한 메시지 페이로드를 출력으로 사용하여 플로우를 시작합니다.
        페이로드의 기본값은 현재시각의 타임스탬프를 1970년 1월1일부터 경과한 밀리초로 표현한 값입니다. 문자열, 수치, 논리값, JavaScript오브젝트 등을 페이로드로 설정할 수 있습니다.
    - 토픽: 임의로 지정가능한 프로퍼티입니다. 데이터페이스 query 또는 MQTT의 토픽을 설정할 경우 사용할 수 있습니다.
    - 반복: 지정된 간격, 혹은 스케쥴에 따라 메시지를 송출하도록 설정합니다. “지정한 시간간격”, “지정한 시간간격, 일시”, “지정한 일시” 등을 설정할 수 있습니다.
    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우 페이로드 타입/값이 노드에 표시됩니다.


## debug
1. 노드 개요  
    사이드바의 '디버그'탭에 선택한 메시지 프로퍼티의 값을 표시합니다.  
    태그 및 태그그룹을 선택할 수 있으며, 아래 형태의 실시간 태그값이 msg.payload로 출력됩니다.  
    노드 우측의 버튼으로 출력을 On/Off 설정할 수 있습니다.  

2. 노드 사용  
    debug 노드를 마우스로 끌어 작업영역에 놓습니다.  

    ![DEBUG]({{ site.url }}/docs/pages/logic-flow/common/debugnode-2.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![DEBUG_EDIT]({{ site.url }}/docs/pages/logic-flow/common/debugedit-2.png)

    - 대상: 출력 대상을 설정합니다. 기본값은 메시지 페이로드입니다. 지정한 프로퍼티 또는 메시지 전체를 출력할 수 있습니다.
    - 출력대상: 기본값은 디버그 창입니다. 시스템 콘솔이나 노드의 상태로 출력하도록 선택할 수 있습니다
    - 노드의 상태로 표시된 예)

         ![DEBUG_OUTPUT]({{ site.url }}/docs/pages/logic-flow/common/debugoutput-2.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우 출력으로 설정된 값이 노드에 표시됩니다.
    
## complete
1. 노드 개요  
    complete 노드에 설정한 노드가 메시지 처리를 마쳤을 때 런타임에 알리면 complete 노드는 연결된 flow를 트리거 할 수 있습니다.  

2. 노드 사용  
    complete 노드를 마우스로 끌어 작업영역에 놓습니다.  

    ![COMPLETE]({{ site.url }}/docs/pages/logic-flow/common/completenode-3.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.  

    ![COMPLETE_EDIT]({{ site.url }}/docs/pages/logic-flow/common/completeedit-3.png)

    - Select nodes: 화면에서 노드를 선택할 경우 사용합니다.
    - 리스트: 화면에 삽입된 노드 리스트를 표시합니다. 체크박스를 설정하면 해당 노드의 종료를 기다립니다.  
        다수를 설정하면 OR 조건으로 어느 하나의 노드가 완료되면 동작합니다. 
        설정한 노드에서 사용하거나 구성한 msg를 complete 노드에 연결된 다음 노드에서 가지고 와서 처리할 수 있습니다.  
        이메일 전송 노드와 같이 출력 포트가 없는 노드와 함께 사용할 수 있습니다. 단, 모든 노드가 이 이벤트를 지원하는 것은 아닙니다.  
        Node-RED 1.0에 도입된 대로 이 기능을 지원하도록 구현되었는지 여부에 따라 다릅니다.  

## catch
1. 노드 개요  
    같은 탭내의 노드가 송출한 에러를 캐치합니다. 메시지 처리중에 노드가 에러를 송출했을 경우,  
    플로우 실행은 기본적으로 정지합니다. 이 노드를 사용하면, 에러를 캐치하고 대응하는 플로우로 처리시킬 수 있습니다.  
    오류가 발생한 경우 msg.error 프로퍼티가 추가됩니다. error 프로퍼티의 내용은 다음과 같습니다.  

    | 프로퍼티 이름       | 내용          |
    | :----------- | :---------------- |
    | error.message           | 에러 메시지 |
    | error.source.id | 에러를 보낸 노드의 id   |
    | error.source.type           | 에러를 보낸 노드의 종류     |
    | error.source.name          | 에러를 보낸 노드의 명칭(설정되어 있는 경우) |


2. 노드 사용  
    catch 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![CATCH]({{ site.url }}/docs/pages/logic-flow/common/catchnode-4.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![CATCH_EDIT]({{ site.url }}/docs/pages/logic-flow/common/catchnodeedit-4.png) ![CATCH_DETAIL]({{ site.url }}/docs/pages/logic-flow/common/catcheditdetail-4.png)

    - 에러 취득처: 모든 노드로부터 에러를 취득하는 것이 기본 설정입니다.  
        “모든 노드”로 설정 시 “Catch노드로 처리된 에러를 무시” 체크 박스를 설정할 수 있습니다. 이는 다른 Catch 노드에서 처리한 에러를 무시하겠다는 의미입니다.  
        에러 취득처를 “선택  한 노드”로 설정한 경우 노드를 선택할 수 있는 리스트가 표시됩니다.  
    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, “모두” 또는 선택한 노드의 개수가 catch 단어와 함께 표시됩니다.

## status
1. 노드 개요  
    같은 탭내 노드의 상태 메시지를 취득합니다. 기본값으로는, 같은 워크스페이스 탭내의 모든 노드의 스테이터스를 취득합니다.  
    특정 노드의 스테이터스를 취득 대상으로 설정할 수도 있습니다.   
    msg.status 프로퍼티의 내용은 다음과 같습니다.  

    | 프로퍼티 이름       | 내용          |
    | :----------- | :---------------- |
    | status.text           | 상태 문자열 |
    | status.source.type | 상태를 표시한 노드의 종류  |
    | status.source.id          | 상태를 표시한 노드의 id     |
    | status.source.name        | 상태를 표시한 노드의 명칭(설정되어 있는 경우) |

2. 노드 사용  
    status 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![STATUS]({{ site.url }}/docs/pages/logic-flow/common/statusnode-5.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![STATUS_EDIT]({{ site.url }}/docs/pages/logic-flow/common/statusedit-5.png) ![STATUS_DETAIL]({{ site.url }}/docs/pages/logic-flow/common/statuseditdetail-5.png)

    - 상태취득처: 모든 노드로부터 상태를 취득하는 것이 기본 설정입니다.  
        상태취득처를 “선택한 노드”로 설정한 경우 노드를 선택할 수 있는 리스트가 표시됩니다.
    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, “모두” 또는 선택한 노드의 개수가 status 단어와 함께 표시됩니다.

## link in
1. 노드 개요  
    Flow 간에 가상의 링크를 작성합니다. 임의의 탭 상에 존재하는 link out 노드에 접속할 수 있습니다.  
    link 노드를 선택하면 연결된 link 노드가 표시됩니다. link in의 설정 창에는 link out 노드들이 표시되며 체크하여 링크할 수 있습니다.  
    이 접속은 직접 링크한 것과 동일하에 작동합니다.  
    link out에서 출력한 메시지를 받아서 다음 노드에 전달하는 역할을 수행합니다.  

    ![LINKIN]({{ site.url }}/docs/pages/logic-flow/common/link-6.png) 

2. 노드 사용  
    link in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![LINKIN_NODE]({{ site.url }}/docs/pages/logic-flow/common/linknode-6.png) 

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![LINKIN_EDIT]({{ site.url }}/docs/pages/logic-flow/common/linkedit-6.png)

    - 이름: link out 노드의 리스트에 표시되는 이름을 설정합니다. 이름이 없을 경우, 임의의 영숫자 조합의 ID가 리스트에 표시됩니다.

## link out
1. 노드 개요  
    Flow 간에 가상의 링크를 작성합니다. 임의의 탭 상에 존재하는 link in 노드에 접속할 수 있습니다.  
    link 노드를 선택하면 연결된 link 노드가 표시됩니다. link out의 설정 창에는 link in 노드들이 표시되며 체크하여 링크할 수 있습니다.  
    이 접속은 직접 링크한 것과 동일하에 작동합니다. 메시지를 link in 노드에 전달하는 역할을 수행합니다.

    ![LINKOUT]({{ site.url }}/docs/pages/logic-flow/common/linkout-7.png)

2. 노드 사용  
    link out 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![LINKOUT_NODE]({{ site.url }}/docs/pages/logic-flow/common/linkoutnode-7.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![LINKOUT_EDIT]({{ site.url }}/docs/pages/logic-flow/common/linkedit-7.png)

    - 이름: link in 노드의 리스트에 표시되는 이름을 설정합니다. 이름이 없을 경우, 임의의 영숫자 조합의 ID가 리스트에 표시됩니다.

## comment
1. 노드 개요  
    Flow에 코멘트를 기술하기 위해 사용합니다. 이름과 내용을 입력할 수 있으며, 내용 항목은 사이드 패널에 표시됩니다.

2. 노드 사용  
    comment 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![COMMENT]({{ site.url }}/docs/pages/logic-flow/common/comment-8.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![COMMENT_EDIT]({{ site.url }}/docs/pages/logic-flow/common/commentedit-8.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, “comment” 단어가 표시됩니다.
    - 편집기: 일반 텍스트 기반의 경량 마크업 언어인 Markdown 형식으로 내용을 작성할 수 있습니다. 입력한 내용은 사이드 패널에 표시됩니다.
    
    ![COMMENT_PANEL]({{ site.url }}/docs/pages/logic-flow/common/commentpannel-8.png)


