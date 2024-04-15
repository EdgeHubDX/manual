---
layout: default
grand_parent: Pages
parent: 로직 플로우
title: Function 노드
nav_order: 3
---

{: .no_toc }
# Function 기본노드

- TOC
{:toc}

## function
1. 노드 개요  
    수신 메시지에 대한 처리를 실시하는 JavaScript 코드(함수 본체)를 작성합니다.  
    입력되는 메시지는 msg라는 명칭의 JavaScript 객체로 전달됩니다. msg 오브젝트는 msg.payload 프로퍼티에 메시지 본체를 유지합니다.  
    일반적으로 코드에서는 msg 오브젝트를 반환합니다. 후속 flow의 실행을 정지하고 싶은 경우 msg 오브젝트를 반환하지 않습니다.  

2. 노드 사용  
    function 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![FUNCTION]({{ site.url }}/docs/pages/logic-flow/function/function-9.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![FUNCTION_EDIT]({{ site.url }}/docs/pages/logic-flow/function/functionedit-9.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 공백이 표시됩니다.
    - 라이브러리 열기: 저장되어 있는 라이브러리를 가져올 수 있습니다.
    - 라이브러리로 저장: 현재 작성된 함수를 저장할 수 있습니다.
    - 코드: JavaScript로 함수 내용을 작성합니다.
    - 출력 수: 출력 단의 개수를 설정합니다. 단일 메시지의 경우 첫 출력단에 접속된 노드에 전달됩니다. 출력 단의 개수가 다수인 경우 출력 메시지의 배열을 반환하도록 구성하며 배열 순서에 따라 출력단의 순서에 대응하여 출력됩니다.

3. 메시지 송신  
    Flow 내의 다음 노드에 메시지를 전달하기 위해서는 메시지를 반환(return msg)하거나, node.send(msg)를 호출합니다.  
    반환/send 대상은 다음과 같습니다.  
    - 단일 메시지 오브벡트 – 첫 출력에 접속된 노드에 전달합니다.  
    - 메시지 오브젝트의 배열 – 대응하는 출력에 접속된 노드에 전달됩니다.  
    메시지 배열이 출력 대상인 경우 복수의 메시지가 대응하는 출력으로 전달됩니다. 반환 값이 null 인 경우 메시지는 전달되지 않습니다.  
    ```js
    var msg1 = { payload: “msg01 – out1” };
    var msg2 = { payload: “msg02 – out2” };
    return [ msg1, msg2 ];
    ```

    ![FUNCTION_OUTPUT]({{ site.url }}/docs/pages/logic-flow/function/functionoutput-9.png)

4. 로그 출력과 에러처리  
    로그 정보의 출력, 에러 출력을 실행하려면 다음 함수를 사용합니다. 
    - node.log(“로그 메시지”)
    - node.warn(“경고”)
    - node.error(“에러”)
    catch 노드를 이용하여 에러를 처리할 수 있습니다. catch 노드로 처리하기 위해서는 msg를 node.error의 제2 인수로 전달합니다.  
    - node.error(“에러”, msg)  

## switch
1. 노드 개요  
    프로퍼티 값에 의해 메시지를 분류합니다. 수신한 메시지에 대해 지정된 룰을 순서대로 평가하여 매치된 룰에 대응하는 출력 포트에 메시지를 송출합니다.  
    룰을 모두 평가하거나 처음 매치된 룰에서 멈추는 것을 설정할 수 있습니다.  

2. 노드 사용  
    switch 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![SWITCH]({{ site.url }}/docs/pages/logic-flow/function/switch-10.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![SWITCH_EDIT]({{ site.url }}/docs/pages/logic-flow/function/switchedit-10.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, “switch” 단어가 표시됩니다.
    - 프로퍼티: 평가 룰의 대상을 설정합니다. msg, flow, global 컨텍스트 프로퍼티 등을 설정할 수 있습니다. 또한 JSONata expression 또는 환경 변수를 대상으로 설정할 수 있습니다.
    - 분류 룰: 분류 룰을 선택합니다. Value rule 또는 Sequence rule을 선택할 수 있습니다.
    - 비교 대상: 분류 룰에 따라 비교할 대상과 값을 설정합니다.
    - 출력단: 숫자는 출력단의 순서를 표시합니다. 예를 들어 1은 첫번째 출력단으로 출력됨을 의미합니다.  
    예) 두번째 룰을 만족하는 경우 메시지는 아래 그램의 func2로 전달됩니다.

    ![SWITCH_LINK]({{ site.url }}/docs/pages/logic-flow/function/switchlink-10.png)

    - 삭제버튼: 해당 항목을 삭제합니다.
    - +추가: 분류 룰 항목을 추가합니다.
    - 모든 조건을 적용: “모든 조건을 적용”과 “처음 맞은 조건으로 종료” 중에 선택할 수 있습니다. “모든 조건을 적용”을 설정한 경우, 조건에 맞는 모든 출력단으로 메시지를 전달합니다. “처음 맞는 조건으로 종료”를 설정한 경우, 조건에 맞는 항목을 만날 경우 해당 출력단에만 메시지를 전달하고 종료합니다.
    - 메시지열의 보정: 옵션을 지정하면, 매치한 각 룰에 대해 새로운 메시지를 생성합니다.

3. 분류 툴  
    분류 룰은 아래의 4개로 나뉩니다.  
    - Value rule: 지정된 프로퍼티에 대해 값을 평가합니다. 설정할 수 있는 룰에는 “==”, “!=”, “<”, “<=”, “>”, “>=”, “is true”, “is false”, “is null” 등이 있습니다.
    -	Sequence rule: 메시지 열에 대해 적용(메시지 열을 split 노드 등으로 생성), head, index between, tail 등 타입을 선택할 수 있습니다. Head는 앞에서부터 인덱스를, tail은 뒤에서부터 인덱스를 가리킵니다. Index between은 설정한 2개의 인덱스 사이의 메시지 열을 의미합니다.
    -	JSONata expression: 메시지 전체에 대해 평가를 수행하여 결과가 true인 경우에 매치
    -	그 외: 이 전의 룰에 매치되는 것이 없는 경우에 적용

## change
1. 노드 개요  
    메시지, flow context, global context의 프로퍼티를 변경, 삭제, 이동합니다. 룰을 여려개 지정한 경우, 정의된 순서로 적용됩니다.

2. 노드 사용  
    change 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![CHANGE]({{ site.url }}/docs/pages/logic-flow/function/change-11.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![CHANGE_EDIT]({{ site.url }}/docs/pages/logic-flow/function/changeedit-11.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 선택한 룰과 대상값이 표시됩니다.
    - 룰: 값의 대입, 값의 치환, 값의 삭제, 값이 이동 중 하나를 선택할 수 있습니다. 값의 치환을 선택할 경우 검색할 문자열과 치환 후의 문자열 항목이 표시됩니다.
    - +추가: 룰 항목을 추가할 수 있습니다. 

## range
1. 노드 개요  
    수치를 다른 범위 값으로 변환합니다.

2. 노드 사용  
    range 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![RANGE]({{ site.url }}/docs/pages/logic-flow/function/range-12.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![RANGE_EDIT]({{ site.url }}/docs/pages/logic-flow/function/rangeedit-12.png)

    - 프로퍼티: 메시지의 payload를 설정합니다. payload에는 수치를 지정합니다. 수치 이외를 지정한 경우에는 수치로 변환합니다. 변환할 수 없는 경우에는 에러를 발생합니다.
    - 동작: 수치를 변환하기 위한 동작은 3가지 중 선택할 수 있습니다.  
        - “msg.payload의 값을 확대/축소”: 수치를 선형 스케일링합니다. 결과 값은 노드에 설정한 범위 내로 한정하지 않습니다.  
        - “입력값의 범위외의 값을 최소값/최대값으로 확대/축소”: 값이 지정된 범위 밖의 값으로 변하지 않도록 합니다.  

        예) 입력값 범위: 0~99, 출력값 범위: 0~50인 경우, 100이 입력으로 들어오면 입력값 범위를 벗어나므로 출력 최대값 50으로 처리된다. 입력갑이 -1이 입력된 경우 출력값은 0으로 출력된다.
        - “입력값의 범위외의 값을 범위폭으로 나눈 나머지로 해서 확대/축소”: 결과를 범위폭으로 나눕니다.  

        예) 입력값 범위: 0~99, 출력값 범위: 0~50인 경우, 100이 입력으로 들어오면 입력값 법위를 벗어나므로 입력값 범위폭인 99으로 나눈다. 나머지 1을 출력값 범위에 확대/축소 처리하면 0.5가 출력된다. 
    - 입력값의 범위: 입력값의 최소값과 최대값을 입력합니다.
    - 출력값의 범위: 출력값의 최소값과 최대값을 입력합니다. 
    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 출력값의 범위가 표시됩니다

## template
1. 노드 개요  
    템플릿에 기초하여 프로퍼티를 설정합니다.

2. 노드 사용  
    template 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TEMPLATE]({{ site.url }}/docs/pages/logic-flow/function/template-13.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TEMPLATE_EDIT]({{ site.url }}/docs/pages/logic-flow/function/templateedit-13.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, “template” 단어가 표시됩니다.
    - 프로퍼티: 메시지의 payload를 설정합니다. 템플릿에 적용하기 위한 정보를 포함한 메시지 오브젝트입니다. 예) 메시지에 다음과 같은 JSON 객체를 설정할 수 있습니다.
    ```js
    msg = {
        date: "월요일",
        payload: {
            name: "홍길동"
        }
    };
    ```
    - 템플릿: 출력 메시지를 생성하기 위한 템플릿입니다. Mustache 형식을 기본값으로 이용합니다.
    Mustache 형식은 중괄호({}) 2개로 JSON 객체의 속성이름을 감싸도록 구성됩니다. 해당 속성의 값이 실제 메시지를 구성하는데 사용됩니다.

    예) 안녕하세요, {{payload.name}}씨. 오늘은 {{date}}입니다.

    - </>형식: 템플릿에서 나타나는 “/”를 Mustach템플릿으로 처리할 것인지, 평문으로 처리할 것인지 설정합니다. Mustache 템플릿 형식으로 설정한 경우 Mustache section의 종료 표시 식별자로 처리됩니다.
    - 출력형식: 평문, JSON, YAML 형식 중 선택할 수 있습니다.

    평문의 예) 안녕하세요, 홍길동씨, 오늘은 월요일입니다.

## delay
1. 노드 개요  
    노드를 통과하는 메시지를 지연, 혹은 유량을 제한합니다.

2. 노드 사용  
    delay 노드를 마우스로 끌어 작업영역에 놓습니다
    
    ![DELAY]({{ site.url }}/docs/pages/logic-flow/function/delay-14.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![DELAY_EDIT]({{ site.url }}/docs/pages/logic-flow/function/delayedit-14.png)

    - 동작: 메시지 지연 또는 메시지의 유량제한을 선택할 수 있습니다.

    메시지에 reset 프로퍼티를 임의의 값으로 설정하여 수신하게되면 노드가 유지하고 있는 모든 메시지를 클리어 합니다. Reset 수신 상태는 노드의 상태값으로 표시됩니다.
    ```js
    msg.reset = 1; 
    ```

    ![DELAY_10S]({{ site.url }}/docs/pages/logic-flow/function/delay10s-14.png)

    - 메시지 지연: 지연 시간은 고정값, 범위내의 난수값, 메시지 마다의 동적인 지정값 중 하나를 지정할 수 있습니다.
    - 고정값: 고정값이 지난 후 큐에 쌓인 메시지를 처리합니다. 설정된 고정값은 노드 이름에 표시되며, 메시지가 큐에 쌓이면 상태값에 사각형이 표시됩니다

    ![DELAY_BOX]({{ site.url }}/docs/pages/logic-flow/function/delay10sbox-14.png)

    - 난수값: 설정된 범위 내에서 랜덤 값을 생성하여 지연 시작을 설정하게 됩니다.

    ![DELAY_EDIT]({{ site.url }}/docs/pages/logic-flow/function/delayrandomedit-14.png)

    위와 같이 설정된 경우, 15~20초 사이에서 랜덤 값을 생성하여 메시지를 지연시키게 됩니다.  
    생성된 랜덤 값은 노드의 상태값에 표시됩니다.  

    ![DELAY_RANDOM]({{ site.url }}/docs/pages/logic-flow/function/delayrandom-14.png)

    - 메시지 마다의 동적인 지정값: msg.delay에 지연 시간을 메시지 마다 설정합니다. 설정하는 시간은 밀리세컨드 값입니다. 변수에 설정된 지연 시간은 노드의 상태값에 표시됩니다.

    ![DELAYD_VARIABLE]({{ site.url }}/docs/pages/logic-flow/function/delayvariable-14.png)

    - 메시지의 유량제한: 메시지는 지정된 시간 간격내에 분산되어 송신합니다. 큐에 남은 메시지 수는 노드의 스테이터스에 표시됩니다. 받은 중간 메시지를 파기할 수 있습니다. 유량제한은 모든 메시지에 적용할 수도 있고, msg.topic값으로 그룹화하여 적용할 수도 있습니다. 그룹화하면, 중간 메시지는 자동적으로 파기됩니다. 지정한 시간 후에 큐 선두의 토픽 메시지를 출력할지, 지정한 시간 후에 큐에 있는 모든 토픽 메시지를 출력할지 설정할 수 있습니다

    ![DELAY_MESSAGE]({{ site.url }}/docs/pages/logic-flow/function/dealymessage-14.png) ![DELAY_MESSAGE2]({{ site.url }}/docs/pages/logic-flow/function/delaymessage2-14.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 현재 설정한 내용이 표시됩니다.  

   예) 유량제한 초당 1개의 메시지를 설정한 경우 “limit 1 msg/s”으로 표시됩니다.

## trigger 
1. 노드 개요  
    메시지를 송신하면 다른 메시지를 송신합니다. 지연 혹은 초기화가 지정되지 않은 경우에는 다음 2번째 메시지를 송신할 수도 있습니다.  
    reset 프로퍼티를 갖는 메시지를 받으면, 준비중인 대기나 반복을 클리어하여 메시지 송신은 실행되지 않습니다. Flow 내에서 타임아웃을 작성하는데 이용합니다.

2. 노드 사용  
    trigger 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TRIGGER]({{ site.url }}/docs/pages/logic-flow/function/trigger-15.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TRIGGER_EDIT]({{ site.url }}/docs/pages/logic-flow/function/triggeredit-15.png)

    - 송신 데이터: 초기 송신 데이터를 설정합니다. 없음을 설정할 수도 있습니다.
    - 송신후의 처리: 초기 송신 데이터를 송신한 후 다음 3개의 옵션을 설정할 수 있습니다.

    1. 초기화될 때까지 대기: trigger노드가 외부 메시지에 의해 트리거되면, 초기 송신 데이터를 송신한 후 reset을 대기합니다. Reset을 대기하는 상태는 노드의 상태 표시에 사각형으로 표시됩니다. 대기 중에는 외부에서 메시지가 수신되어도 아무런 동작을 수행하지 않습니다. msg.reset 속성을 갖는 메시지가 송신되면 외부 메시지에 의한 트리거를 대기하는 상태가 됩니다. 즉, trigger & block 형태로 동작하게 됩니다.

    ![TRIGGER_INIT]({{ site.url }}/docs/pages/logic-flow/function/trigger_init-15.png) ![TRIGGER_BLOCK]({{ site.url }}/docs/pages/logic-flow/function/triggerblock-15.png)

    2. 지정한 시간 대기: 노드의 기본값으로 설정되어 있는 옵션입니다. 초기 송신 데이터를 송신 후 설정한 시간을 대기합니다. 대기한 시간이 경과하면 재송신 데이터를 송신하게 됩니다. 예를 들어 초기 송신 데이터를 없음으로 설정하고 “새로운 메시지를 받앗을 때 지연을 연장”을 체크하게되면 타이머로 사용할 수 있습니다. 
    
    예) 센서 데이터가 10초마다 수신되어야한다면, 10초가 경과하여도 데이터 메시지가 수신되지 않으면 “타임아웃 발생” 메시지를 송신하게 설정할 수 있습니다.

    ![TRIGGER_WAIT]({{ site.url }}/docs/pages/logic-flow/function/triggerwait-15.png)

    3. 지정한 시간 간격마다 송신을 반복: 지정한 시간마다 초기 송신 메시지를 반복하여 송신합니다. msg.reset 을 수신하면 동작이 reset되어 중지됩니다. Reset된 후에는 외부에서 메시지를 수신하면 재시작하게 됩니다.
    
    ![TRIGGER_REPLAY]({{ site.url }}/docs/pages/logic-flow/function/triggerreplay-15.png)

    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 현재 설정한 내용이 표시됩니다.

   예) 5초마다 재송신을 설정한 경우 “resend every 5s”으로 표시됩니다.

