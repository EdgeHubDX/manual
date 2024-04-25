---
layout: default
grand_parent: Drivers
parent: Allen Bradley
title: Ethernet/IP
nav_order: 1
---

{: .no_toc }
# Allen Bradley: Ethernet/IP

- TOC
{:toc}

## PLC 설정
### Control/CompactLogix 시리즈
Control/CompactLogix 시리즈에서는 RSLogix5000 프로그램을 이용하여 사용자가 직접 Tag를 정의해서 사용합니다.  

- RSLogix5000 프로그램을 실행 후 상단 메뉴 [Communication] -> [Who Active] 선택하십시오.

  ![PLC-set]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/PLC-set-1.png)

- 검출된 PLC와 접속하여 사용할  Tag를 정의하고 등록합니다. 

{:.note}
>PLC의 통신 설정이나 태그 생성 방법은 RSLogix5000 사용 설명서 참조하시기 바랍니다. 

### MicroLogix 시리즈
- RSLogix500(또는 RS Logix Micro) 프로그램을 실행 후 상단 메뉴 [Comms] -> [Who Active Go Online] 선택하십시오.

  ![PLC-ML]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/PLC-ML-1.png)

- [Create New File] 클릭하면 접속 완료 됩니다.

  ![PLC-create]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/PLC-create-1.png)

- 접속된 PLC에 사용할 Tag를 정의하고 등록합니다.

{:.note}
>PLC의 통신 설정이나 태그 생성 방법은 RSLogix5000 사용 설명서 참조하시기 바랍니다. 

## EdgeHub 설정
### 채널 추가
   
자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

- 채널추가 리스트에서 “ABEthernetIP”를 선택한 후 “확인” 버튼을 누릅니다. 

  ![channel-add]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/channel-add-2.png)

### Control/CompactLogix 시리즈
1. 채널 속성 설정  
  ![channel-att]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/channel-att-2.png)

    - 채널명 : 통신채널 이름을 입력합니다. 
    - 채널설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP 주소 #1 : PC의 IP Address를 입력합니다.
    - 로컬 IP 주소 #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
    - 통신 TimeOut : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

2. 디바이스 추가   
  자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

3. 디바이스 속성 설정  
  ![device-add]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/device-add-2.png)
    
    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : CPU Type을 선택합니다. (Contrl/Compact를 선택합니다.)
    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 
    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 
    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP 방식으로 고정되어 사용됩니다.
    - 포트 번호 : EthernetIP는 44818포트로 고정되어 사용됩니다. 
    - 확장베이스슬롯 : EtherNet/IP 통신 모듈이 장착되어 있는 슬롯이 확장 베이스에 장착되어 있을 경우에 확장 베이스 슬롯 번호를 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

4. Block 추가
  자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

5. Block 설정  
  디바이스 속성을 저장하면 Block 설정을 할 수 있습니다.  
    ![block-add]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/block-add-2.png)

    - 블록번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : EtherNet/IP의 통신블록의 시작Address는 PLC에서 등록한 태그 이름을 어드레스로 사용합니다. 
        - PLC에서 INT_A1_TAG 이름으로 Data타입을 INT형으로 배열0~99까지 100개를 할당했다면, 시작어드레스는 INT타입, INT_A1_TAG[0]으로 데이터수는 100으로 설정합니다.
        - PLC에서 BOOL_A_TAG 이름으로 Data타입을 BOOL형으로 배열0~99까지 100개를 할당했다면, 시작어드레스는 BOOL타입, BOOL_A_TAG[0]으로 데이터수는 100으로 설정합니다.   
          BOOL형의 시작주소는 항상 32의 배수이어야 합니다.
        - 데이터 수는 PLC에 정의된 범위 내에서 입력하여야하며 최대 100개 이하로 입력하여야 합니다.   
          (Float 타입의 경우에는 50개 이하)
    - 데이터 수 : 해당 구별자별 읽고자하는 개수를 입력합니다.
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.


6. 입출력 주소
    - 형식
        - 태그이름[Array 번호]
        - 태그이름[Array 번호].0 ~ 태그이름[Array 번호].15
        - 태그이름[Array 번호].0 ~ 태그이름[Array 번호].31   
        참고) Array 타입의 주소 형식만 지원합니다.

    - 데이터 타입 

        | PLC 태그의 데이터 타입  | 블록의 데이터 타입 | 태그의 장비 데이터 타입 |
        |:-----------------------|:-----------------|:----------------------|
        | BOOL                   | BOOL             | Digital(태그 타입)     |
        | SINT                   | SINT             | INT8                  |
        | INT                    | INT              | INT16                 |
        | DINT	                 | DINT	            | INT32                 |
        | USINT	                 | USINT	        | UINT8                 |
        | UINT	                 | UINT	            | UINT16                |
        | UDINT	                 | UDINT	        | UINT32                |
        | REAL	                 | REAL	            | FLOAT                 |

    - 예1) BOOL Array Type의 통신 블록 설정 및 입출력 주소 입력   
      RS Logix 5000 에서 BOOL형의 Array 타입 태그 BOOL0을 BOOL0[0]부터 BOOL0[49]까지 50개를 설정하였다면, 통신블록에 아래와 같이 입력합니다.

      ![block-att]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/block-att-2.png)

      ※ [주의] 시작 어드레스는 반드시 32의 배수가 되어야 합니다   
      예) TEST_1[0], TEST_1[32], TEST_1[512]

    - 예2) INT Array Type의 통신 블록 설정 및 입출력 주소 입력
      RS Logix 5000 에서 INT형의 Array 타입의 태그 N125[0]부터 N125[49]까지 50개를 설정하였다면,  통신블록에 아래와 같이 입력합니다.

      ![block-att2]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/block-att2-2.png)

    - 입출력 주소 예 
      BOOL0[0], BOOL0[1], BOOL0[30], BOOL0[31]
      N125[0], N125[1], N125[30], N125[31]

