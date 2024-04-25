---
layout: default
grand_parent: Drivers
parent: MITSUBISHI
title: MELSEC-FX PLC
nav_order: 1
---

{: .no_toc }
# MITSUBISHI: MELSEC-FX PLC
- TOC
{:toc}

## 1. PLC 목록
접속이 가능한 PLC 목록은 아래와 같습니다

|PLC 종류	|CPU모듈|	접속 방식	|통신 방식|	접속 모듈|
|:---------|:------|:--------------|:-------|:--------|
|MELSEC-FX	FX1N   |Serial     |RS-232C|	FX1N-232-BD|
|         |  FX2N   |             ||       FX2N-232-BD|
|          |  FX1NC  |              ||       FX0N-232ADP|
|           |FX2NC    |               ||    FX2NC-232ADP|
|          |FX0N      |             ||   FX0N-232ADP + FX1N-CNV-BD|
|         |FX1S       |            ||   FX0N-232ADP + FX2N-CNV-BD|
|        |FX2         |             ||  FX2NC-232ADP + FX1N-CNV-BD|
|       |FX2C	      |            ||   FX2NC-232ADP + FX2N-CNV-BD|	
|        |             |          ||    FX-232ADP|
|         |             |    |  RS-422/485|	FX1N-485-BD|
|||||FX2N-485-BD|
|||||FX2NC-485ADP|
|||||FX0N-485ADP|
|||||FX-485ADP|
|FX3U|Ethernet	|Ethernet|	FX3U-ENET-L|
|FX3UC	|||||

{:.note}
>☞ 자세한 지원 정보는 MELSEC-FX 사용설명서를 참조하십시오. 또한 지원 사항은 본 제품과 무관하게MITSUBISHI사에 의해 변경될 수 있습니다.

## 2. 결선도
### 2.1 링크 방식: Serial

통신 방식은 RS-232C용과 RS-422/485용으로 구분되어 있습니다.
RS-232C을 제공하는 Mitsubishi MELSEC-FX 시리즈의 계산기 링크 방식은 모듈에 따라 2가지 형태의 커넥터가 있습니다.

먼저 9핀(Pin) 커넥터와 연결할 때의 결선 법입니다.

![9pin]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/9pin-1.png)

다음은 20핀(Pin) 커넥터와 연결할 때의 결선 법입니다.

![20pin]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/20pin-1.png)

{:.note}
>☞ MELSEC-FX는 흐름제어를 사용하므로 위와 같이 결선을 하지 않을 경우에는 통신을 하지 않습니다.   
>☞ 안정적인 통신을 위해서는 Mitsubishi에서 제안하는 실드 결선을 권장합니다. 자세한 사항은 MELSEC-FX 사용설명서를 참조하십시오.   

다음은 RS-422/485 결선 법입니다.
Mitsubishi에서는 1선 페어 결선 법을 권장하므로 RS-422 보다는 RS-485 결선 법을 권장합니다.

![RS-422/485]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/RS-422,485-1.png)

{:.note}
>☞ PLC 모듈 종류에 따라 커넥터 및 핀 배열이 다를 수 있습니다.   
>☞ RS-422 보다는 RS-485를 권장합니다.   
>☞ 안정적인 통신을 위해서는 실드 결선을 권장합니다. 실드 결선 법은 MELSEC-FX 사용설명서를 참조하십시오.   

### 2.2 링크 방식 : Ethernet
1. 이더넷 결선
이더넷을 통해 아래와 같이 2가지 형태로 연결할 수 있습니다. 

![hub-node]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/hub-node-1.png)

![1vs1]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/1vs1-1.png)

{:.note}
>☞ 허브-노드 간 연결할 때에는 다이렉트 케이블을 사용해야 하며, 1:1 연결할 때에는 크로스 케이블을 사용해야 합니다.

2. 이더넷 케이블
이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다. 허브와 같은 네트워크 장비에 연결하여 랜(LAN)망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.

다이렉트 케이블을 제작하는 방법은 아래와 같습니다. 

![direct_cable]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/direct-cable-1.png)![modular_jack]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/modular-jack-1.png)

위의 그림에서 ‘백황’, ‘백녹’, ‘백청’, ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.
예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.

크로스 케이블을 제작하는 방법은 아래와 같습니다.

![cross_cable]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/cross-cable-1.png) ![modular_jack]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/modular-jack-1.png)

{:.note}
>☞ 연결 방식에 맞게 사용하십시오.   
>☞ 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.   
>☞ 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.   
>☞ UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다.    
>☞ 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.   

## 3. 통신드라이버 설정
### 3.1 링크 방식: Serial
1. PLC 설정
MELSEC-FX PLC의 통신 파라미터는 GX Developer S/W에서 설정합니다. 설정방법에 대한 자세한 사항은 MITSUBISHI 통신 사용설명서를 참조 바랍니다.

