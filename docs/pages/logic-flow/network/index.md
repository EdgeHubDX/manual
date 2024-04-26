---
layout: default
grand_parent: Pages
parent: 로직 플로우
title: Network 노드
nav_order: 4
---

{: .no_toc }
# Network 노드

- TOC
{:toc}

## mqtt in
1. 노드 개요  
    MQTT 브로커에 접속하여 지정한 토픽의 메시지를 구독합니다.

2. 노드 사용  
    mqtt in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![MQTTIN]({{ site.url }}/docs/pages/logic-flow/network/mqttin-18.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![MQTTIN_EDIT]({{ site.url }}/docs/pages/logic-flow/network/mqttinedit-18.png)

    - 서버: 우측의 편집 버튼을 클릭하면 서버 접속 설정을 생성할 수 있습니다. 서버 접속 설정은 mqtt in과 mqtt out에서 재이용할 수 있습니다

    1. 접속  

    ![MQTTIN_CONNECT]({{ site.url }}/docs/pages/logic-flow/network/mqttinconnect-18.png)

    - 서버: mqtt 브로커 서버의 주소를 입력합니다.
    - 포트: mqtt 브로커 서버의 포트를 입력합니다. 디폴트값은 1883 입니다.
    - 사용TLS: 인증서 기반의 암호화 통신할 경우 체크하여 인증서 설정을 추가할 수 있습니다. 체크하게되면 인증서 설정할 수 있는 편집 버튼이 표시됩니다.
    - 프로토콜: 프로토콜을 선택할 수 있습니다. V3.1, V3.1.1, V5 중에서 선택합니다.
    - 클라이언트: 클라이언트 ID를 입력합니다. ID를 자동생성하는 경우에는 입력하지 않습니다.
    - 킵 얼라이브 시간: Keep Alive는 초 단위로 측정 한 시간 간격입니다. 서버가 Keep Alive 시간 기간의 1.5 배 이내에 클라이언트로부터 Control Packet을받지 못하면 네트웍 연결이 끊어진 것처럼 Client 와의 연결을 끊습니다. 이 Keep Alive 값을 0으로 설정하면 연결 유지 매커니즘이 해제된다

    2. 세큐리티
    
    ![MQTTIN_SECURITY]({{ site.url }}/docs/pages/logic-flow/network/mqttinsecurity-18.png)

    - 유저: 사용자 ID를 입력합니다.
    - 패스워드: 사용자 암호를 입력합니다.

    3. 메시지
        
    ![MQTTIN_MESSAGE]({{ site.url }}/docs/pages/logic-flow/network/mqttinmessage-18.png)

    - 접속 시, 중단 시, 예기치 않은 중단 시 사용할 메시지를 설정합니다
    - 토픽: mqtt의 토픽을 입력합니다. “/”를 사용하여 계층을 구분합니다.
    - QoS: 통신 품질에 대하여 설정할 수 있습니다.
        - 0: 최대 1번 도착
        - 1: 1번 이상 도착
        - 2: 1번만 도착

## mqtt out
1. 노드 개요  
    mqtt 브로커에 접속하여 메시지를 발행합니다.

2. 노드 사용  
    mqtt out 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![MQTTOUT]({{ site.url }}/docs/pages/logic-flow/network/mqttout-19.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![MQTTOUT_EDIT]({{ site.url }}/docs/pages/logic-flow/network/mqttoutedit-19.png)

    - 서버: 우측의 편집 버튼을 클릭하면 서버 접속 설정을 생성할 수 있습니다. 서버 접속 설정은 mqtt in과 mqtt out에서 재이용할 수 있습니다.
    - 토픽: 발행 대상의 mqtt 토픽입니다. msq.payload의 값을 사용하여 발행하며 보통 단순한 텍스트 형태이지만, 바이너리 버퍼를 발행하는 것도 가능합니다.
    - QoS: 0: 최대 1번 도착, 1: 1번 이상 도착, 2: 1번만 도착
    - 보존: true인 경우 메시지를 브로커에 보존합니다. 브로커에 보존한 토픽을 클리어하려면, 보존 플래그를 설정하여 해당 토픽에 빈 메시지를 발행합니다.

    
## http in
1. 노드 개요  
    http 엔드 포인트를 작성하여 Web 서비스를 구성합니다.

2. 노드 사용  
    http in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![HTTPIN]({{ site.url }}/docs/pages/logic-flow/network/httpin-20.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![HTTPIN_EDIT]({{ site.url }}/docs/pages/logic-flow/network/httpinedit-20.png)

    - 메소드: GET, POST, PUT, DELETE, PATCH 등의 메소드를 선택할 수 있습니다.
        - GET: 리소스 조회에 사용
        - POST: 요청된 자원을 생성하기 위해 사용
        - PUT: 기존 정보를 UPDATE할 때 주로 사용
        - DELETE: 특정 리소스의 삭제를 요청하는데 사용
        - PATCH: 리소스를 부분적으로 UPDATE하는 경우 사용
    - URL: url은 /api의 상대 경로로 입력됩니다. 예) /user 로 입력하면 실제 서비스되는 url은 /api/user 가 됩니다.
    - 요청 메시지의 구성
        - msg.payload: GET 요청의 경우, 쿼리 파라미터로 구성된 오브젝트, 그 외의 경우 HTTP 요청의 본체를 가리킵니다.
        - msg.req: HTTP 요청 오브젝트, 다음과 같은 속성을 포함합니다.
    - body: 요청 본체
    - headers: HTTP 요청 헤더를 포함한 오브젝트
    - query: 쿼리 파라미터를 포함한 오브젝트 예) /user?id=userid&pasword=userpass 와 같이 구성된 경우, id,password 등의 쿼리 파라미터는 msg.req.query에 저장됩니다. 
    - params: route 파라미터를 포함한 오브젝트,   
        예) /user/:name 와 같이 이름있는 파라미터를 지정한 경우 해당 값은 msg.req.params에 저장됩니다.
    - cookies: 요청 쿠키를 포함한 오브젝트
    - files: POST 요청에서 파일의 업로드가 설정으로 유효화 되어 있는 경우, 업로드 대상 파일

