---
layout: default
grand_parent: Drivers
parent: SIEMENS
title: ISOEnet
nav_order: 1
---

{: .no_toc }
# Siemens: ISOEnet
- TOC
{:toc}

## 통신드라이버 설정
### PLC 설정
도움말 작성 간에 사용된 Siemens PLC의 구성은 아래와 같습니다.
- CPU313C-2 DP
- CP 343-1 EX30-0XE0

Siemens PLC은 전용 프로그램인 ‘SIMATIC Manager’를 이용하여 설정할 수 있습니다.

1. 프로젝트 생성
    SIMATIC Manager를 실행하여 [File] -> [‘New Procject’ Wizard]를 클릭합니다.

    ![project]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/project-1.png)

    사용할 CPU의 종류를 선택합니다.

    ![CPU]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/CPU-set-1.png)

    프로젝트 명을 입력하고 Finish 버튼을 누르면 해당 이름으로 프로젝트가 생성됩니다. 

    ![finish]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/finish-1.png)

2.	하드웨어(통신 모듈) 추가
    좌측 트리의 ‘SIMATIC 300 Station’을 선택하고, 우측의 ‘Hardware’를 우클릭하면 아래와 같이 팝업 메뉴가 나타납니다. 

    ![hw-set]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/hw-set-1.png)

    'Open Object'를 클릭하여 'HW Config' 창을 실행시킵니다.

    4번 슬롯을 우클릭하여 팝업 메뉴의 'Insert Object'를 선택합니다.

    ![insert-obj]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/insert-object-1.png)

    아래와 같이 사용할 하드웨어를 선택하여 추가합니다. (본 도움말에서는 'CP 343-1 EX30-0XE0'를 사용함.)

    ![hw-select]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/hw-select-1.png)

    사용할 하드웨어를 선택하면 아래와 같은 설정창이 화면에 표시됩니다.

    ![ip-address]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/ip-address-1.png)

    PLC 통신모듈에 설정한 IP Address를 입력하고, 우측 아래 [New]버튼을 클릭하여 Ethernet(1)을 추가합니다.

    본 도움말에서 사용할 CP 343-1 EX30-0XE0 모듈이 아래와 같이 추가 됩니다.

    ![CP343]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/CP343-1.png)

    화면 상단의 다운로드 아이콘을 클릭하여 PLC에 해당사항을 다운로드합니다.
    ![PLC]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/PLC-1.png)

3. 데이터 블록 추가
    좌측 트리의 [Blocks]를 우클릭하여 팝업 메뉴를 화면에 표시합니다.
    ![popup]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/popup-1.png)

    팝업 메뉴의 [Insert New Object] -> [Data Block]을 선택하면 아래와 같은 설정창이 화면에 표시됩니다.

    ![datablock](({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/datablock-1.png)

    생성된 데이터 블록(DB1)을 우클릭 하여 [Open Object]를 선택합니다.

    ![open-obj]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/open-object-1.png)

    사용할 변수(Tag)들을 아래와 같이 설정합니다.

    ![tag]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/tag-1.png)

4. 변수 값 모니터링 및 변경
    PLC 운용 간에 설정된 변수(Tag)들의 값을 모니터링 및 제어할 수 있습니다.

    SIMATIC Manager의 [PLC] -> [Monitor/Modify Variables]를 클릭합니다.

    ![monitoring]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/monitoring-1.png)

    Address에 모니터링 및 제어할 변수의 주소를 입력합니다.   
    Status Value에는 현재 값이 표시되고, Modify value에 값을 입력하면 해당 값으로 제어할 수 있습니다.   

    ![status-value]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/status-value-1.png)

    TIA Portal 에서 Siemens PLC 설정 확인 
    - Optimized block access 체크 해제

    ![optimized]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/optimized-1.jpg)

    - 아래 항목 선택 및 체크 설정
    ![check]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/check-1.jpg)

    {:.note}
    >☞ 본 도움말에 언급된 PLC 설정 내용은 도움말 작성 간에 포함된 PLC 설정을 간략히 설명한 것입니다.   
    >☞ 자세한 PLC의 통신 설정이나 태그 생성 방법은 SIMATIC Manager 및 해당 Siemens PLC 의 사용 설명서 참조하시기 바랍니다.   

