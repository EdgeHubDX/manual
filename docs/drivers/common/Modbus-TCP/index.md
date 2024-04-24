---
layout: default
grand_parent: Drivers
parent: Common
title: Modbus TCP
nav_order: 3
---

{: .no_toc }
# Modbus TCP
- TOC
{:toc}

## 연결가능 TCP
모드버스 TCP/IP 프로토콜을 지원하는 기기와 통신 연결이 가능합니다.
모드버스 프로토콜은 서버-클라이언트 사이의 통신에 사용되는 규격화된 개방형 프로토콜로 펑션 코드에 따라 데이터의 읽기/쓰기로 동작합니다. 모드버스 프로토콜을 사용하는 기기간 통신은 오직 하나의 클라이언트에서만 처리하는 서버-클라이언트 기능을 사용합니다.

## 결선도  
이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다.   
허브와 같은 네트워크 장비에 연결하여 랜 망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)   
랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.   

다이렉트 케이블을 제작하는 방법은 아래와 같습니다.

![direct-cable]({{ site.url }}/docs/drivers/common/Modbus-TCP/direct-cable.png) ![modular-jack]({{ site.url }}/docs/drivers/common/Modbus-TCP/modular-jack.png)

위의 그림에서 ‘백황’,  ‘백녹’,  ‘백청’,  ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.
예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.

크로스 케이블을 제작하는 방법은 아래와 같습니다.

![cross-cable]({{ site.url }}/docs/drivers/common/Modbus-TCP/cross-cable.png) ![modular-jack]({{ site.url }}/docs/drivers/common/Modbus-TCP/modular-jack.png)

{:.note}
>☞ 연결 방식에 맞게 사용하십시오.   
>☞ 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.   
>☞ 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.   
>☞ UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다.    
>☞ 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.   

## 통신드라이버 설정
MODBUS(TCP/IP)통신이 지원되는 각종 기기와 MODBUS 프로토콜을 통해서 접속 가능합니다. 제조사별 설정방법이 다르므로 자세한 내용은 해당 기기 사용 설명서를 참조 바랍니다.
여기에서는 LS ELECTRIC의 PLC(XGK)를 예로 들어 설명하겠습니다.

### PLC 설정
PLC(XGK)의 통신 파라미터는 XG-PD에서 설정합니다.

![XG-PD]({{ site.url }}/docs/drivers/common/Modbus-TCP/XG-PD-1.png)

1. 접속설정
    - [온라인]->[접속설정]을 선택합니다.
    - 사용자 환경에 맞는 접속 옵션을 설정한 후 접속을 클릭합니다.

2. I/O 정보 읽기
    - [온라인]->[I/O 정보읽기]를 선택하여 현재 베이스에 장착된 모듈의 정보를 읽습니다.

    ![modbus-set]({{ site.url }}/docs/drivers/common/Modbus-TCP/modbus-set-1.png)

3. 기본 설정
    - 해당 cnet I/F 모듈을 더블 클릭하여 기본 설정 창을 실행하고 접속 설정메뉴의 통신형태, 통신속도, 모뎀형식, 데이터 비트, 정지비트, 국번을 설정합니다. 

4. 동작 모드
    - 동작 모드는 RTU 서버를 선택합니다.
    - 모드버스 RTU 서버로 동작모드를 선택한 경우 모드버스 설정이 활성화 됩니다.

5.모드버스 설정 
- 비트 읽기 영역 시작주소: 비트읽기 영역의 시작주소를 의미하며 5자리로 구성됩니다. 이때 앞의 4자리는 워드 값을 나머지 한자리는 비트 값을 의미합니다.
    예) M00000일 경우: M디바이스 영역의 0번째 워드의 0번째 비트가 비트 읽기 영역의 시작주소로 설정됨을 의미합니다.
- 비트 쓰기 영역 시작주소: 비트쓰기 영역의 시작주소를 의미하며 5자리로 구성됩니다. 이 때 앞의 4자리는 워드 값을 나머지 한자리는 비트 값을 의미합니다.
    예) M00100 경우: M디바이스 영역의 10번째 워드의 0번째 비트가 비트 읽기 영역의 시작주소로 설정됨을 의미합니다.
- 워드 읽기 영역 시작주소: 워드읽기 영역의 시작주소를 의미하며 4자리로 구성됩니다.
    예) M00200 경우: M디바이스 영역의 200번째 워드가 워드 읽기영역의 시작주소로 설정됨을 의미합니다.
- 워드 쓰기 영역 시작주소: 워드쓰기 영역의 시작주소를 의미하며 4자리로 구성됩니다.
    예) M00300 경우: M디바이스 영역의 300번째 워드가 워드 쓰기영역의 시작주소로 설정됨을 의미합니다.