## http response
1. 노드 개요  
    http In 노드에서 받은 요청에 대한 응답을 반환합니다. http in 노드로 시작하여, 응답 메시지를 구성하는 노드(예, function 노드)에서 응답 메시지를 구성한 결과를 받아서 응답을 요청한 곳으로 전송하는 역할을 수행합니다.

2. 노드 사용  
    http response 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![HTTPREP]({{ site.url }}/docs/pages/logic-flow/network/httpresponse-21.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![HTTPREP_EDIT]({{ site.url }}/docs/pages/logic-flow/network/httpresponseedit-21.png)

    - 상태코드: http 응답 상태 코드를 지정할 수 있습니다. 지정하지 않을 경우, msg.statusCode의 값이 사용됩니다.
    - 헤더: 헤더를 지정할 수 있습니다. “+추가” 버튼을 클릭하면 헤더 항목을 추가할 수 있습니다.
    - 입력 메시지의 구성
        - msg.payload: 응답 본체
        - msg.statusCode: 설정하면 응답 상태 코드로 합니다. 기본값은 200 입니다.
        - msg.headers: 설정하면 응답 HTTP 헤더로 합니다.
        - msg.cookies: 설정하면 쿠키를 설정 또는 삭제하기 위해 사용합니다. 쿠키를 삭제하려면 value에 null을 설정합니다.
            ```js
            mmsg.cookies = {
                name: ‘nick’,
                session: {
                    value: ‘1234’,
                    maxAge: 9000000
                }
            }

            ```

## http request
1. 노드 개요  
    http 요청을 송신하여 응답을 반환합니다.

2. 노드 사용  
    http request 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![HTTPREQ]({{ site.url }}/docs/pages/logic-flow/network/httpreq-22.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![HTTPREQ_EDIT]({{ site.url }}/docs/pages/logic-flow/network/httpreqedit-22.png)

    - 메소드: GET, POST, PUT, DELETE, PATCH 등의 메소드를 선택할 수 있습니다.
        - GET: 리소스 조회에 사용
        - POST: 요청된 자원을 생성하기 위해 사용
        - PUT: 기존 정보를 UPDATE할 때 주로 사용
        - DELETE: 특정 리소스의 삭제를 요청하는데 사용
        - HEAD: 웹 서버 다운 여부 또는 웹 서버 정보 확인을 위해 사용, 웹 서버는 헤더만 전송한다.
    - URL: 노드 설정에서 url 프로퍼티를 지정할 경우, mustache 형식의 태그를 포함할 수 있습니다.  
        예를 들어 url이 {% raw %} example.com/\{\{\{topic\}\}\} {% endraw %}인 경우, msg.topic의 값에 의해 치환작업을 자동적으로 실행합니다.
    - 페이로드: 입력 payload를 처리하는 방법을 설정합니다.
        - Ignore: 페이로드를 전송하지 않습니다.
        - Append to query-string paremeters: 쿼리 스트링 파라미터에 붙여 전송합니다.
        - Send as request body: 요청 본체로써 전송합니다.
    - SSL/TLS 접속을 유효화: 체크하면 보안 통신을 위한 인증서 정보를 설정할 수 있습니다.
    - 인증을 사용: 체크할 경우: 인증 종류와 Id/password를 설정할 수 있습니다. 인증이 필요한 사이트에 접속 시 적용할 수 있습니다.
    - Enable connection keep-alive: 체크하여 keep-alive 설정을 할 수 있습니다.
    - 프록시를 사용: 체크하면 프록시 정보를 설정할 수 있습니다.
    - 출력형식: UTF8문자열, 바이너리버퍼, JSON오브젝트 중 선택하여 설정할 수 있습니다. 
    - 입력 메시지 구성
        - url: 노드 설정에서 지정하지 않은 경우, 이 프로퍼티로 요청 url을 설정합니다.
        - method: 노드 설정에서 지정하지 않은 경우, 이 프로퍼티로 요청에 사용할 HTTP 메소드를 설정합니다. GET, PUT, POST, PATCH, DELETE 중 하나를 지정해 주시기 바랍니다.
        - headers: 요청의 HTTP 헤더를 지정합니다.
        - cookies: 설정하면 요청과 함께 쿠키를 보낼 수 있습니다.
        - payload: 요청 본체로써 보내는 데이터
        - rejectUnauthorized: false를 설정하면 자기 서명 증명서를 사용하는 https사이트로 요청을 허가합니다.
        followredirects: false를 설정하면 리다이렉트를 하지 않습니다. 기본값은 true 입니다.
    - 출력 메시지 구성
        - payload: 응답 본체, 반환할 본체 데이터를 문자열, JSON 문자열로서 해석할 결과, 바이너리버퍼 그대로, 어떤 것으로 할지를 노드 설정에서 지정할 수 있습니다.
        - statusCode: 응답 상태 코드 또는 요청에 따른 에러코드
        - headers: 응답 헤더를 포함하는 오브젝트
        - responseUrl: 요청 처리시에 리다이렉트가 발생한 경우, 이 프로퍼티가 마지막으로 리다이렉트된 url을 표시합니다. 리다이렉트가 일어나지 않았을 경우, 첫 요청 url을 표시합니다.
        - responseCookies: 응답이 쿠키를 포함하는 경우, 이 프로퍼티는 각 쿠키의 이름/값을 포함하는 오브젝트를 표시합니다.
        - redirectList: 요청이 1번 이상 리다이렉트된 경우, 이 프로퍼티에 정보가 축적됩니다.

## websocket in
1. 노드 개요  
    기본값으로 WebSocket에 의해 수신한 데이터는 msg.payload에 저장됩니다. 서버 역할을 수행하여 데이터를 수신한 수 있으며, 클라이언트 역할을 수행하여 데이터를 수신할 수도 있습니다.

2. 노드 사용  
    websocket in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![WEBSOCKETIN]({{ site.url }}/docs/pages/logic-flow/network/websocketin-23.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![WEBSOCKETIN_EDIT]({{ site.url }}/docs/pages/logic-flow/network/websocketinedit-23.png)

    - 종류: 대기 또는 접속을 선택할 수 있습니다.
    - 패스: 종류에 따라 설정이 달라집니다. 
        - websocket-listener의 노드타입 추가: 종류를 대기로 선택할 경우에 해당합니다. 패스를 설정하고 해당 패스에 대하여 값이 입력되는 것을 기다립니다. 즉, 서버로 동작합니다. 패스의 예) /ws/example로 설정한 경우 실제 대기 url은 /api/ws/example이 됩니다.
        - websocket-client의 노트타입 추가: 종류를 접속으로 선택한 경우에 해당합니다. 접속하고자하는 websocket 서버의 리스닝 url을 입력합니다. 예) ws://127.0.0.1:1880/api/ws/example

## websocket out
1. 노드 개요  
    기본값으로 msg.payload를 WebSocket 통하여 송신합니다. 서버 역할을 수행하여 데이터를 송신한 수 있으며, 클라이언트 역할을 수행하여 데이터를 송신할 수도 있습니다.

2. 노드 사용  
    websocket out 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![WEBSOCKETOUT]({{ site.url }}/docs/pages/logic-flow/network/websocketout-24.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![WEBSOCKETOUT_EDIT]({{ site.url }}/docs/pages/logic-flow/network/websocketoutedit-24.png)

    - 종류: 대기 또는 접속을 선택할 수 있습니다.
    - 패스: 종류에 따라 설정이 달라집니다. 
        - websocket-listener의 노드타입 추가: 종류를 대기로 선택할 경우에 해당합니다. 패스를 설정하고 해당 패스에 대하여 클라이언트 접속을 기다립니다. 즉, 서버로 동작합니다. 패스의 예) /ws/example로 설정한 경우 실제 대기 url은 /api/ws/example이 됩니다.
        - 노드의 입력으로 들어온 payload 값을 접속된 클라이언트에게 전송합니다. 
        websocket-client의 노트타입 추가: 종류를 접속으로 선택한 경우에 해당합니다. 접속하고자하는 websocket 서버의 리스닝 url을 입력합니다. 예) ws://127.0.0.1:1880/api/ws/example 
        노드 입력으로 들어온 payload 값을 접속한 서버로 전송하게 됩니다.