### EdgeHub 설정
SiemensISOEnet 통신드라이버는 지멘스의 ‘ISO on TCP’ 프로토콜의 Client로 동작합니다. 따라서 PLC는 ISO On TCP서버로 동작해야 하며, 이더넷 카드가 이를 지원하는지 먼저 확인해야 합니다. 사용이 가능한 경우 채널 설정에서 SiemensISOEnet 드라이버를 선택하고 아래와 같이 설정합니다.
1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “SiemenSISOEnet”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/channel-add-2.png)

2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/channel-att-2.png)

    - 채널 명 : 통신채널 이름을 입력합니다. 
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - Channel Type : 채널 타입을 선택합니다. (ISO_Over_TCP를 선택합니다.)
    - Time Out : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - Retry Count : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.



3. Device 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/device-att-2.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC IP Address : PLC 의 IP Address를 입력합니다.
    - Port No : 포트 번호를 입력합니다.
    - Station No : 스테이션 번호를 입력합니다.
    - Base : 베이스 번호를 입력합니다.
    - Slot : 슬롯 번호를 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

    {:.note}
    >☞ Port와 스테이션 No는 기본값 102,1를 입력합니다. 만약 Stn ID나 PortNo나 변경한 경우 해당하는 번호를 입력합니다.    
    >☞ S-300 은 Base는 0 Slot은 2이 기본값 입니다.   
    >☞ S-400 은 Base는 0 Slot은 3이 기본값 입니다. (Power가 두 슬롯을 차지하기 때문입니다.)   
    >☞ 1개 이상의 PLC를 등록하는 경우 스테이션은 하나의 채널에서만 등록합니다. %채널은 하나만 등록해야 합니다.   


5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

6. Block 속성 설정
    ![block-att]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/block-att-2.png) 

    - Block No : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Description : Block 설명을 입력합니다.
    - Start Address : 시작어드레스는 PLC에서 사용하는 어드레스를 그대로 사용합니다. 
    (Ex DB1.DBW0 , MB0, AIW0,..)
    - Data Length : 해당 Block에서 수집할 데이터의 크기를 입력합니다.
    (1개의 데이터 블록은 최대 210Bytes를 넘길 수 없습니다.)
    - Period : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

    {:.note}
    >☞ 시작어드레스는 PLC에서 사용하는 어드레스를 그대로 사용합니다. (Ex DB1.DBW0 , MB0, AIW0,..)   
    >☞ 1개의 데이터 블록은 최대 210Bytes를 넘길 수 없습니다.   
    >☞ 따라서 210Byte가 넘는 경우는 여러 개 블록으로 쪼개서 등록합니다.   

7. 입출력 주소
- Siemens ISOEnet 통신드라이버에서 제공하는 입출력 주소 영역은 아래와 같습니다.
    - DB 영역은 PLC설정에서 연속된 태그로 설정이 되어 있어야 통신이 가능합니다.

![io-address]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/IO-address-2.jpg)

- 비트접점
Ex) I120.7, Q50.3, M511.1 등
Ex) DB100.DBX7500.7 (블록번호 100, 7500 번째 Byte 의 7번째 Bit)

- 워드접점
Ex) IW100, QW50, MW500 등
Ex) DB300. DBW100 (블록번호 300, 100 번째 Byte로부터 2bytes 메모리)

- SIMATIC Manager에서 Monitor/Modify Variables를 통한 변수 모니터링 및 변경 화면
![simatic-manager]({{ site.url }}/docs/drivers/SIEMENS/ISO-Enet/simatic-manager-2.png)

- PLC어드레스는 S7에서 사용하는 어드레스 포맷을 그대로 사용한다.   
    Data blocks: 	DB3.DBW4, DB1.DBW0   
    Flags/Markers: 	MW4, MW100.10   
    Input memory: 	IB0, I0.10   
    Output memory: 	QB8, Q10.2   
    Timers daveTimer: 	T2    
    Counters: 	C2   
    Direct I/O: 	PIW4, PIW10.5   
    Data (V-memory) in S7-200: 	VW1234   
    Analog input words of 200 family: AIW0    
    Analog output words of 200 family: AQW0?   





