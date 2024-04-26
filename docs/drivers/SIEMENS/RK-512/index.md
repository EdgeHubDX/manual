---
layout: default
grand_parent: Drivers
parent: SIEMENS
title: RK512
nav_order: 2

---
{: .no_toc }
# Siemens: RK512 Driver
- TOC
{:toc}

## 결선도
### RS-232C
1:1 RS-232C 통신 방식에 대한 결선은 아래와 같습니다. 

![RS-232C]({{ site.url }}/docs/drivers/SIEMENS/RK-512/RS-232C-1.png)

### RS-422(4wire) 통신방식
RS-422/485(4wire) 통신 방식에 대한 결선은 아래와 같습니다.

![RS-422]({{ site.url }}/docs/drivers/SIEMENS/RK-512/RS-422-1.png)

- PLC S7 300/400 의 통신 파라미터

| 파라미터 | 구성                                         |
|------|------------------------------------------|
| 통신속도 | 9600, 19200, 38400, 57600, 76800 중 설정가능    |

| Parity Bit      |  EVEN, ODD, NONE중 설정              |
|-----------------|---------------------------------|
| Data Bit        | 8 Bits                            |
| Stop Bit        | 1 Bit                             |
| 통신방식            | RS-232 or RS422/485               |
| Error Detection | Protocol (With Block Check) 사용    |
| Priority        | Low                               |

{:.note}
>☞ 안정적인 통신을 위해서는 실드 결선을 권장합니다.

## 통신 드라이버 설정
### PLC 설정
- PLC S7 300/400 CP341의 3964(R)/RK512 통신을 위한 설정

![set1]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set1-1.png)

a. “SIMATIC Manager”을 실행하고, 새로운 프로젝트를 생성합니다.   
b. [그림 1]처럼 [Insert], [Station], [사용하고 있는 CPU 타입] (예: 2 SIMATIC 300 Station)을 설정합니다.   

![set2]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set2-1.png)

c. 	[그림 2]와 같이 CPU315-2DP 가 등록된 화면에서 “Hardware”를 선택합니다.

![set3]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set3-1.png)

d. [그림 3]과 같이 Hardware를 등록/설정 하는 화면이 나옵니다. 여기서 사용하고자 하는 Hardware를 등록합니다.   
e.	 [그림 3]과 같이 CPU 및 CP341 232통신모듈을 등록을 하시면 다음 화면이 보입니다.   

![set4]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set4-1.png)

f. [그림 4]와 같이 설정을 하신 후, CPU의 MPI 포트를 설정하기 위하여 슬롯2번의 “CPU315-2 DP”를 더블클릭 합니다.

![set5]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set5-1.png)

g. [그림 5]와 같이 “Properties”를 클릭합니다.

![set6]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set6-1.png)

h. [그림 6]에서 MPI Address(Default로 2로 설정합니다.) 와 MPI Port의 통신속도를 설정합니다. 주의 할 점은 CP 341의 3964(R)/RK512 통신 및 MPI Adapter 를 사용하여 통신을 하기 위해서는 통신속도를 187.5kbps로 설정하여야 합니다.   

i. [그림 4]와 같이 설정을 하신 후, CP 341의 통신설정을 하기 위하여 위의 그림에서 하이라이트 된 부분을 더블 클릭합니다.

![set7]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set7-1.png)

j. [그림 7]에서 Addresses 탭을 선택합니다.

![set8]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set8-1.png)

k. [그림 8]에서 Input Start Address 를 입력합니다. Input Start Address는 [그림 4]에서 Slot의 위치에 따라 달라집니다. 여기서는 4번째 위치하며, 그때의 값은 Start: 256, End: 271 입니다. 이 값을 변경하지 마시고 Default로 설정하시면 됩니다. 아래의 과정 (FB7 P_RCV_RK CP341 수신관련 통신블록 등록 시)에서 이 값들이 사용됩니다. [그림 8]에서 “Parameter” 버튼을 클릭합니다.   

![set9]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set9-1.png)

l. [그림 9] 에서 S7 PLC는 “RK512”를 선택하시고, S5 PLC는 “3964(R)”을 선택합니다. 그리고, 그림처럼 “Protocol”부분을 더블클릭 합니다   

