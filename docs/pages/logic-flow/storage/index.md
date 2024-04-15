---
layout: default
grand_parent: Pages
parent: 로직 플로우
title: Storage 노드
nav_order: 7
---

{: .no_toc }
# Storage 노드

- TOC
{:toc}

## file
1. 노드 개요  
    msg.payload를 파일로 내보냅니다. 내보내기는, 파일의 마지막에 추가 혹은 기존 내용의 치환을 선택할 수 있습니다. 또한, 파일을 삭제하는 것도 가능합니다.

2. 노드 사용  
    file 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![FILE]({{ site.url }}/docs/pages/logic-flow/storage/file-39.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![FILE_EDIT]({{ site.url }}/docs/pages/logic-flow/storage/fileedit-39.png)

    - 파일명: 파일명을 절대 경로를 포함하여 작성합니다. 파일명만 작성할 경우 LogicFlow 실행 디렉토리에서의 상태패스가 설정됩니다. 대상 파일명을 노드에 설정하지않은 경우, msg.filename 프로퍼티로 파일을 지정할 수 있습니다. msg.filename을 사용할 경우 동작을 수행한 후 매번 파일을 닫습니다. 성능의 저하를 초래할 수 있으므로 파일명을 노드에 설정하는 것이 바람직합니다.  
    파일이 존재하지 않을 경우 자동 생성됩니다. 

    파일명 예) c:\temp\myfile  
    - 동작: 동작은 다음 셋 중에 선택할 수 있습니다.
        - 파일에 추가: msg.payload 내용을 파일에 추가합니다.
        - 파일을 덮어쓰기: msg.payload 내용으로 파일 내용을 덮어씁니다.
        - 파일을 삭제: 해당 파일을 삭제합니다.
    - 메시지의 입력마다 줄바꿈을 추가: 체크할 경우 메시지를 파일에 추가한 후 개행문자(\n)을 추가합니다. 기본값으로 체크되어 있습니다.
    - 디렉토리가 존재하지 않을 경우에 작성: 체크할 경우 디렉토리가 존재하지 않을 경우 해당 디렉토리를 작성하는 동작을 수행합니다.
    - 인코딩: 텍스트 인코딩을 선택할 수 있습니다.

## file in
1. 노드 개요  
    파일 내용을 문자열 혹은 바이너리버퍼로 불러옵니다.