- 1단계: GX Developer를 실행하신 후 프로젝트 창에서 [파라미터] -> [PLC 파라미터] -> [PLC 시스템(2)] 탭을 선택하십시오.

![param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/param-1.png)

- 2단계: 통신 동작 설정을 체크하십시오.

![check]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/check-1.png)

- 3단계: 프로토콜은 전용 프로토콜을 선택하십시오. 이는 계산기 링크를 설정하는 방법입니다.

![protocol]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/protocol-1.png)

- 4단계: 기본적인 통신 파라미터(전송 속도/데이터 길이/패리티/스톱 비트)를 설정하십시오. 

![data_length]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/data-length-1.png)

- 5단계: 통신 종류를 선택하십시오.

![hw-set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/hw-1.png)

- 6단계: 계산기 링크 중 형식1을 사용합니다. 섬 체크 사용 여부는 EdgeHub 디바이스 설정과 동일하게 설정하시기 바랍니다.

![sum_check]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/sum-check-1.png)

- 7단계: 국번을 설정하여 주십시오.
![h-set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/h-set-1.png)

{:.note}
>☞ 본 설명서에서는 간략하게 설명하고 있습니다. 설정 시 반드시 MITSUBISHI의 해당 PLC 사용설명서를 참조 바랍니다.

2. EdgeHub 설정
   1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “MelsecFXSerial”를 선택한 후 “확인” 버튼을 누릅니다. 

    ![channel_add]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/channel-add-1.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/channel-att-1.png)

    - 채널 명 : 통신채널 이름을 입력합니다. 
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 통신포트 #1 : PC의 시리얼 포트를 선택합니다.
    - 통신속도 : 시리얼 통신 속도를 선택합니다.
    - 패리티비트 : 패리티비트를 선택합니다.
    - 데이터비트 : 데이터비트를 선택합니다.
    - 스톱비트 : 스톱비트를 선택합니다.
    - 타임아웃 : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

    3. Device 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

    4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - CheckSum 사용 : CheckSum 사용 여부를 설정합니다. PLC 통신 설정과 동일하게 설정하여 주십시오.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.


    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정
    ![block_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/block-att-1.png)

    - Block 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 
        - X,Y,M,S는 Bit단위의 디바이스 메모리이며, 읽기는 WORD단위로 불러옵니다.

        예제1) X,Y는 8진수단위의 Bit 메모리 입니다. Address는 X7 다음은 X10으로 표현합니다. 시작Address는 8진수로 8의 배수이어야 합니다. 즉, X0(0번째 비트), X10(8번째 비트), X20(16번째 비트), X30(24번째 비트)....
        그리고, Block크기는 WORD단위 입니다. 만약16점을 읽어오려면, 1을 넣어주면 됩니다.
        시작 Address : X0, Block크기 : 2로 하였다면, X0~X7, X10~X17, X20~X27, X30~X37의 32Bit를 읽어옵니다. 

        예제2) M,S는 10진수단위의 Bit메모리 입니다. Address는 M9 다음은 M10으로 표현합니다. 시작Address는 10진수로 8의 배수이어야 합니다. 즉, M0(0번째 비트), M8(8번째 비트), M16(16번째 비트), M24(24번째 비트)....
        그리고, Block크기는 WORD단위 입니다. 만약16점을 읽어오려면, 1을 넣어주면 됩니다.
        시작 Address : M0, Block크기 : 2로 하였다면, M0~M31의 32Bit를 읽어옵니다. 

        - D,T,C,CN,TN은 WORD단위의 디바이스 메모리입니다.
        시작Address : D10, Block크기 : 10으로 하였다면, D10~D19까지의 10개 WORD값을 읽어옵니다.
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 왼쪽의 “등록 정보” 트리에 추가되어 나타납니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    - 사용가능 입출력 주소

    | 영역 | 크기    | 비트 접점         | 워드 데이터        | 비고    |
    |----|-------|---------------|---------------|-------|
    | X  | 256점  | X000 ~ X377   | X000 ~ X360   | 팔진수   |
    | Y  | 256점  | Y000 ~ Y377   | Y000 ~ Y360   | 팔진수   |
    | M  | 7680점 | M0000 ~ M7679 | M0000 ~ M7664 | 십진수   |
    |    | 512점  | M8000 ~ M8511 | M9000 ~ M8496 | 십진수   |
    | S  | 4096점 | S0000 ~ S4095 | S0000 ~ S4080 | 십진수   |
    | TN | -     | -             | TN000 ~ TN511 | 십진수   |
    | CN | -     | -             | CN000 ~ CN199 | 십진수   |
    |    | -     | -             | CN200 ~ CN255 |       |
    | D  | -     | -             | D0000 ~ D7999 | 십진수   |

