---
layout: default
grand_parent: Drivers
parent: LS ELECTRIC
title: MASTER-K PLC
nav_order: 1
---

{: .no_toc }
# LS ELECTRIC: MASTER-K PLC
- TOC
{:toc}

## 1. PLC 목록
접속이 가능한 PLC 목록은 아래와 같습니다.


| PLC 명   | CPU모듈 | 접속 방식 | 통신 방식      | 접속 모듈    | 비고         |
|---------|-------|-------|------------|----------|------------|
| MASTE-K | 1000S | 링크 방식 | RS-232C    | G3L-CUEA | Cnet       |
|         |       | 링크 방식 | RS-422/485 | G3L-CUEA | Cnet       |
|         |       | 링크 방식 | 이더넷        | G3L-EUTB | 오픈형 FEnet  |
|         | 300S  | 링크 방식 | RS-232C    | G4L-CUEA | Cnet       |
|         |       | 링크 방식 | RS-422/485 | G4L-CUEA | Cnet       |
|         |       | 링크 방식 | 이더넷        | G4L-EUTB | 오픈형 FEnet  |
|         | 20R0S | 링크 방식 | RS-232C    | G6L-CUEB | Cnet       |
|         |       | 링크 방식 | RS-422/485 | G6L-CUEC | Cnet       |
|         |       | 링크 방식 | 이더넷        | G6L-EUTB | 오픈형 FEnet  |
|         | 120S  | 링크 방식 | RS-232C    | G7L-CUEB | Cnet       |
|         |       | 링크 방식 | RS-422/485 | G7L-CUEC | Cnet       |
|         | 80S   | 링크 방식 | RS-232C    | G7L-CUEB | Cnet       |
|         |       | 링크 방식 | RS-422/485 | G7L-CUEC | Cnet       |

    
{:.note}
> 1. 지원하지 않는 PLC    
>☞ K10S1은 지원하지 않습니다.   
>☞ 전용 이더넷(GxL-EUTC, ERTC) 모듈은 지원하지 않습니다.   
>2. 용어 설명  
>☞ 링크(Link): PLC 통신모듈과 시리얼 통신하는 것을 말합니다.   

## 2. 결선도
### 2.1 링크방식: Cnet
Cnet은 RS-232C용과 RS-422/485용으로 구분되어 있습니다.
RS-232C Cnet 결선은 다음과 같습니다.

![RS-232]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/RS-232C-1.png)

{:.note}
> MASTER-K Cnet(RS-232C)는 흐름제어를 사용하므로 위와 같이 결선을 하지 않을 경우에는 통신을 하지 않습니다.

RS-422 결선은 아래와 같습니다.

![RS-422]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/RS-422-1.png)
 
RS-485 결선은 아래와 같습니다.

![RS-485]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/RS-485-1.png)

{:.note}
>☞ PC에서 RS-422/485 결선을 사용하려면 RS232 to RS422/485 컨버터가 필요합니다.
>☞ PLC의 RS-422/485 포트는 단자대로 되어 있으므로 별도의 컨버터가 필요 없습니다.

### 2.2 링크방식:FEnet
1. 이더넷 결선
이더넷을 통해 아래와 같이 2가지 형태로 연결할 수 있습니다. 

![hub-node]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/hub-node-2.png)

![1vs1]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/1vs1-2.png)

{:.note}
> ☞ 허브-노드 간 연결할 때에는 다이렉트 케이블을 사용해야 하며, 1:1 연결할 때에는 크로스 케이블을 사용해야 합니다.

2. 이더넷 케이블
이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다. 허브와 같은 네트워크 장비에 연결하여 랜(LAN)망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.

다이렉트 케이블을 제작하는 방법은 아래와 같습니다.

![direct-cable]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/direct-cable-2.png) ![modular-jack]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/modular-jack-2.png)

위의 그림에서 ‘백황’, ‘백녹’, ‘백청’, ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.
예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.
크로스 케이블을 제작하는 방법은 아래와 같습니다.


![cross-cable]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/cross-cable-2.png) ![modular-jack]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/modular-jack-2.png)

