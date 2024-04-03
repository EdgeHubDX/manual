layout: default
parent: Drivers
title: BACnetIP
nav_order: 3
---
# BACnetIP 
## 1. 통신드라이버 설정
### 1.1 EdgeHub 설정

1. 채널 추가
    1. Field Device 트리에서 Field Device를 클릭 후, 추가 버튼을 누르면 추가할 채널의 드라이버를 선택하는 화면이 열립니다. 

     사진 첨부
    
    2. 채널추가 리스트에서 “BACnetIP”를 선택한 수 “확인” 버튼을 누릅니다. 

       사진 첨부

2. 채널 속성 설정
 
  사진 첨부

    - 채널명 : 통신채널 이름을 입력합니다.
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP 주소 #1 : PC의 IP Address를 입력합니다.
    - 통신 TimeOut : 장비에게 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

3. 디바이스 추가
    Field Device 트리에서 추가한 BACNet 채널을 클릭 후, 추가 버튼을 누르면 디바이스를 추가할 수 있는 화면이 열립니다. 

     사진 첨부

4. 디바이스 속성 설정
   
   사진첨부

    - 디바이스명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - CPU 종류 : CPU 종류는 BACnetIP 로 고정되어 있습니다.
    - MAC Address : 통신하고자 하는 장비의 Address를 입력합니다.
    - Network Number : 사용안함.
    - Network Address : 사용안함.
    - 통신 방식 : BACnetIP는 UDP 통신 방식을 사용합니다.
    - 포트 번호 : BACnetIP는 47808을 사용합니다.
    - 제어 우선순위 : 제어 우선순위를 설정합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

5. 입출력 주소
    1. 형식
        - [오브젝트 이름][인스턴스No].[속성 No].[아이템 No]
        - 예제 : AI4.75.1, AI4.45 등 

        {:.note}
        > [아이템 No]는 [속성 No]의 종류에 따라 생략될 수 있습니다. 각 오브젝트 별 속성 No 테이블에서 아이템 유무를 확인 해 주십시오.

    2. 오브젝트 이름

        |오브젝트 이름	|설명    |
        |:-------------|:-------|
        |AI|	Analog Input|
        |AO	|Analog Output|
        |AV	|Analog Value|
        |BI	|Binary Input|
        |BO	|Binary Output|
        |BV	|Binary Value|
        |CD	|Calendar|
        |CM	|Command|
        |DV	|Device|
        |ER	|Event Enrollment
        |FI	File
        |GR	Group
        |LP	Loop
        |MI	Multi State Input
        |MO	Multi State Output
        |NC	Notification Class
        |PG	Program
        |SC	Schedule
        |MV	Multi State Value




