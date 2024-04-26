---
layout: default
grand_parent: Drivers
parent: Allen Bradley
title: NX-CCU
nav_order: 2
---

{: .no_toc }
# Allen Bradley: NX-CCU
- TOC
{:toc}

## 결선도
RS-232C, RS485 접속 방법으로 NX-CCU와 접속 합니다.
### RS-232C
 
 ![RS-232C]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/RS-232C-1.png)

### RS-485

 ![RS-485]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/RS-485-2.png)

 {:.note}
>WinFPST 로더 케이블을 사용하여 통신이 안될 수 있습니다. 

## 통신드라이버 설정
RS-232C, RS485 접속 방법으로 NX-CCU와 접속 합니다.

### PLC 설정
1. CPU 상의 COM포트 이용 시

    ![PLC-set]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/PLC-set-1.png)

    PLC의 통신 설정은 래더 소프트웨어인 WinFPST 상에서 변경할 수 있습니다.   
    WinFPST 에서 메뉴의 [옵션] -> [시스템 레지스터 설정] -> [COM 포트설정]을 선택하여 아래와 같이 설정할 수 있습니다.

    ![PLC-register-set]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/PLC-register-set-1.png)

    - 동작선택: 컴퓨터 링크
    - 종단 코드: CR
    - 헤더코드: STX 없음
    - 모뎀 접속: 체크하지 않음

    그 외 나머지 설정은 XP-Builder의 통신 상세 설정과 동일하게 맞춥니다.

2. CCU 유닛 이용 시
 
    ![CCU-unit1]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/CCU-unit1-1.png)![CCU-unit2]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/CCU-unit2-1.png)

    PLC의 통신 설정은 밑면 딥 스위치를 통해 설정할 수 있습니다. 

    통신 설정은 아래 표를 참고하시기 바랍니다.

    ![PLC-DSW-1]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/PLC-DSW-1.png)

### EdgeHub 설정
1. 채널 추가
    
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/index.html/#채널-추가)를 참고해 주세요


    - 채널추가 리스트에서 “NXCCU”를 선택한 후 “확인” 버튼을 누릅니다. 

    ![CHANNEL_ADD]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/channel-add-2.png)

2. 채널 속성 설정
  
    ![CHANNEL_ATT]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/channel-att-2.png)

    - 채널명 : 통신채널 이름을 입력합니다. 
    - 채널설명 : 통신채널 설명을 입력합니다.
    - 통신포트#1 : 통신포트를 선택합니다.
    - 통신속도 : 통신 속도를 선택합니다.
    - 패리티비트 : 패리티비트를 선택합니다.
    - 데이터비트 : 데이터비트를 선택합니다.
    - 스톱비트 : 스톱비트를 선택합니다.
    - 타임아웃 : 장비에게 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

3. 디바이스 추가 
  
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/index.html/#디바이스-추가)를 참고해 주세요


4. 디바이스 속성 설정

     ![DEVICE_ADD]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/device-add-2.png)
     
    - 디바이스 명 : 디바이스 이름을 입력합니다.
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : CPU 타입을 선택합니다.
    - Station 번호 : Station 번호를 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

5. Block 추가
   
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/index.html/#블록-추가)를 참고해 주세요

6. Block 설정
    디바이스 속성을 저장하면 Block 설정을 할 수 있습니다. 

    ![BLOCK_ADD]({{ site.url }}/docs/drivers/Allen-Bradley/NXC-CU/block-add-2.png)

    - 블록번호 : 통신 블록 번호를 입력합니다. 블록의 고유 번호이며 같은 번호를 중복하여 사용할 수 없습니다.
    - Block설명 : 통신 블록의 설명을 입력합니다.
    - 시작 Address : 통신 블록의 시작 주소를 입력합니다. 디바이스를 선택하고 주소를 입력합니다.
    - 통신 주기 : 데이터를 요청하는 주기입니다.
    - Block 크기 : 통신 블록의 크기를 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

7. 입출력 주소
    1.	N700a, NX700(CPU750C, CPU750D)  
     
        | 	          |오퍼랜드	  |범위         |
        |:------------|:---------|:------------|
        |비트 오퍼랜드 |  X	      |X0 ~ X511F   |
        |             |  Y       |	Y0 ~ Y511F |
        |             |  R	     |  R0 ~ R886F |
        |             |  L       |	L0 ~ L639F |
        |             |  T	     |T0 ~ T2999   |
        |             |  C	     |C3000 ~ C3071|
        |:------------|:---------|:------------|
        |워드 오퍼랜드 | WX       |WX0 ~ WX511  |
        |             |	WY	     |WY0 ~ WY511  |
        |             |WR	     |WR0 ~ WR886  |
        |             |WL	     |WL0 ~ WL639  |
        |             | DT	     |DT0 ~ DT10239|
	    |             | LD	     |LD0 ~ LD8447 |
	    |             | FL	     |FL0 ~ FL32764|
	    |             | SV	     |SV0 ~ SV3071 |
	    |             |EV	     |EV0 ~ EV3071 |
         
    2. N700H, NX70(CPU750), NX700(CPU750A, CPU750B)

        |	          |오퍼랜드	  |범위         |
        |:------------|:---------|:------------|
        |비트 오퍼랜드 |  X	      |X0 ~ X127F   |
        |             |  Y       |	Y0 ~ Y127F |
        |             |  R	     |  R0 ~ R252F |
        |             |  L       |	L0 ~ L127F |
        |             |  T	     |T0 ~ T999   |
        |             |  C	     |C1000 ~ C1023|
        |:------------|:---------|:------------|
        |워드 오퍼랜드 | WX           |WX0 ~ WX127  |
        |             |	WY	         |WY0 ~ WY127  |
        |             |WR	         |WR0 ~ WR252  |
        |             |WL	         |WL0 ~ WL127  |
        |             | DT	         |DT0 ~ DT5999|
	    |             | LD	         |LD0 ~ LD255 |
	    |             | FL(16K-750A) |FL0 ~ FL14332|
	    |             | FL(32K-750B) |FL0 ~ FL30716 |
	    |             |SV	         |SV0 ~ SV1023 |
        |             |EV            |EV0 ~ EV1023   |


{:.note}
> 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.   
> 디바이스 영역 범위는 접속기기의 CPU에 따라 다르므로 디바이스 영역 범위에 대한 자세한 내용은 접속 기기의 사용설명서를 반드시 확인하여 주십시오.