## exec
1. 노드 개요  
    시스템 커맨드를 실행하여 출력을 반환합니다. 커맨드 완료까지 기다릴지, 커맨드가 출력을 실행할 때마다 메시지를 출력할지 지정할 수 있습니다. 실행대상의 커맨드는 노드의 설정 혹은 수신 메시지에서 지정합니다.

2. 노드 사용  
    exec 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![EXEC]({{ site.url }}/docs/pages/logic-flow/function/exec-16.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![EXEC_EDIT]({{ site.url }}/docs/pages/logic-flow/function/execedit-16.png)

    - 커맨드: 실행할 시스템 커맨드를 입력합니다. 커맨드 혹은 파라미터가 공백을 포함하는 경우에는 앞뒤에 인용부를 붙입니다.
    - 인수: 커맨드의 인수값을 설정합니다. mag.payload를 인수로 설정할 수 있습니다. 
    - 출력: 출력 메시지 표시 방식을 선택할 수 있습니다.
        - 커맨드 종료시-exec모드: 출력 메시지는 커맨드의 실행이 완료된 후 출력됩니다.
        - 커맨드 실행 중-spawn모드: 1행이 실행될 때마다 출력 메시지를 반환합니다.	
    - 타임아웃: 지정한 시간(초) 이내에 커맨드가 완료되지 않는 경우, 프로세스를 자동적으로 정지합니다.
    - 이름: 노드에 표시되는 이름을 설정합니다. 이름이 없을 경우, 현재 설정한 커맨드 내용이 표시됩니다.
    - 출력: exec 노드는 3개의 출력단을 가지고 있습니다.
        - 표준출력(stdout): 커맨드의 표준 출력
        - 표준 에러 출력(stderr): 커맨드의 표준 에러 출력
        - 반환코드(return code): 리턴코드, message, signal 프로퍼티를 포함하는 오브젝트
    
    ![EXEC_LINK]({{ site.url }}/docs/pages/logic-flow/function/execlink-16.png)

    - 프로세스 정지: msg.kill을 수신하면, 실행 중인 프로세스를 정지할 수 있습니다. msg.kill에는 송출할 시그널 종류를 지정할 수 있습니다. 예를 들면, SIGINT, SIGQUIT, SIGHUP 등입니다. 빈 문자열이 지정된 경우에는 SIGTERM을 지정한 것으로 간주됩니다. 노드가 1개 이상의 프로세스를 실행하고 있는 경우, msg.pid에 정지 대상의 PID 를 지정해야 합니다

## rbe
1. 노드 개요  
    RBE(예외 보고) 노드 - 페이로드가 변경된 경우에만 데이터를 전달합니다. 값이 지정된 양만큼 변경되지 않는 한 차단하거나 무시할 수도 있습니다(dead 와 narrowband 모드)

2. 노드 사용  
    rbe 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![RBE]({{ site.url }}/docs/pages/logic-flow/function/rbe-17.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![RBE_EDIT]({{ site.url }}/docs/pages/logic-flow/function/rbeedit-17.png)

    - Mode: payload의 값이 변경된 경우 다음 노드로 메시지를 전달합니다. 변경이 없으면 차단됩니다. 설정할 수 있는 모드는 다음과 같습니다.
        1. 값이 변하지 않으면 차단
        2. 값이 변하지 않으면 차단, 단 초기값은 무시
        3. 설정한 값보다 크거나 같게 값이 변하지 않으면 차단
        4. 설정한 값보다 크게 값이 변하지 않으면 차단
        5. 설정한 값보다 크거나 같게 값이 변하면 차단
        6. 설정한 값보다 크게 값이 변하면 차단