2. 노드 사용  
    file in 노드를 마우스로 끌어 작업영역에 놓습니다
    
    ![FILEIN]({{ site.url }}/docs/pages/logic-flow/storage/filein-40.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![FILEIN_EDIT]({{ site.url }}/docs/pages/logic-flow/storage/fileinedit-40.png)

    - 파일명: 파일이름은 절대패스에서 지정할 것을 권장합니다. 절대패스를 지정하지 않는 경우에는, Node-RED프로세스의 워킹디렉토리로부터의 상대패스로서 취급합니다. 파일명을 노드에 설정하지 않고 msg.filename 프로퍼티로 설정할 수 있습니다. 이 경우 노드의 상태표시줄에 파일명이 표시됩니다.
    
    ![FILEIN_NAME]({{ site.url }}/docs/pages/logic-flow/storage/fileinname-40.png)

    - 출력형식: 문자열, 행마다의 메시지, 바이너리버퍼 등을 선택할 수 있습니다. 문자열로 선택할 경우 파일 내용이 하나의 문자열로 전달됩니다. 행마다의 메시지로 선택할 경우, 파일의 각 행마다 메시지를 생성하여 전달하게 됩니다.
    - Encoding: 파일 내용이 문자열인 경우, 인코딩을 선택할 수 있습니다.
    - 오류처리: 파일 읽기 오류가 발생하는 경우 Catch 노드를 사용하여 처리할 것을 권장합니다.

## watch
1. 노드 개요  
    디렉토리 혹은 파일의 변화를 감지합니다.

2. 노드 사용  
    watch 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![WATCH]({{ site.url }}/docs/pages/logic-flow/storage/watch-41.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![WATCH_EDIT]({{ site.url }}/docs/pages/logic-flow/storage/watchedit-41.png)

    - 파일: 절대경로를 포함하는 파일명이나 디렉토리명을 입력합니다. 복수일 경우 콤마로 나누어 입력합니다. 경로가 공백을 포함하는 경우, 인용부를 이용해 "..." 형태로 입력하시기 바랍니다.
    - 서브디렉토리를 재귀적으로 감시: 체크할 경우 하위의 서브 디렉토리를 모두 감시 대상으로 설정합니다.
    - 출력:
    실제로 변경된 파일의 풀패스명을 msg.payload으로, 감지대상 리스트의 문자열을 msg.topic으로 반환합니다.
    msg.file은 변경된 파일의 파일명을 나타냅니다. msg.type은 변경된 대상의 종류(file 혹은 directory)를, msg.size는 파일사이즈(바이트 수)를 나타냅니다.
    
    ![WATCH_OUTPUT]({{ site.url }}/docs/pages/logic-flow/storage/watchoutput-41.png)

## tail
1. 노드 개요  
    구성된 파일에 추가할 항목을 감시합니다.

2. 노드 사용  
    tail 노드를 마우스로 끌어 작업영역에 놓습니다.
    
    ![TAIL]({{ site.url }}/docs/pages/logic-flow/storage/tail-42.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![TAIL_EDIT]({{ site.url }}/docs/pages/logic-flow/storage/tailedit-42.png) 

    - Filename: 추가되는 내용을 감시할 파일명을 입력합니다. msg.filename 프로퍼티에 파일명을 설정할 수 있습니다. msg.filename에 공백문자 “”가 입력된 경우 동작을 중지합니다.
    - File type: 출력의 타입을 설정합니다. 문자열과 바이너리버퍼를 선택할 수 있습니다.
    - Split on: 다수의 문자열이 추가된 경우에 분리 문자열에 의해 다수의 메시지로 분리하여 출력합니다. 기본 설정값은 캐리지리턴(\r) 또는 뉴라인(\n)에 의해 분리하도록 설정되어 있습니다. 예를 들어 “/”를 구분자로 설정하고, “입력1/입력2/입력3” 이 파일에 추가되면 3개의 문자열(입력1, 입력2, 입력3)로 구분하여 출력합니다.

## mysql
1. 노드 개요  
    mysql 데이터베이스를 읽고 쓰기 위해 사용하는 노드입니다.

2. 노드 사용  
    mysql 노드를 마우스로 끌어 작업영역에 놓습니다
    
    ![MYSQL]({{ site.url }}/docs/pages/logic-flow/storage/mysql-43.png)

    작업영역에서 해당 노드를 더블클릭하면 노드의 속성 수정 화면이 표시됩니다.

    ![MYSQL_EDIT]({{ site.url }}/docs/pages/logic-flow/storage/mysqledit-43.png) 

    - Database: mysql 데이터베이스 접속정보를 설정합니다. 우측의 연필이 표시된 버튼을 클릭하면 설정창이 표시됩니다.
    
    ![MYSQL_CONNECT]({{ site.url }}/docs/pages/logic-flow/storage/mysqlconnect-43.png) 

    - Host: 접속하고자 하는 mysql이 설치된 서버의 주소를 입력합니다. LogicFlow와 동일한 서버에 설치되어 있을 경우 “127.0.0.1”을 입력할 수 있습니다.
    - Port: mysql 서비스 포트를 입력합니다. 기본값은 3306입니다.
    - User: mysql에 접속할 사용자 계정을 입력합니다.
    - Password: 사용자의 패스워드를 입력합니다.
    - Database: 접속하고자 하는 mysql 데이터베이스명을 입력합니다.


<!-- ## write file
## read file
## MSSQL
## oracledb
## influxdb in
## influxdb out
## influxdb batch
## mongodb in
## mongodb out -->