6. 파라미터
- [온라인] -> [파라미터 쓰기]를 클릭합니다.
- 기본 설정에서 기본설정을 완료한 모듈을 클릭한 후 확인을 클릭합니다.
- 확인버튼 클릭 후 파라미터 쓰기 완료 후 해당모듈을 개별 리셋합니다.

7. 동작 확인
- [온라인] -> [시스템 진단]을 클릭합니다.
- 해당 모듈의 클릭한 후 오른쪽 마우스 버튼을 눌러 프레임 모니터링이나 서비스별 상태를 클릭하여 정상적인 통신 여부를 확인 할 수 있습니다.

### EdgeHub  설정: Modbus TCP
 1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “ModbusTCP”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/common/Modbus-TCP/channel-add-2.png)

2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/common/Modbus-TCP/channel-att-2.png)

    - 채널 명 : 통신채널 이름을 입력합니다. 
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP Address #1 : PC의 IP Address를 입력합니다.
    - 로컬 IP Address #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
    - 타임아웃 : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - Address Offset 시작번지 : 0 또는 1을 가진다. 시작번지를 0번부터 또는 시작번지를 1부터 시작하는가의 여부를 설정한다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.



3. Device 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/common/Modbus-TCP/device-att-2.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 
    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 
    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 포트 번호 : 포트 번호를 입력합니다. 기본 값은 502 입니다.
    - UnitID : 통신하고자 하는 Modbus TCP 장비의 ID를 입력한다.
    - 32Bit데이터 Swap: 32Bit인 경우 [상위워드 + 하위워드] 또는 [하위워드 + 상위워드]의 조합으로 32Bit를 나타낼수 있는데 이를 위하여 상위워드와 하위워드 Swap을 사용한다. 
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

6. Block 속성 설정
    ![block-att]({{ site.url }}/docs/drivers/common/Modbus-TCP/block-att-2.png) 

    - Block 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 4가지 종류가 있으며, 각각 아래와 같은 방법으로 Address를 지정합니다.
        - Address 구별자: 0(Coil Status), 1(Discrete Input Status), 3(Input Register), 4(Holding Register) 
        - Address:  0 ~ 65535  (채널정보에서 Address Offset 시작번지를 1로 설정하였다면, 1 ~ 65536)
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 구별자별 읽고자하는 갯수
    -  저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

7.	입출력 주소
    1.	아날로그
        구별자(3 또는 4) + 0~65535 
        (채널정보에서 Address Offset 시작주소를 1로 설정하였다면, 1~65536) 

        예1) 3번(Input Register : 읽기만 가능)의 0번지(0~65535중 0)를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 300000 또는 30으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 300001 또는 31으로 설정

        예2) 4번(Holding Register)의 17번지(0~65535중 17)를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 400017 또는 417으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 400018 또는 418으로 설정

    2.	디지털
        구별자(0 또는 1 또는 3 또는 4) + 0~65535 
        (채널정보에서 Address Offset 시작주소를 1로 설정하였다면, 1~65536)

        예1) 0번(Coil Status : 읽기/쓰기 가능)의 0번지(0~65535중 0)를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 000000 또는 00으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 000001 또는 01으로 설정

        예2) 1번(Discrete Input Status : 읽기만 가능)의 17번지(0~65535중 17)를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 100017 또는 117으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 100018 또는 118으로 설정

        예3) 3번(Input Register : 읽기만 가능)의 17번지(0~65535중 17)의 10번째 Bit를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 300017.A 또는 317.A으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 300018.A 또는 318.A으로 설정

        예4) 4번(Holding Register : 읽기만 가능)의 0번지(0~65535중 17)의 15번째 Bit를 읽고 싶다면 
        Address Offset 시작주소를 0으로 설정하였다면, 300000.F 또는 30.F으로 설정
        Address Offset 시작주소를 1으로 설정하였다면, 300000.F 또는 31.F으로 설정

## 사용 가능 디바이스
사용가능한 디바이스는 아래와 같습니다. 

| 디바이스    | 접속 가능 영역  | 비고        |           |     
|---------|-----------|-----------|-----------|-----|---|
|         | 가능 범위     | 읽기(펑션 코드) | 쓰기(펑션 코드) |     
| 출력 접점   | 0 - 65535 | 가능(01)    | 가능(05)    | -  |
| 입력 접점   | 0 - 65535 | 가능(02)    | 가능(05)    | -   |
| 출력 레지스터 | 0 - 65535 | 가능(03)    | 가능(06,16) | -  | 
| 입력 레지스터 | 0 - 65535 | 가능(04)    | 가능(06,16) | -   |

{:.note}
>☞ 디바이스에 대한 자세한 내용은 모드버스 프로토콜 사용설명서를 사용하십시오.    
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.   
>☞ PLC 에 따라 사용 가능한 디바이스 최대값이 다르므로 접속할 PLC 의 사용설명서를 확인하여 주십시오.   
 