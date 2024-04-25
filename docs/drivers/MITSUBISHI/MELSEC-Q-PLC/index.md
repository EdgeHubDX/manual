---
layout: default
grand_parent: Drivers
parent: MITSUBISHI
title: MELSEC-Q PLC
nav_order: 2
---

{: .no_toc }
# MITSUBISHI: MELSEC-Q PLC
- TOC
{:toc}

## PLC 목록
MITSUBISHI: MELSEC-Q PLC

| PLC 종류      | CPU모듈                                                        | 접속 방식        | 통신 방식      | 접속 모듈                | 비고     |
|-------------|--------------------------------------------------------------|--------------|------------|----------------------|--------|
| MELSEC-Q    | Q00J, Q00, Q01, Q02, Q02H, Q06H, Q12H, Q25H, Q12PH, 25PH     | 링크 방식        | RS-232C    | QJ71C24N QJ71C24N-R2 | Cnet   |
|             |                                                              | 링크 방식        | RS-422/485 | QJ71C24N   QJ71C24N-R4|   Cnet     |
|             |                                                              | 링크 방식        | Ethernet   | QJ71E71-100          | FEnet  |
|  | Q03UDE, Q04UDEH, Q06QDEH, Q10UDEH, Q13UDEH, Q20UDEH, Q26UDEH | CPU Ethernet | Ethernet   | Built in Ethernet    | -      |


{:.note}
>용어 설명
>☞ 링크: PLC 통신 모듈과 통신하는 것을 말합니다.
>☞ Built in Ethernet: PLC CPU에 탑재된 RJ45 포트를 통한 Ethernet 통신입니다.

## 결선도
### 링크 방식: Serial
Serial은 RS-232C용과 RS-422/485용으로 구분되어 있습니다. RS-232C Cnet 결선은 다음과 같습니다.

![RS-232]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/RS-232C-1.png)

{:.note}
>☞ MELSEC-Q Serial(RS-232C)는 흐름제어를 사용하므로 위와 같이 결선을 하지 않을 경우에는 통신을 하지 않습니다.

QJ71C24N(RS-422) 결선 도는 다음과 같습니다.

![QJ71C24N]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/QJ71C24N-1.png)

QJ71C24N-4R(RS-422) 결선 도는 다음과 같습니다.

![QJ71C24N-4R]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/QJ71C24N-4R-1.png)

{:.note}
>☞ PLC의 RS-422/485 포트는 터미널블록으로 되어 있으므로 별도의 커넥터가 필요 없습니다.
>☞ 안정적인 통신을 위해서는 실드 결선을 권장합니다. 

### 링크 방식: Ethernet
1. 이더넷 결선
이더넷을 통해 아래와 같이 2가지 형태로 연결할 수 있습니다.

![hub-node]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/hub-node-1.png)

![1vs1]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/1vs1-1.png)

{:.note}
>☞ 허브-노드 간 연결할 때에는 다이렉트 케이블을 사용해야 하며, 1:1 연결할 때에는 크로스 케이블을 사용해야 합니다.

2. 이더넷 케이블
이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다. 허브와 같은 네트워크 장비에 연결하여 랜(LAN)망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.

다이렉트 케이블을 제작하는 방법은 아래와 같습니다. 

![cross_cable]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/cross-cable-1.png) ![modular_jack]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/modular-jack-1.png)

위의 그림에서 ‘백황’, ‘백녹’, ‘백청’, ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.
예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.
크로스 케이블을 제작하는 방법은 아래와 같습니다.

![cross_cable]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/cross-cable-1.png) ![modular_jack]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/modular-jack-1.png)

{:.note}
>☞ 연결 방식에 맞게 사용하십시오.    
>☞ 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.   
>☞ 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.   
>☞ UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다.    
>☞ 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.   