{:.note}
>☞ 연결 방식에 맞게 사용하십시오.
>☞ 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.
>☞ 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.
>☞ UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다. 
>☞ 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.

## 3. 통신드라이버 설정
### 3.1 링크 방식: Cnet
1.PLC 설정
PLC(K80S/K120S 제외)의 Cnet 통신 파라미터는 프레임 편집기에서 설정합니다. (해당 PLC의 Cnet I/F Module 사용설명서 참조 바랍니다.) Cnet설정은 다음과 같이 합니다.

![frame-edit]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/frame-edit-1.png)

통신 채널은 ‘RS232 side’로 설정하고 통신 파라미터를 설정합니다. RS-422/485을 설정할 때에는 ‘RS422 side’를 설정하십시오. 모니터등록 크기는 반드시 16 x 20을 선택합니다.

파라미터 값을 PLC에 설정하기 위해서는 아래 그림에서와 같이 Cnet 모듈이 설치되어 있는 슬롯번호를 선택하십시오.

![write]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/write-1.png)

쓰기가 완료되면 아래의 그림과 같이 동작을 개시 하십시오.

![move-edit]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/move-1.png)

Cnet 모듈에서 반드시 동작모드를 설정하여 주십시오.
동작모드 설정은 각 Cnet마다 스위치 설정 값이 다르므로 해당 PLC의 Cnet I/F Module 사용설명서를 참조 바랍니다.

{:.note}
>1. 통신 상태 확인    
>☞ 프레임 편집기에는 모니터 기능이 있습니다. 이 기능을 사용하시면 통신 데이터를 확인할 수 있습니다.   
>☞ Cnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.   
>2. PLC 설정 시 주의사항   
>☞ 프레임 편집기 통신 파라미터 설정 후 반드시 PLC를 리셋시켜 주십시오. (자세한 사항은 사용설명서 참조 바랍니다.)   
>☞ 본 설명서에서는 간략하게 설명하고 있습니다. 설정 시 반드시 해당 PLC의 Cnet I/F Module 사용설명서를 참조 바랍니다.   

K80S/K120S에 Cnet을 사용하기 위해서는 아래와 같이 ‘BUILT_IN CNET’ 스위치를 ‘OFF’로 설정하십시오.

![switch]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/switch-1.png)

통신 파라미터는 KGL-WIN에서 설정합니다.

![param]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/param-1.png)

{:.note}
>1. PLC 설정 시 주의사항
>☞ 본 설명서에서는 간략하게 설명하고 있습니다. 설정 시 반드시 KGL-WIN 사용설명서를 참조 바랍니다.
>2. 설정 시 주의 사항
>☞ RS-422/485를 1:N으로 구성될 때에는 전송 대기 시간을 설정하여 사용하십시오.
>
>![MKCnet]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/MKCnet-1.png)(MKCnet) 
>![MKCnet20]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/MKCnet20-1.png)(MKCnet20)

2. EdgeHub 설정: MKCnet
    1. 채널추가
     자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

     채널추가 리스트에서 “MKCnet”를 선택한 후 “확인” 버튼을 누릅니다.
     
      ![channel_add]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/channel-add-1.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/channel-att-1.png)

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
    
    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 설정
    
    ![block_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/block-att-1.png)

    - 블록번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 아래와 같은 방법으로 Address를 지정합니다.
        - 올바른 예제: D0, F20, M10, P30
        - 잘못된 예제: M0.0.0, F11A
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    - 지원하는 디바이스
    : P, M, K, F, L, D (T, C 디바이스는 지원하지 않습니다.)
    - I/O 어드레스 형식
    : P000(아날로그 태그: 디바이스 뒤의 숫자는 워드영역를 표시합니다.), P00F(디지털 태그 : 맨뒤의 한자리가 비트 영역을 나타냅니다.) 나머지 앞의 영역은 워드영역을 표시합니다.

### 3.2 링크 방식: FEnet
1. PLC 설정
오픈형 FEnet만 지원합니다.(전용 FEnet 모듈은 지원하지 않습니다.) FEnet 통신 파라미터는 고속 이더넷 프레임 편집기에서 설정합니다. (해당 PLC의 FEnet I/F Module 사용설명서 참조 바랍니다.)
소프트웨어를 실행하면 아래와 같이 ‘FENET’을 선택하십시오.

