---
layout: default
grand_parent: Drivers
parent: LS ELECTRIC
title: XGK PLC
nav_order: 1
---

{: .no_toc }
# LS ELECTRIC: XGK PLC
- TOC
{:toc}

## 1. PLC 목록
접속이 가능한 PLC 목록은 아래와 같습니다.

|PLC 명	| CPU모듈	|접속 방식	|통신 방식	|접속 모듈|	비고|
|:-------|:---------|:--------|:----------|:-------|:-----|
|XGK |	CPUH |링크 방식|RS-232C|	XGL-C22A, XGL-CH2A|Cnet|
|     | CPUA |링크 방식|RS-422/485	|XGL-C42A, XGL-CH2A|Cnet|
|     |  CPUS|링크 방식|이더넷	|XGL-EFMT|-|
|     |  CPUE|||||
|      |  CPUU|||||		
||CPUHN|||||
||CPUSN|||||
||CPUUN|||||

{:.note}
>1. 지원하지 않는 PLC 
>☞ 광 이더넷 모듈(XGL-EFMF)은 지원하지 않습니다.
>2. 용어 설명
>☞ 링크(Link): PLC 통신모듈과 시리얼 통신하는 것을 말합니다.

## 2. 결선도
### 2.1 링크방식: Cnet
Cnet은 RS-232C용과 RS-422/485용으로 구분되어 있습니다.
RS-232C Cnet 결선은 다음과 같습니다.

![Cnet1]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/Cnet1-1.png)

RS-422 결선은 아래와 같습니다.

![Cnet2]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/Cnet2-1.png)

RS-485 결선은 아래와 같습니다.

![Cnet3]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/Cnet3-1.png)

{:.note}
>☞ PC에서 RS-422/485 결선을 사용하려면 RS232 to RS422/485 컨버터가 필요합니다.
>☞ PLC의 RS-422/485 포트는 단자대로 되어 있으므로 별도의 컨버터가 필요 없습니다.

### 2.2 링크방식: FEnet
1. 이더넷 결선
이더넷을 통해 아래와 같이 2가지 형태로 연결할 수 있습니다.
![hub_node]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/hub-node-2.png)

![1vs1]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/1vs1-2.png)

{:.note}
>☞ 허브-노드 간 연결할 때에는 다이렉트 케이블을 사용해야 하며, 1:1 연결할 때에는 크로스 케이블을 사용해야 합니다.

2. 이더넷 케이블
이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다. 허브와 같은 네트워크 장비에 연결하여 랜(LAN)망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.

다이렉트 케이블을 제작하는 방법은 아래와 같습니다.

![direct_cable]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/direct-cable-2.png) ![modular_jack]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/modular-jack-2.png)

위의 그림에서 ‘백황’, ‘백녹’, ‘백청’, ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.
예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.
크로스 케이블을 제작하는 방법은 아래와 같습니다.

![corss_cable]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/cross-cable-2.png) ![modular_jack]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/modular-jack-2.png)

{:.note}
>☞ 연결 방식에 맞게 사용하십시오.
>☞ 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.
>☞ 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.
>☞ UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다. 
>☞ 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.

## 3. 통신드라이버 설정
### 3.1 링크 방식: Cnet
1. PLC 설정
PLC의 Cnet 통신 파라미터는 XG-PD에서 설정합니다. (XGT Cnet 사용설명서 참조 바랍니다.)
Cnet설정은 다음과 같이 합니다.

![module]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/module-1.png) ![Cnet]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/Cnet-1.png)

설정하고자 하는 채널에 통신 파라미터를 설정합니다. 동작 모드는 XGT 서버를 선택하십시오.
설정한 정보를 PLC에 쓰기가 완료되면 PLC를 리셋하여 주십시오.

{:.note}
>1. 통신 상태 확인 
>☞ XG-PD에는 모니터 기능이 있습니다. 이 기능을 사용하시면 통신 데이터를 확인할 수 있습니다.
>☞ Cnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.
>2. PLC 설정 시 주의사항
>☞ XG-PD에서 통신 파라미터 설정 후 반드시 PLC를 리셋시켜 주십시오.
>☞ 본 설명서에서는 간략하게 설명하고 있습니다. 설정 시 반드시 XGT Cnet 사용설명서를 참조 바랍니다.
>☞ 2개의 채널을 사용하지 않고 1개만 사용할 때에도 다른 채널의 통신 형태를 설정하여 주십시오.