## 통신 드라이버 설정
### 링크 방식: Serial
1. PLC 설정
    PLC의 Serial 통신 파라미터는 GX Developer에서 설정합니다. 자세한 설정은 MITSUBISHI 사용설명서를 참조 바랍니다. 여기서는 기본적인 설정 방법에 대해 설명 드리겠습니다.

    - 1단계: GX Developer에서 메뉴 항목 중 [파라미터] -> [PLC 파라미터] -> [I/O 할당] 을 선택하십시오.

    ![PLC_param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/PLC-param-1.png)

    ![On_param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/On-param-1.png)

    - 2단계: 위와 같이 설정 화면에 표시되면 I/O 할당을 하십시오. I/O 할당은 다음과 같이 하십시오.

    | 항 목                                                | 설 정                    |
    |----------------------------------------------------|-------------------------|
    | 종류                                                 | ‘인텔리전트’를 선택하십시오.       |
    | 형명                                                 | 장착된 모듈명을 설정하십시오.       |
    | 예를 들면 QJ71C24N 모듈을 장착하신 경우에는  ‘QJ71C24N’을 선택하십시오.  |                        |
    |   점수                                                 | 32점을 선택하십시오.           |
    | 선두 XY                                              | 모듈의 선두 입출력 주소를 설정하십시오.   |

    * 인텔리전트: PLC CPU의 명령에 의해 동작하는 Q시리즈 PLC 모듈의 총칭

    - 3단계: [스위치 설정] 버튼을 선택하여 스위치를 설정하십시오.

    ![I/O_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/I,O-set-1.png)

    | 스위치 번호               | 내용                  |
    |----------------------|------------------|
    | 스위치1                 | CH1의 통신 설정          |
    | 스위치2                 | CH1의 통신 프로토콜 설정   -> EdgeHub는 0001로 설정    |
    | 스위치3                 | CH2의 통신 설정          |
    | 스위치4                 | CH2의 통신 프로토콜 설정 -> EdgeHub는 0001로 설정    |
    | 스위치5                 | 국번 설정               |

    1. 스위치 1,3 구성

        B15  B14	B13	B12	B11	B10	B9	B8	B7	B6	B5	B4	B3	B2	B1	B0


    2. 통신속도   

        | 통신 속도(bps) | 상위 바이트(B15 ~ B8)     |
        |------------|-------------------|
        | 9,600      | 05H                  |
        | 19,200     | 07H                  |
        | 38,400     | 09H                  |
        | 57,600     | 0AH                  |
        | 115,200    | 0BH                  |


    3. 통신 파라미터

        | 비트 | 내용        | 0  | 1  | 참고                           |   
        |----|-----------|----|----|------------------------------|
        | B7 | 설정 변경     | 금지 | 허가 | 허가(1)로 설정                    |   
        |   B6 | 런 중 쓰기    | 금지 | 허가 | 허가(1)로 설정                    |   
        | B5 | 섬 체크 코드   | 없음 | 있음 | 있음(1)으로 설정                   |   
        | B4 | 정지 비트     | 1  | 2  | -                            |   
        | B3 | 패리티 종류    | 홀수 | 짝수 | -                            |   
        | B2 | 패리티 비트 유무 | 없음 | 있음 | -                            |   
        | B1 | 데이터 비트    | 7  | 8  | -                            |   
        | B0 | 작성 설정     | 독립 | 연동 | 1개의 통신채널만을 사용할 경우에는 독립으로 설정  |   

    4. 스위치2, 4 구성
        -> 스위치2, 스위치4는 통신 프로토콜을 설정하는 항목입니다. EdgeHub는 형식1(0001)로 설정하여 주십시오.

    {:.note}
    >1. 통신 상태 확인 
    >☞ Cnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.
    >2. PLC 설정 시 주의사항
    >☞ 본 설명서에서는 간략하게 설명하고 있습니다. 설정 시 반드시 MITSUBISHI의 해당 PLC 사용설명서를 참조 바랍니다.