### MicroLogix 시리즈
1. 채널 속성 설정   
  Control/CompactLogix 시리즈의 채널 속성 설정과 동일합니다.

2. 디바이스 속성 설정   
  PLC CPU 종류를 “slc500/Micro”로 선택 합니다.   
  나머지 속성은 	Control/CompactLogix 시리즈의 디바이스 속성과 동일합니다.

  ![device-mod]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/device-mod-2.png)

3. Block 추가  
  ![block-att3]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/block-att3-2.png)

    - 블록번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 데이터 수 : 해당 구별자별 읽고자하는 개수를 입력합니다.
    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다. 
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.
    - 시작 Address : EtherNet/IP의 통신블록의 시작Address는 PLC에서 등록한 태그 이름을 기준으로 하여 아래와 같은 형식으로 입력합니다.

      - 블록 시작 Address는 어드레스의 타입과 무관하게 UINT(2byte) 타입을 고정으로 사용합니다.
      - 데이터 수는 PLC에 정의된 범위 내에서 입력하여야하며 최대 100개 이하로 입력하여야 합니다.   
        (Float 타입의 경우에는 50개 이하)

      - 워드 타입의 N7:0, N7:2, N7:31 의 I/O 주소를 사용하는 태그들을 하나의 블록으로 설정할 경우에는 아래와 같이 블록을 설정하면 됩니다.
          - 블록 시작주소: N7:0
          - 데이터 수: 32

      - 디지털 타입의 B3:0/1, B3:1/7, B3:2/15 의 I/O 주소를 사용하는 태그들을 하나의 블록으로 설정할 경우에는 아래와 같이 블록을 설정하면 됩니다. 
          - 블록 시작주소: B3:0  (블록 시작주소는 WORD 타입으로 설정하여야 합니다.)
          - 데이터 수: 3         (WORD offset 만큼 데이터 수를 설정하면 됩니다.)

      - Input 타입의 I:0.0/1, I:0.1/7, I:0.2/15 의 I/O 주소를 사용하는 태그들을 하나의 블록으로 설정할 경우에는 아래와 같이 블록을 설정하면 됩니다.
          - 블록 시작주소: I:0.0  (블록 시작주소는 WORD 타입으로 설정하여야 합니다.)
          - 데이터 수: 3         (WORD offset 만큼 데이터 수를 설정하면 됩니다.)

      - Output 타입의 O:0.0/1, O:0.1/7, O:0.2/15 의 I/O 주소를 사용하는 태그들을 하나의 블록으로 설정할 경우에는 아래와 같이 블록을 설정하면 됩니다.
          - 블록 시작주소: O:0.0  (블록 시작주소는 WORD 타입으로 설정하여야 합니다.)
          - 데이터 수: 3          (WORD offset 만큼 데이터 수를 설정하면 됩니다.)

      - Float 타입의 F8:0, F8:2, N8:4 의 I/O 주소를 사용하는 태그들을 하나의 블록으로 설정할 경우에는 아래와 같이 블록을 설정하면 됩니다.
          - 블록 시작주소: F8:0  (블록 시작주소는 WORD 타입으로 설정하여야 합니다.)
          - 데이터 수: 10        (Float 타입의 경우에는 x2를 하여야 합니다. [예] 5 x 2 = 10 )

          ![block-att4]({{ site.url }}/docs/drivers/Allen-Bradley/Ethernet-IP/block-att4-2.png)

4. 입출력 주소           
  slc500 및 Mirco Logix 의 주소 형식 중에서 지원하는 태그의 입출력 주소 형식은 아래와 같습니다.

    - File Name: N, B, I, O, F
    - 주소 형식 예   
      N7:0, N7:1, B3:0/1, B3:7/15, I:0.0/1, I:0.1/15, O:0.0/0, O:0.2/15, F8:0, F8:2   
      참고) 위의 예로 제시한 형식의 주소만 지원합니다.

    - PLC에 정의된 범위를 벗어나지 않는 I/O 주소를 사용하여야 합니다.

### XGT EthenetIP (XGL-EIPT 모듈)   
앞의 2. Control/CompactLogix 시리즈 의 도움말을 참고하시면 됩니다. (디바이스 속성 설정에서 PLC CPU 종류만 “XGT_EIP”로 선택하시고, 나머지는 Control/CompactLogix와 동일한 방식으로 설정하여 사용가능 합니다.)