## tcp in
1. 노드 개요  
    메시지를 TCP로부터의 입력을 수행합니다. 리모트 TCP 포트에 접속하거나, 외부로부터의 접속을 접수합니다. 즉, TCP 클라이언트로 동작하면서 값을 받거나, TCP 서버로 동작하면서 값을 받아들입니다.

2. 노드 사용  
    tcp in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TCPIN]({{ site.url }}/docs/pages/logic-flow/network/tcpin-25.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TCPIN_EDIT]({{ site.url }}/docs/pages/logic-flow/network/tcpinedit-25.png)

    - 종류: 대기 또는 접속을 선택할 수 있습니다.  
    대기를 선택한 경우, 대기할 포트값을 입력하여야 합니다. 접속을 선택한 경우, 접속할 호스트 주소와 포트값을 입력하여야 합니다.

    ![TCPIN_SORT]({{ site.url }}/docs/pages/logic-flow/network/tcpinsort-25.png)

    - 출력: 스트림 또는 단일을 선택할 수 있습니다. 각각에 대하여 공히 데이터 형식은 문자열, 바이너리 버퍼, Base64 문자열 중 선택할 수 있습니다.
        - 스트림: 통신 연결된 상태에서 데이터를 주기적, 간헐적으로 입력되는 데이터를 입력 처리할 수 있습니다. 나누는 문자를 설정하면 해당 구분자로 끊어서 처리할 수 있습니다. 예) “/”로 설정한 경우 입력되는 메시지는 “this/is/a/test/”로 입력되면 각각이 구분되어 입력 처리됩니다.
        - 단일: 통신이 완료되어야 입력 데이터가 flush되어 입력 처리할 수 있습니다. 예를 들어 tcp out 클라이언트에서 “메시지를 송신할 때마다 접속을 절단”을 선택하고, 단일 출력으로 설정된 tcp in 서버에서 메시지가 입력될 때마다 단일 입력 데이터를 처리할 수 있게 됩니다.
    - 토픽: 다음 단계로 전달되는 메시지의 토픽을 입력한 값으로 설정합니다.