2. EdgeHub 설정: MelsecQ Serial
   1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “MelsecQSerial”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/channel-add-1.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/channel-att-1.png)

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

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    {:.note}
    >☞ EdgeHub는 MelsecQ PLC와 통신 할 때 QnA호환 4C 프레임 형식1 을 사용합니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정

    ![block_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/block-att-1.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다.
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    - I/O Address Map

    |디바이스 종류|	비트|	워드|CPU종류에 따른 어드레스 범위 (디폴트 값)|CPU종류에 따른 어드레스 범위 (디폴트 값)|	표현|표현	|예 제|
	|||        		|Q02(H), Q06H, Q12H, Q25H, Q12PH, Q25PH, Q2A, Q2A-S1,Q2AS, Q2AS-S1, Q2ASH, Q2ASH-1, Q3A, Q4A, Q4AR|Q00J, Q00, Q01|10 진수|	16 진수	||
    |--------------|----|-----|-----------------|---------------------|-----------|---------------------------------------------------|		
    |  SM    |- |   | 000000~002047 | 000000~001023 |- | SM0 , SM10, SM197          |
    |     SD |   |- | 000000~002047 | 000000~001023 |- || SD1, SD2047                | 
    |     X  |- |   | 000000~001FFF | 000000~0007FF |   |- | X0~XF, X10~X1F, X1FFF      |
    |     Y  |- |   | 000000~001FFF | 000000~0007FF |   |- | Y0~YF, Y10~Y1F, YFFF       |
    |     M  |- |   | 000000~008191 | 000000~008191 |- || M0, M1F                    |
    |     L  |- |   | 000000~008191 | 000000~002047 |- || L0~L11, L15, L100          |
    |     F  |- |   | 000000~002047 | 000000~001023 |- || F0~F17, F9, F2000          |
    |     V  |- |   | 000000~002047 | 000000~001023 |- || V1000, V2047               |
    |     B  |- |   | 000000~001FFF | 000000~0007FF |   |- | B1F, B1000, B1FFF          |
    |     D  |   |- | 000000~012287 | 000000~011135 |- || D0, D1000, D10000, D12287  |
    |     W  |   |- | 000000~001FFF | 000000~0007FF |   |- | W0, WF, W1F, W1FFF         |
    |     TS |- |   | 000000~002047 | 000000~000511 |- | | TS0, TS12, TS1000, TS2000  | 
    |     TC |-            |               |- || TC1, TC17, TC200, TC2047   |
    |     TN |   |- |               |               |- || TN0, TN2047                |
    |     SS |-            |               |- || SS0, SS2047                | 
    |     SC |-            |               |- || SC0~SS2047                 | 
    |     SN |   |- |               |               |- | | SN0~SN2047                 | 
    |     CS |- |   | 000000~001023 | 000000~000511 |- || CS0~CS1023                 |
    |     CC |-            |               |- || CC0~CC1023                 |
    |  CN                       |   |- |               |               |- || CN0~CC1023   | 
    |     SB                    |- |   | 000000~0007FF | 000000~0003FF |   |-                     | SB0~SB7FF    | 
    |     SW                    |   |- | 000000~0007FF | 000000~0003FF |   |-                     | SW0~SW7FF    |
    |     S                     |- |   | 000000~008191 | 000000~002047 |- |                       | S0~S8191 (Q00J,Q00,Q01 엑세스불가)    |
    |     DX                    |- |   | 000000~001FFF | 000000~0007FF |   |  -                     | DX0~DX1FFF   |
    |     DY                    |- |   | 000000~001FFF | 000000~0007FF |   |-                     | DY0~DY1FFF   |
    |     Z                     |   |- | 000000~000015 | 000000~000009 |- |                    | Z0~Z15       | 
    |     R                     |   |- | 000000~032767 | 000000~032767 |- |                               | R0~R32767    |
    |     ZR                    |   |- | 000000~0FE7FF | 000000~00FFFF |   |-                     | ZR0~ZRFE7FF  |  

### 링크 방식: Ethernet
1. PLC 설정
    PLC의 Ethrenet 통신 파라미터는 GX Developer에서 설정합니다. MITSUBISHI 사용설명서를 참조 바랍니다. 여기서는 기본적인 설정 방법에 대해 설명 드리겠습니다.

    - 1단계: GX Developer에서 메뉴 항목 중 [파라미터] -> [PLC 파라미터] -> [I/O 할당] 을 선택하십시오.

    ![PLC_param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/PLC-param-2.png)

    ![on_param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/on-param-2.png)

    - 2단계: 위와 같이 설정 화면에 표시되면 I/O 할당을 하십시오. I/O 할당은 다음과 같이 하십시오.

    | 항 목                                              | 설 정                       |
    |--------------------------------------------------|-------------------------|
    | 종류                                               | ‘인텔리전트’를 선택하십시오.          |
    | 형명                                               | 장착된 모듈명을 설정하십시오.          |
    | 예를 들면 QJ71E71 모듈을 장착하신 경우에는  ‘QJ71E71’을 선택하십시오.  |                           |
    | 점수                                               | 32점을 선택하십시오.              |
    | 선두 XY                                            | 모듈의 선두 입출력 주소를 설정하십시오.  

    * 인텔리전트: PLC CPU의 명령에 의해 동작하는 Q시리즈 PLC 모듈의 총징

    - 3단계: GX Developer에서 메뉴 항목 중 [파라미터] -> [네트워크 파라미터] -> [MELSECNET/Ethernet] 을 선택하십시오.

    ![network_param]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/network-param-2.png)

    - 4단계: 이더넷 네트워크 파라미터를 설정화면이 표시됩니다. 파라미터를 설정하십시오.

    ![module_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/module-set-2.png)

    | 항 목        | 설 정                                |
    |------------|----------------------------------|
    | 네트워크 종류    | Ethernet으로 설정하십시오.                 |
    | 선두 I/O No. | 모듈의 선두 입출력 주소를 설정하십시오.             |
    | 네트워크 No.   | 통신이 영향을 주지 않으므로 임의의 값으로 설정하십시오.    |
    | 총(자)국수     | 통신이 영향을 주지 않으므로 임의의 값으로 설정하십시오.    |
    | 그룹 No.     | 통신이 영향을 주지 않으므로 임의의 값으로 설정하십시오.    |
    | 국번         | 통신이 영향을 주지 않으므로 임의의 값으로 설정하십시오.    |
    | 모드         | 온라인으로 설정하십시오.                      |

    - 5단계:[동작 설정]을 선택하여 IP 어드레스를 설정하신 후 나머지 항목은 아래 그림과 같이 설정하십시오.

    ![move-set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/move-set-2.png)![move_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/move-set2-2.png)

    - 6단계:[오픈설정]을 선택하여 다음과 같이 설정하십시오. 

    ![move_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/move-set3-2.png)

    1. UDP/IP 설정 시

    | 항목            | 설정                                       |
    |---------------|-----------------------------------------|
    | 프로토콜          | ‘UDP’로 설정합니다.                            |
    | 고정버퍼          | ‘송신’으로 설정합니다.                            |
    | 고정버퍼 교신 수순    | ‘수순 있음’으로 설정합니다.                         |
    | 페어링 오픈        | ‘페어로 하지 않음’으로 설정합니다.                     |
    | 생존 확인         | ‘확인 안 함’으로 설정합니다.                        |
    | 자국 포트 No.     | PLC에 할당된 포트 No. 를 16진수로 설정합니다.           |
    | 교신 상대 IP 어드레스 | PC(EdgeHub)에 설정된 IP 어드레스를 설정합니다.         |
    | 교신 상대 포트 No.  | PC(EdgeHub)에 설정된 포트 No. 를 16진수로 설정합니다.   |

    2. TCP/IP 설정 시

    | 항목            | 설정                                          |
    |---------------|------------------------------------------|
    | 프로토콜          | ‘TCP’로 설정합니다.                               |
    | 오픈 방식         | ‘Fullpassive’, ‘Unpassive’ 모두 설정 가능합니다.     |
    | 고정버퍼          | ‘수신’으로 설정합니다.                               |
    | 고정버퍼 교신 수순    | ‘수순 있음’으로 설정합니다.                            |
    | 페어링 오픈        | ‘페어함’으로 설정합니다. 자동적으로 송신 프로토콜이 생깁니다.         |
    | 생존 확인         | ‘확인 안 함’으로 설정합니다.                           |
    | 자국 포트 No.     | PLC에 할당된 포트 No.를 16진수로 설정합니다.               |
    | 교신 상대 IP 어드레스 | PC(EdgeHub)에 설정된 IP 어드레스를 설정합니다.            |
    | 교신 상대 포트 No.  | PC(EdgeHub)에 설정된 포트 No.를 16진수로 설정합니다.       |

    ![move_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/move-set4-2.png)

    {:.note}
    >통신 상태 확인
    >☞ PLC FEnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.