2. EdgeHub 설정: XGKCnet
    1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “XGIEnet”를 선택한 후 “확인” 버튼을 누릅니다. 

    ![channel_add]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/channel-add-1.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/channel-att-1.png)

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

    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정
    ![block_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/block-att-1.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 아래와 같은 방법으로 Address를 지정합니다.
        - 올바른 예제: D0, F20, M10, P30, R20, ZR20
        - 잘못된 예제: M0.0.0, F11A 
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    7. 입출력 주소
    - 형식
        - 아날로그 : D20, F10, M30, P0, R20
        - 디지털 : D20A, F105, M30F, P01, R20F (마지막 문자가 해당 Word 값의 비트 위치를 나타냅니다. 0 ~ F 까지 사용 가능)
    - 사용가능한 디바이스
        - D, F, K, M, P, R, ZR

### 3.2 링크 방식:FEnet
1.	PLC 설정
FEnet 통신 파라미터는 XG-PD에서 설정합니다. (XGT FEnet 사용설명서 참조 바랍니다.)

![XG-PD]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/XG-PD-2.png)

![module]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/module-2.png)

통신 모듈을 설정할 때는 FEnet으로 설정하십시오.
IP주소, 게이트웨이 등 통신 파라미터를 설정하십시오. 드라이버 설정에서 XGT 서버를 선택하십시오.

![basic_set]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/basic-set-2.png)

쓰기가 완료되면 PLC를 리셋하십시오. PLC 또는 모듈이 리셋되면 설정이 완료됩니다.

{:.note}
>통신 상태 확인 
>☞ PLC FEnet 모듈에 RX, TX LED가 있습니다. 정상적으로 통신이 이루어지면 LED가 빠르게 점멸합니다.

2. EdgeHub 설정 : XGKEnet
 1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “XGKEnet”를 선택한 후 “확인” 버튼을 누릅니다. 

    ![channel_add]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/channel-add-2.png)

    2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/channel-att-2.png)

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

    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/device-att-2.png)   

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 2개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 네트웍을 분리하여 통신하고자 할 때 사용합니다. 네트웍 라인에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![line_double]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/line-double-2.png)

    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 컴퓨터에 랜카드 1개를 설치하고, PLC에 Enet 통신 모듈을 2개 설치하여, 그림과 같이 통신 모듈이 분리되어 있는 경우 사용합니다. PLC 통신 모듈에 이상이 있을때를 대비하기 위한 이중화 옵션 입니다.

    ![device_double]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/device-double-2.png)

    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 포트 번호 : 통신 방식 선택에 따라 자동으로 입력됩니다.
    - 유동 IP 지원 : 유동 IP 를 사용하고자 할 때, 체크합니다. 이 옵션은, hosts 파일 또는 DNS 서버로 부터 IP 어드레스를 얻어와서 통신할때 사용합니다. 따라서 hosts 파일 또는 DNS 서버에 호스트 이름 또는 URL이 등록되어 있어야 합니다. hosts 파일을 이용하는 방식은 다음과 같습니다. hosts 파일은 C:\WINDOWS\system32\drivers\etc 위치에 있습니다. hosts 파일이 아래와 같이 저장되어 있을 때, 유동 IP 는 다음과 같이 설정합니다. (DNS 서버를 이용할 때도, 설정방식은 동일 합니다.)

    ![hosts]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/hosts-2.png)

    ![device_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/device-att-2.png)

    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

    6. Block 속성 설정
    ![block_att]({{ site.url }}/docs/drivers/LS-ELECTRIC/XGK-PLC/block-att-2.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 아래와 같은 방법으로 Address를 지정합니다.
        - 올바른 예제: D0, F20, M10, P30, R20, ZR20
        - 잘못된 예제: M0.0.0, F11A 
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

	7. 입출력 주소
    - 형식
        - 아날로그 : D20, F10, M30, P0, R20
        - 디지털 : D20A, F105, M30F, P01, R20F (마지막 문자가 해당 Word 값의 비트 위치를 나타냅니다. 0 ~ F 까지 사용 가능)
    - 사용가능한 디바이스
        - C, D, F, K, M, P, R, T, U, ZR

## 4. 사용 가능 디바이스
사용 가능한 디바이스 아래와 같습니다. 

| 영역 | 크기      | 비트 접점               | 워드 데이터             |   
|----|---------|---------------------|--------------------|
| P  | 32768점  | P00000 ~ P2047F     | P0000 ~ P2047      |   
| M  | 32768점  | M00000 ~ M2047F     | M0000 ~ M2047      |  
| K  | 32768점  | K00000 ~ K2047F     | K0000 ~ K2047      |   
| F  | 32768점  | F00000 ~ F2047F     | F0000 ~ F2047      |   
| T  | 2048점   | T0000 ~ T2047       | T0000 ~ T2047      |   
| C  | 2048점   | C0000 ~ C2047       | C0000 ~ C2047      |   
| U  | 3072 워드 | U00.00.0 ~ U7F.31.F | U00.00 ~ U7F.31    |   
| D  | 32K 워드  | D00000.0 ~ D32767.F | D00000 ~ D32767    |   
| ZR | 32K 워드  | -                   | ZR00000 ~ ZR65535  |   
| R  | 32K 워드  | R00000.0 ~ R32767.F | R00000 ~ R32767    |   

{:.note}
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.
>☞ CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 각 CPU모듈 사용설명서를 참조 바랍니다.