## tcp out
1. 노드 개요  
    TCP로의 출력을 수행합니다. 리모트 TCP포트로 접속, 외부로부터의 접속을 접수, 혹은 TCP In 노드에서 받은 메세지로의 리플라이를 수행합니다.

2. 노드 사용  
    tcp out 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TCPOUT]({{ site.url }}/docs/pages/logic-flow/network/tcpout-26.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TCPOUT_EDIT]({{ site.url }}/docs/pages/logic-flow/network/tcpoutedit-26.png)

    - 종류: 대기, 접속 또는 TCP응답을 선택할 수 있습니다.
        - 대기를 선택한 경우, 대기할 포트값을 입력하여야 합니다. 
        - 접속을 선택한 경우, 접속할 호스트 주소와 포트값을 입력하여야 합니다.
    
    ![TCPOUT_SORT]({{ site.url }}/docs/pages/logic-flow/network/tcpoutsort-26.png)

    - TCP 응답의 경우 TCP in 노드에 접속한 상대방으로 응답 메시지를 보낼 수 있습니다.
        
    ![TCPOUT_REP]({{ site.url }}/docs/pages/logic-flow/network/tcpoutrep-26.png)

    예) 1번은 tcp in 서버입니다. 2번은 tcp out(tcp 응답)입니다. 3번은 메시지 생성자입니다. 3번에서 메시지를 생성하여 2번에 전달하면 2번은 1번에 접속한 모든 클라이언트로 메시지를 전송하게 됩니다. 1번에서 받은 메시지를 수정하여 응답하게 되는 경우에는 메시지를 보낸 클라이언트에게만 메시지를 전송합니다. 즉, msg._session 속성 항목이 존재하지 않은 경우, 접속한 모든 클라이언트에게 송신합니다

    ![TCPOUT_LINK]({{ site.url }}/docs/pages/logic-flow/network/tcpoutlink-26.png)

    - 메시지를 송신할 때마다 접속을 절단: 데이터를 송신한 후 연결을 끊고 다시 연결하는 동작을 합니다. 보내는 데이터는 flush되어 모두 전송됩니다.
    - Base64메시지의 복호: msg.payload가 바이너리 데이터를 Base64인코딩의 문자열로 변환한 것일 경우, Base64디코딩 옵션을 지정하면 데이터를 바이너리로 변환하여 송신합니다.