2. EdgeHub 설정:MelsecQ Ethernet
    1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “MelsecQEnet”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/channel-add-2.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/channel-att-2.png)

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

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/device-att-2.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.

    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 2개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 네트웍을 분리하여 통신하고자 할 때 사용합니다. 네트웍 라인에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![line_double]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/line_double-2.png)

    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 1개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 통신 모듈이 분리되어 있는 경우 사용합니다. PLC 통신 모듈에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![device_double]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/device-double-2.png)

    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    -  PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 포트 번호 : PLC의 포트 번호를 입력합니다.
    - 유동 IP 지원 : 유동 IP 를 사용하고자 할 때, 체크합니다. 이 옵션은, hosts 파일 또는 DNS 서버로 부터 IP 어드레스를 얻어와서 통신할때 사용합니다. 따라서 hosts 파일 또는 DNS 서버에 호스트 이름 또는 URL이 등록되어 있어야 합니다. hosts 파일을 이용하는 방식은 다음과 같습니다. hosts 파일은 C:\WINDOWS\system32\drivers\etc 위치에 있습니다. hosts 파일이 아래와 같이 저장되어 있을 때, 유동 IP 는 다음과 같이 설정합니다. (DNS 서버를 이용할 때도 설정방식은 동일 합니다.)

    ![hosts]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/hosts-2.png)

    ![device_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/device-att-2.png)

    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    {:.note}
    >☞ EdgeHub는 MelsecQ PLC와 통신 할 때 QnA호환 3E 프레임을 사용합니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정

    ![block_att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/block-att-2.png)
    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 왼쪽의 “등록 정보” 트리에 추가되어 나타납니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    -I/O Address Map

    |디바이스 종류|	비트|	워드|CPU종류에 따른 어드레스 범위 (디폴트 값)|CPU종류에 따른 어드레스 범위 (디폴트 값)|	표현|표현	|예 제|
	|||        		|Q02(H), Q06H, Q12H, Q25H, Q12PH, Q25PH, Q2A, Q2A-S1,Q2AS, Q2AS-S1, Q2ASH, Q2ASH-1, Q3A, Q4A, Q4AR|Q00J, Q00, Q01|10 진수|	16 진수	||
    |--------------|----|-----|-----------------|---------------------|-----------|---------------------------------------------------|		
    | SM | ● | - | 000000~002047 | 000000~001023 | ● | - | SM0 , SM10, SM197             |
     SD | - | ● | 000000~002047 | 000000~001023 | ● | - | SD1, SD2047                   |
    | X  | ● | - | 000000~001FFF | 000000~0007FF | - | ● | X0~XF, X10~X1F, X1FFF         |
    | Y  | ● | - | 000000~001FFF | 000000~0007FF | - | ● | Y0~YF, Y10~Y1F, YFFF          |
    | M  | ● | - | 000000~008191 | 000000~008191 | ● | - | M0, M1F                       |
    | L  | ● | - | 000000~008191 | 000000~002047 | ● | - | L0~L11, L15, L100             |
    | F  | ● | - | 000000~002047 | 000000~001023 | ● | - | F0~F17, F9, F2000             |
    | V  | ● | - | 000000~002047 | 000000~001023 | ● | - | V1000, V2047                  |
    | B  | ● | - | 000000~001FFF | 000000~0007FF | - | ● | B1F, B1000, B1FFF             |
    | D  | - | ● | 000000~012287 | 000000~011135 | ● | - | D0, D1000, D10000, D12287     |
    |   W  | - | ● | 000000~001FFF | 000000~0007FF | - | ● | W0, WF, W1F, W1FFF            |
    | TS | ● | - | 000000~002047 | 000000~000511 | ● | - | TS0, TS12, TS1000, TS2000     |
    | TC | ● | - |               |               | ● | - | TC1, TC17, TC200, TC2047      |
    | TN | - | ● |               |               | ● | - | TN0, TN2047                   |
    | SS | ● | - |               |               | ● | - | SS0, SS2047                   |
    | SC | ● | - |               |               | ● | - | SC0~SS2047                    |
    | SN | - | ● |               |               | ● | - | SN0~SN2047                    |
    | CS | ● | - | 000000~001023 | 000000~000511 | ● | - | CS0~CS1023                    |
    | CC | ● | - |               |               | ● | - | CC0~CC1023                 |   
    | CN                    | - | ● |               |               | ● | - | CN0~CC1023      |
    | SB                    | ● | - | 000000~0007FF | 000000~0003FF | - | ● | SB0~SB7FF       |
    | SW                    | - | ● | 000000~0007FF | 000000~0003FF | - | ● | SW0~SW7FF       |
    | S                     | ● | - | 000000~008191 | 000000~002047 | ● | - | S0~S8191        |
    | (Q00J,Q00,Q01 엑세스불가)                 |                                |
    | DX                    | ● | - | 000000~001FFF | 000000~0007FF | - | ● | DX0~DX1FFF      |
    | DY                    | ● | - | 000000~001FFF | 000000~0007FF | - | ● | DY0~DY1FFF      |
    | Z                     | - | ● | 000000~000015 | 000000~000009 | ● | - | Z0~Z15          |
    | R                     | - | ● | 000000~032767 | 000000~032767 | ● | - | R0~R32767       |
    | ZR                    | - | ● | 000000~0FE7FF | 000000~00FFFF | - | ● | ZR0~ZRFE7FF  |    