![frame_edit]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/frame-edit-2.png)

IP주소, 게이트웨이 등 통신 파라미터를 설정하십시오.

![basic_set]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/basic-set-2.png)

파라미터 값을 PLC에 설정하기 위해서는 아래 그림에서와 같이 Cnet 모듈이 설치되어 있는 슬롯번호를 선택하십시오.

![write]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/write-2.png)

쓰기가 완료되면 PLC를 리셋하면 설정이 완료됩니다.

{:.note}
>통신 상태 확인 
>☞ PLC FEnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.

2. EdgeHub 설정: MKEnet
    1. 채널추가
     1. 채널추가
     자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

     채널추가 리스트에서 “MKEnet”를 선택한 후 “확인” 버튼을 누릅니다.
     
      ![channel_add]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/channel-add-2.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/channel-att-2.png)

   - 채널 명 : 통신채널 이름을 입력합니다. 
   - 채널 설명 : 통신채널 설명을 입력합니다.
   - 로컬 IP Address  #1 : PC의 IP Address를 입력합니다.
   - 로컬 IP Address  #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
   - 통신 Time Out : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
   - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
   - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.


    3. Device 추가 
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요


    4. Device 속성 설정
    
    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/device-att-2.png)

    - 디바이스 명 : Device 이름을 입력합니다. 
    - 디바이스 설명 : Device 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 2개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 네트웍을 분리하여 통신하고자 할 때 사용합니다. 네트워크 라인에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![line_double]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/line-double-2.png)

    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 1개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 통신 모듈이 분리되어 있는 경우 사용합니다. PLC 통신 모듈에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![device_double]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/device-double-2.png)

    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 포트 번호 : 통신 방식 선택에 따라 자동으로 입력됩니다.
    - 유동 IP 지원 : 유동 IP 를 사용하고자 할 때, 체크합니다. 이 옵션은, hosts 파일 또는 DNS 서버로 부터 IP 어드레스를 얻어와서 통신할때 사용합니다. 따라서 hosts 파일 또는 DNS 서버에 호스트 이름 또는 URL이 등록되어 있어야 합니다. hosts 파일을 이용하는 방식은 다음과 같습니다. hosts 파일은 C:\WINDOWS\system32\drivers\etc 위치에 있습니다. hosts 파일이 아래와 같이 저장되어 있을 때, 유동 IP 는 다음과 같이 설정합니다. (DNS 서버를 이용할 때도, 설정방식은 동일 합니다.)

    ![hosts]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/hosts-2.png)

    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/device-att-2.png)

    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 설정

    ![block_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/MASTER-K-PLC/block-att-2.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 아래와 같은 방법으로 Address를 지정합니다.
        - 올바른 예제: D0, F20, M10, P30
        - 잘못된 예제: M0.0.0, F11A
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    - 지원하는 디바이스
    : P, M, K, F, L, D (T, C 디바이스는 지원하지 않습니다.)
    - I/O Address 형식
    : P000(Analog 태그: 디바이스 뒤의 숫자는 word 영역를 표시합니다.), P00F(Digital 태그 : 맨뒤의 한자리가 bit 영역을 나타냅니다.) 나머지 앞의 영역은 word 영역을 표시합니다.

## 4. 사용 가능 디바이스
사용 가능한 디바이스는 아래와 같습니다. 

| 영역 | 크기       | 비트 접점             | 워드 데이터           |
|----|----------|-------------------|----------------|
| P  | 1024점    | P0000 ~ P063F     | P000 ~ P063      |
| M  | 3072점    | M0000 ~ M191F     | M000 ~ M191      |
| L  | 1024점    | L0000 ~ L063F     | L000 ~ L063      |
| K  | 512점     | K0000 ~ K031F     | K000 ~ K031      |
| F  | 512점     | F0000 ~ F031F     | F000 ~ F031      |
| D  | 10000 워드 | D0000.0 ~ D9999.F | D0000 ~ D9999    |

{:.note}
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.   
>☞ CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 각 CPU모듈 사용설명서를 참조 바랍니다.






 