![set10]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set10-1.png)

m. [그림 10]과 같이 통신속성을 설정합니다. “Protocol”부분에서 [Use Default Values]는 Default로 설정하시고, [With Block Check]부분을 사용자가 설정 합니다. 만약, [With Block Check] 부분을 설정하시면, BCC를 체크한다는 뜻이므로 XP Builder에서는 “Block Check(BCC)”를 설정하시면 됩니다. “Priority”는 Low로 설정 하십시오. 위와 같이 설정하셔서 CP 341 모듈 / CPU MPI Port 와 관련된 Hardware 설정을 끝내고, CP 341 통신모듈을 사용하여 외부기기와 통신하기 위하여 로더 프로그램을 작성 합니다.

- PLC S7 300/400 CP341의 3964(R)/RK512 통신을 위한 설정
![set11]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set11-1.png)

n. “FB7 P_RCV_RK CP341”과 같이 수신관련 통신블록을 등록하기 위하여 [그림 11]의 “OB1”을 더블클릭 합니다.

![set12]({{ site.url }}/docs/drivers/SIEMENS/RK-512/set12-1.png)

o. “OB1”내의 로더 프로그램 스텝에 FB Block중 “FB7 CP 341”을 등록합니다. 그리고, 파라미터들은 위의 그림처럼  설정합니다.

이상으로 설정을 Siemens PLC의 설정을 끝냅니다.


### EdgeHub 설정
1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/index.html/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “SiemensRK512”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/SIEMENS/RK-512/channel-add-2.png)

2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/SIEMENS/RK-512/channel-att-2.png)

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
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/index.html/#디바이스-추가)를 참고해 주세요

4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/SIEMENS/RK-512/device-att-2.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.


5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/index.html/#블록-추가)를 참고해 주세요

6. Block 속성 설정
    ![block-att]({{ site.url }}/docs/drivers/SIEMENS/RK-512/block-att-2.png) 

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다.
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 Block의 Block 크기를 Word(2 byte) 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

7. 입출력 주소

    | 영역         | 설명    | 비트접점 | 워드데이터     | 타입 | 영역(Byte)    |
    |------------|-------|------|-----------|----|-----------|
    | I          | 입력릴레이 |      | IW0~IW126 | R  |             |
    | Q          | 출력릴레이 |      | QW0~QW126 | R  |             |
    | T          | 타이머   |      | TW0~TW255 | R  | BCD타입       |
    | C          | 카운터   |      | CW0~CW255 | R  | BCD타입       |
    | M          | 내부메모리 |      | MW0~MW254 | R  |             |
    | DB         | 데이터블럭 |      | DB0. 0 ~  |    |             |
    | DB255. 510 | R/W   |      |           |    |             |


    - IW,QW,MW의 형식    
    ► IW,QW,MW의 형식 : [영역][어드레스]    
    [영역]       : IW,QW,MW   
    [어드레스]   : 바이트단위 (2의 배수 이어야 함)    
    예) IW100, QW50, MW200 등   
    ► TW,CW : [영역][어드레스]     
    [영역]       : TW,CW   
    [어드레스]   : 워드단위  예) 0,1,2,3,4, …   
    예) TW100, TW101 등   
    카운터 및 타이머값은 반드시 BCD 타입으로 설정하여야 합니다.   

    - DB 의 형식 : [영역][블럭번호]. [어드레스]   
    ► 현재 DB100,DB200 디바이스 영역에 대해서 INT16/UINT16 R/W가 가능합니다.   
    [영역]       : DB   
    [블록번호]	 : 블록번호 0~255   
    [어드레스]   : 바이트단위(Decimal) , 0~511 (2의 배수이어야 함)    
    예) DB200.100 (블록번호 200, 100번째 Byte 메모리시작 1WORD )    

    {:.note} 
    >(1) 주의사항   
    >► 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.   
    >(2) 쓰기 경우는 DB100,DB200영역의 INT16/UINT16만 지원합니다.   

## 사용가능 디바이스
사용가능한 디바이스는 통신 드라이버의 입출력 주소를 참고하시기 바랍니다.

{:.note}
>☞ 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.   
>☞ CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 각 CPU모듈 사용설명서를 참조 바랍니다.   