### 링크 방식: QnU CPU Built in Ethernet
1. PLC 설정
    PLC의 통신 파라미터는 GX Developer에서 설정합니다. MITSUBISHI 사용설명서를 참조 바랍니다.
    여기서는 기본적인 설정 방법에 대해 설명 드리겠습니다.
    
    1. 	GX Developer에서 메뉴 항목 중 ‘파라미터 -> PLC 파라미터 -> Built-in Ethernet port’를 선택하십시오.
    ![PLC_set]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/PLC-set-3.png)

    ![Q_param_setting]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/q-parameter-setting-3.png)

    2. 위와 같이 설정 화면에 표시되면 파라미터를 입력합니다. 

    | 항 목                     | 설 정                                     |
    |-------------------------|--------------------------------------|
    | IP                      | Built In Ethernet 모듈의 IP 주소를 입력합니다.     |
    | Communication data code | Binary code를 선택합니다.                     |
    | Enable Online Change    | 디바이스 쓰기를 하기 위해서 체크합니다.                  |

    3. [Open settings]버튼을 누릅니다. 
    ![open_setting]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/open-setting-3.png)

    | 항 목                   | 설 정                 |   
    |-----------------------|----------------------|
    | Protocol              | UDP 또는 TCP를 선택합니다.  |   
    | Open System           | MC Protocol을 선택합니다. |   
    | Host station port No. | 포트 번호를 입력합니다.       |   

    {:.note}
    >입력 불가 포트 번호가 있습니다. 자세한 내용은 PLC 사용 설명서를 참고하세요.
    포트 번호는 16진수 표기로 입력합니다.

2. EdgeHub 설정
![device-att]({{ site.url }}/docs/drivers/MITSUBISHI/MELSEC-Q-PLC/device-att-2.png)	

디바이스 속성 설정에서 네트워크 번호, PLC 번호, 모듈 IO 번호, 모듈 국번호를 아래와 같이 설정합니다.

| 항 목      | 설 정   |   
|----------|-------|
| 네트워크 번호  | 0        |
| PLC 번호   | 255      |
| 모듈 IO 번호 | 1023     |
| 모듈 국번호   | 0        |

그외 설정은 [링크 방식 : FEnet]과 동일합니다.
[통신 드라이버 설정] -> [링크 방식 : FEnet] 설정을 참고하시기 바랍니다.

## 사용 가능 디바이스
사용 가능한 디바이스는 통신 드라이버 설정의 입출력 주소를 참고하시기 바랍니다.

{:.note}
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.
>☞ CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 각 CPU모듈 사용설명서를 참조 바랍니다.