### 3.2 링크방식: Ethernet
1. PLC 설정
PLC 이더넷 카드에 대한 IP Address 및 Port 번호를 설정하여야 합니다. IP Address 및 Port 번호를 설정은 GX Developerd와 FX3U-ENET-L Configuration Tool을 이용하여 설정합니다.

- 1단계: 	GX Developer 프로그램을 인스톨하신 후 FX3U-Enet-L Configuration Tool를 셋 업 하시면 다음과 같이 비활성화 되어있던 메뉴가 활성화 됩니다.
[메뉴]-[Tools]-[FX special function utility]-[FX3U-ENET-L Configuration Tool]

![ethernet1]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet1-2.png)

- 2단계: 	FX3U-ENET-L Configuration Tool을 실행하면 이더넷 모듈을 설정 할 수 있는 창이 나타납니다. 우선 이더넷 모듈이 있는 모듈 자리를 선택합니다. CPU 다음부터가 0번입니다.

![ethernet2]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet2-2.png)

- 3단계: 	모듈선택이 끝나면 Operational settings를 선택하여 IP Address을 설정합니다.

![ethernet3]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet3-2.png)

- 4단계:  Open settings를 선택하여 Port 번호를 설정합니다. 3이나4번을 사용하여야 합니다.  
Port 번호는 1025~65534까지 설정할 수 있습니다.
다음은 TCP/IP 설정 및 UDP/IP 설정에 대한 예입니다.

<TCP/IP 설정>
3번에 Unpassive(MC)를 선택하고 Port번호를 4000번으로 설정한 것입니다.
4번에 설정된 내용은 MELSOFT(GX Developer)와 통신을 할 때 설정합니다.

![ethernet4]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet4-2.png)

<UDP/IP 설정>
3번에 UDP 프로토콜을 선택하고 Port 번호를 4000번으로 설정하고 PC Port 번호를 4001번(EdgeHub에서 설정한 로컬 포트번호)으로 설정한 것입니다.
4번에 설정된 내용은 MELSOFT(GX Developer)와 통신을 할 때 설정합니다.

![ethernet5]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet5-2.png)

<TCP/IP, UDP/IP 설정>
4번에 MELSOFT(GX Developer)와 통신 설정을 넣지 않고 UDP 사용으로 하였을 때는 MELSOFT와는 통신이 되지 않습니다.

![ethernet6]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet6-2.png)

- 5단계:  설정한 내용을 PLC에 Write합니다. 아직 이더넷 모듈이 설정되지 않았기 때문에 로더 케이블을 사용하여서 Write를 하여야 합니다.

![ethernet7]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet7-2.png)

![ethernet8]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet8-2.png)

- 6단계: Transfer setup으로 Connection test를 하여 다음과 같은 메시지 창이 뜨면 이더넷 모듈 설정이 완료된 것입니다. (MELSOFT와 통신 연결이 성공하려면 위 Open settings 4단계와 같이 MELSOFT connection를 설정하여야 합니다)

![ethernet9]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/ethernet9-2.png)

{:.note}
>프로그래밍 툴
>☞  GX Developer, FX3U-ENET-L Configuration Tool.