<!-- ? -->

## tcp request
1. 노드 개요  
    간단한 TCP리퀘스트 노드. msg.payload를 서버의 TCP포트에 송신하여, 응답을 기다립니다. 서버 접속, “request” 송신, “response” 수신을 수행합니다.

2. 노드 사용  
    tcp request 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TCPREQ]({{ site.url }}/docs/pages/logic-flow/network/tcpreq-27.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TCPREQ_EDIT]({{ site.url }}/docs/pages/logic-flow/network/tcpreqedit-27.png)

    - 서버/포트: 접속할 서버의 ip address 및 포트 정보를 입력합니다. 포트 번호를 공백으로 설정한 경우, msg.host 및 msg.port 프로퍼티를 설정해야 합니다.
    - 반환값: 반환값은 버퍼형식으로 msg.payload에 출력됩니다. 문자열로 취급하기 위해서는 .toString()을 사용하시가 바랍니다. 반환값을 처리하는 동작을 선택할 수 있습니다.
        - 지정시간 후: 첫번째 응답을 받은 후 지정한 시간(밀리초)을 대기한 후 결과를 반환합니다.
        - 지정문자의 수신 시: 설정한 문자열이 도착한 경우 결과를 반환합니다.  
    
    ![TCPREQ_RECEIVE]({{ site.url }}/docs/pages/logic-flow/network/tcpreqreceive-27.png)

    - 지정 개수의 문자열: 반환된 문자의 수가 지정한 문자 개수를 초과할 경우 결과를 반환합니다.
        
    ![TCPREQ_STRING]({{ site.url }}/docs/pages/logic-flow/network/tcpreqstring-27.png)

    - 없음 - 접속을 유지: 별도의 동작 조건이 없음을 의미합니다. 응답이 도착할 경우 즉시 결과를 반환합니다.
    - 즉시 – 응답을 기다리지 않음: 요청을 송신한 후 응답을 기다리지 않고 접속을 즉시 삭제합니다.

## udp in
1. 노드 개요  
    UDP입력 노드. msg.payload에 버퍼, 문자열, 혹은 Base64인코딩 문자열을 생성합니다. 멀티캐스트를 지원합니다.

2. 노드 사용  
    udp in 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![UDP_IN]({{ site.url }}/docs/pages/logic-flow/network/udpin-28.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![UDP_IN_EDIT]({{ site.url }}/docs/pages/logic-flow/network/udpinedit-28.png)

    - 대기: UDP 메시지 또는 멀티캐스트 메시지 중 선택할 수 있습니다. UDP 메시지는 UniCasting을 의미합니다.
    - 포트/종류: 데이터를 수신할 포트를 설정합니다. 종류는 ipv4 또는 ipv6 중 선택할 수 있습니다.
    - 출력: 바이너리 버퍼, 문자열, Base64문자열 중 선택할 수 있습니다.

## udp out
1. 노드 개요  
    msg.payload를 지정된 UDP 호스트와 포트에 송신합니다. 멀티캐스트를 지원합니다.

2. 노드 사용  
    udp out 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![UDPOUT]({{ site.url }}/docs/pages/logic-flow/network/udpout-29.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![UDPOUT_EDIT]({{ site.url }}/docs/pages/logic-flow/network/udpoutedit-29.png)

    - 송신/포트: UDP 메시지, 브로드캐스트 메시지 또는 멀티캐스트 메시지 중 선택할 수 있습니다. 데이터를 수신할 호스트의 포트 정보를 입력합니다.
    - 어드레스: 데이터를 수신할 호스트의 IP 주소를 입력합니다. 주소 타입을 ipv4/ipv6 중 선택할 수 있습니다. 기본값은 ipv4입니다.