2. EdgeHub 설정
    1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “MelsecFXEthernet”을 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/channel-add-2.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/channel-att-2.png)

    - 채널 명 : 통신채널 이름을 입력합니다. 
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP Address #1 : PC의 IP Address를 입력합니다.
    - 로컬 IP Address #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
    - 타임아웃 : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.



    3. Device 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

    4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/device-att-2.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - 유동 IP 지원 : 유동 IP 를 사용하고자 할 때, 체크합니다. 이 옵션은, hosts 파일 또는 DNS 서버로 부터 IP 어드레스를 얻어와서 통신할때 사용합니다. 따라서 hosts 파일 또는 DNS 서버에 호스트 이름 또는 URL이 등록되어 있어야 합니다. hosts 파일을 이용하는 방식은 다음과 같습니다. hosts 파일은 C:\WINDOWS\system32\drivers\etc 위치에 있습니다. hosts 파일이 아래와 같이 저장되어 있을 때, 유동 IP 는 다음과 같이 설정합니다. (DNS 서버를 이용할 때도, 설정방식은 동일 합니다.)

    ![hosts]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/hosts-2.png)

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/device-att-2.png)

    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 2개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 네트웍을 분리하여 통신하고자 할 때 사용합니다. 네트웍 라인에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![line_double]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/line_double-2.png)

    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 1개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 통신 모듈이 분리되어 있는 경우 사용합니다. PLC 통신 모듈에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![device_double]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/device-double-2.png)

    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 포트 번호 : PLC의 포트 번호를 입력합니다..
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 코드 타입 : BINARY와 ASCII 중의 한가지를 선택합니다. (PLC의 설정과 동일해야 함)

    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정

    ![block_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-FX-PLC/block-att-2.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
        - 사용 가능 입출력 주소

        | 디바이스 | 크기    | 비트 접점       | 워드 데이터      | 읽기/쓰기 | 비고   |
        |------|-------|-------------|-------------|-------|------|
        | X    | 256점  | X000~X377   | X000~X360   | 읽기    | 팔진수  |
        | Y    | 256점  | Y000~Y377   | Y000~Y360   | 읽기    | 팔진수  |
        | M    | 8192점 | M0000~M7679 | M0000~M7664 | 읽기/쓰기 | 십진수  |
        |      |       | M8000~M8511 | M8000~M8496 | 읽기/쓰기 |      |
        | S    | 4096점 | S0000~S4095 | S0000~S4080 | 읽기/쓰기 | 십진수  |
        | TN   | 512점  | -           | TN000~TN511 | 읽기/쓰기 | 십진수  |
        | CN   | 256점  | -           | CN000~CN199 | 읽기/쓰기 | 십진수  |
        |      |       |             | CN200~CN255 | 읽기/쓰기 |      |
        | D    | 8512점 | -           | D0000~D7999 | 읽기/쓰기 | 십진수  |
        |      |       |             | D8000~D8511 | 읽기/쓰기 |      |

        1. X, Y는 팔진수입니다. (비트 디바이스)   
        비트접점(팔진수 수 체계를 사용하면 됩니다).   
        예) X000~X007, X010~X017, X020~X027, …… X070~X077, X100~X107, X110~X117……   
        워드접점(16Bit의 배수로 설정합니다).   
        예) X000, X020, X040, X060, X100, X120, ……   

        2. M, S는 십진수입니다. (비트 디바이스)   
        비트접점은(십진수 수 체계를 사용하면 됩니다).   
        예) M0000~M0009, M0010~M0019, M020~M029, ……    
        워드접점(16Bit의 배수로 설정합니다)    
        예) M0000, M0016, S032, S048, S064……   
        ※ M0000 ~M7679와 M8000~D8511는 서로 다른 디바이스 영역입니다.   
        - CPU 타입에 따라서 M0000~M7679의 크기가 다를 수 있습니다. Mitsubishi FX ENET PLC 매뉴얼을 참조하시기 바랍니다.   

        3. TN, CN는 십진수입니다. (워드 디바이스)      
        워드접점   
        예) TN000~TN511, CN000~CN255   
        ※CN0~CN199(16Bit)와, CN200~CN255(32 Bit)는 서로 다른 디바이스 영역이므로    
        - CN199를 32bit 디바이스로 사용 할 수 없습니다. (CN199 + CN200 은 서로 다른 디바이스 이므로)    
        - CN0~CN199의 영역과 CN200~CN255의 영역을 연속으로 서로 사용할 수 없다. (즉, CN190부터 CN210까지를 연속데이터(로깅, 데이터 목록 보기, 레서피 등)을 사용한다면, CN190~CN199까지와, CN200부터 CN210까지를 2개로 분리하여 사용하여야 합니다.   
        ※CN200~CN255 사용 시 숫자표시기, 숫자 입력기 에서 32Bit를 선택 후 “연속 복사”을 하게 되면, CN200, CN202, CN204……와 같이 생성되는데 CN200부터는 32bit 디바이스 이므로 주소가 1씩 증가되도록 사용하셔야 합니다. 즉, CN200, CN201, CN202, CN203……와 같이 수정해 주셔야 합니다.     

        4. D 는 십진수입니다. (워드 디바이스)   
        워드접점   
        예) D0000~D7999, D8000~D8511   
        ※ D0000 ~D7999 와 D8000~D8511는 서로 다른 디바이스 영역이므로    
        - D7999를 32 Bit 디바이스를 사용 할 수 없습니다. (CN199 + CN200 은 서로 다른 디바이스 이므로)   
        - D0~D7999의 영역과 D8000~D8496의 영역을 연속으로 서로 사용할 수 없습니다. (즉, D7990부터 D8010 까지를   연속데이터(로깅, 데이터 목록 보기, 레서피 등)을 사용한다면, D7990~D7999까지와, D8000부터 D8010까지를 2개로 분리하여 사용하여야 합니다.    

        ※M8000 ~ 및 D8000 ~ 의 메모리는 특수 영역으로써 시스템에 의해서 사용 될 수 있습니다. 또한, 이 영역은 쓸 수 없는 영역을 포함하고 있습니다. 따라서 이 영역을 사용하기 위하여서는 Mitsubishi FX ENET PLC 매뉴얼을 참조하시기 바랍니다.   

## 4. 사용 가능 디바이스
사용 가능한 디바이스는 통신 드라이버의 입출력 주소를 참고하시기 바랍니다. 

{:.note}
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.    
>☞ CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 







    


    



