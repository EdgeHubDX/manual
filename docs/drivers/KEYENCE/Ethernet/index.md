---
layout: default
grand_parent: Drivers
parent: KEYENCE
title: Ethernet
nav_order: 1
---

{: .no_toc }
# KEYENCE: Ethernet
- TOC
{:toc}

## 연결 가능 PLC 
 접속 가능한 PLC 목록은 다음과 같습니다.

  | PLC 명          | CPU모듈   | 접속방식 | 통신방식 | 접속모듈                                      |
 |----------------|---------|------|------|-------------------------------------------|
 | KV-700 Series  | KV-700  | 링크방식 | 이더넷  | KV-LE20V , KV-LE21V                       |
 | KV-1000 Series | KV-1000 | 링크방식 | 이더넷  | KV-LE20V , KV-LE21V                       |
 | KV-3000 Series | KV-3000 | 링크방식 | 이더넷  | KV-LE20V , KV-LE21V                       |
 | KV-5000 Series | KV-5000 | 링크방식 | 이더넷  | KV-LE20V , KV-LE21V,Ethernet port on CPU  |
 | KV-5500 Series | KV-5500 | 링크방식 | 이더넷  | KV-LE20V , KV-LE21V, Ethernet port on CPU |


  {:.note}
  >1. 용어 설명   
   >► 링크: PLC 통신 모듈과 통신하는 것을 말합니다.
  >2. 프로그래밍 툴   
   >► KV Studio
  >3. 주의사항   
   >► 자세한 지원 정보는 KEYENCE 사용설명서를 참조하십시오. 또한 지원 사항은 본 제품과 무관하게 KEYENCE 사에 의해 변경될 수 있습니다.

## 결선도
 이더넷 케이블은 연결 형태에 따라 2가지 케이블로 나누어 집니다.   
 허브와 같은 네트워크 장비에 연결하여 랜 망으로 통신할 때는 다이렉트 케이블을 사용합니다. (허브-노드 간 연결 시)   
 랜 망을 사용하지 않고 기기 간에 직접 연결할 수 있는데, 이 때는 크로스 케이블을 사용합니다.   

 다이렉트 케이블을 제작하는 방법은 아래와 같습니다.   
 ![direct_cable]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/direct-cable.png) ![modular_jack]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/modular-jack.png)

 위의 그림에서 ‘백황’,  ‘백녹’,  ‘백청’,  ‘백갈’은 케이블 피복에 색 띠로 표시되어 있습니다.   
 예를 들면 ‘백청’은 흰색 피복에 파란색 색 띠로 제작되어 있습니다.   

 크로스 케이블을 제작하는 방법은 아래와 같습니다.   
 ![cross_cable]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/cross-cable.png) ![modular_jack]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/modular-jack.png)

 {:.note}
 >- 연결 방식에 맞게 사용하십시오.
 >- 모듈러 전용 툴을 이용하여 케이블을 제작하십시오. 접촉 불량이 발생할 수 있습니다.
 >- 모듈러 잭의 로크(Lock) 부분이 파손되면 RJ45 커넥터(이더넷 커넥터)에 고정이 안되어 접촉 불량이 발생할 수 있습니다.
 >- UTP 케이블은 단선 재질이므로 무리하게 케이블을 꺾거나 흔들면 케이블이 끊어지거나 특성이 나빠질 수 있습니다. 
 >- 케이블 제작 시 플러그 커버(Plug Cover) 사용을 권장합니다.
 >- PLC의 Ethernet 유닛의 IP 주소와 InfoU 의 IP 주소가 다른 장치와 중복되지 않게 설정해야 합니다. IP 주소 중복 시 사내 네트워크 관리자에게 문의하십시오.

## 통신 드라이버 설정
### PLC 설정
1. KV-LE2*V 유닛 설정   
    KV STUDIO에서 메뉴 [Tool]-[Unit Editor]를 선택합니다.   
    Unit Editor에서 KV-LE20V 또는 KV-LE21V 유닛을 추가합니다.   
    KV-LE21 유닛 설정에서 [IP address]를 입력합니다.   
    Uplink 포트 번호를 입력합니다. (기본: 8501)   

    ![uplink_port]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/uplink-port-1.png)

2. KV-5000/5500 Ethernet Port on CPU 설정   
   KV STUDIO에서 메뉴 [Tool]-[Unit Editor]를 선택합니다.    
   Unit Editor에서 CPU를 선택합니다.    
   CPU 설정에서 [IP address]를 입력합니다.   
   Uplink 포트 번호를 입력합니다. (기본: 8501)   

   ![uplink_port2]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/uplink-port2-1.png)

### EdgeHub 설정

1. 채널추가

    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요
    
    - 채널 추가 리스트에서 “KeyenceE”를 선택한 후 “확인” 버튼을 누릅니다. 

    ![channel_add]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/channel-add-2.png)


2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/channel-att-2.png)
  
    - 채널명 : 통신채널 이름을 입력합니다. 
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP 주소 #1 : PC의 IP Address를 입력합니다.
    - 로컬 IP 주소 #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
    - 통신 TimeOut : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

3. 디바이스 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

4. 디바이스 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/device-att-2.png) 
    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - 라인 이중화 : 라인 이중화를 사용할 경우 체크 합니다. 
    - 장비 이중화 : 장비 이중화를 사용할 경우 체크 합니다. 
    - PLC IP Address #1-1 : PLC 의 IP Address를 입력합니다.
    - PLC IP Address #1-2 : PLC 의 IP Address를 입력합니다. 라인 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-1 : PLC 의 IP Address를 입력합니다. 장비 이중화를 사용할 때 입력합니다.
    - PLC IP Address #2-2 : PLC 의 IP Address를 입력합니다. 라인 이중화와 장비 이중화를 함께 사용할 때 입력합니다.
    - 통신 방식 : TCP와 UDP 중의 한가지를 선택합니다.
    - 포트 번호 : 포트 번호를 입력합니다. 기본값은 8051 입니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/#블록-추가)를 참고해 주세요

6. Block 설정
    디바이스 속성을 저장하면 Block 설정을 할 수 있습니다.
    
    ![block_att]({{ site.url }}/docs/drivers/KEYENCE/Ethernet/block-att-2.png)

    - 블록 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - Block 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다. 디바이스 별 어드레스는 하단의 “사용 가능한 디바이스”를 참고하시기 바랍니다.

    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.
    - Block 크기 : 해당 디바이스 별 읽고자하는 갯수
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.

7.  입출력 주소 
    태그 입력을 위한 입출력 주소는 하단의 “사용 가능한 디바이스”를 참고하시기 바랍니다.   
    태그 입출력 주소 입력시 디바이스 영역은 대문자를 입력하여 주십시오. (ex : R, CR, DM 등)


## 사용가능한 디바이스

InfoU에서 사용 가능한 디바이스 아래와 같습니다.    


### KV-700 시리즈 디바이스

| 영역   | 설명                                          | 비트              | 워드                | 비고    | 읽기개수   |
    |------|---------------------------------------------|-----------------|-------------------|-------|--------|
    | R    | Relay                                       | R00000 ~ R59915 | R000 ~ R599       |       | 1~408  |
    | CR   | Control Relay                               | CR0000 ~ CR3915 | CR00 ~ CR39       |       | 1~408  |
    | DM   | Data Memory                                 | -               | DM00000 ~ DM39999 | *3    | 1~408  |
    | TM   | Temporary Data Memory                       | -               | TM000 ~ TM511     | *3    | 1~408  |
    | T    | Timer Contact                               | T000 ~ T511     | -                 | *3    | 1      |
    | TC   | Timer Current Value                         | -               | TC000 ~ TC511     | *3    | 1~120  |
    | TS   | Timer Setting Value                         | -               | TS000 ~ TS511     | *3    | 1~120  |
    | C    | Count Contact                               | C000 ~ C511     | -                 | *2    | 1      |
    | CC   | Count Current Value                         | -               | CC000 ~ CC511     | *3    | 1~120  |
    | CS   | Count Setting Value                         | -               | CS000 ~ CS511     | *3    | 1~120  |
    | CTH  | High-speed Counter Current Value            | -               | CTH0 ~ CTH1       | *3    | 1~2    |
    | CTC  | High-speed Counter Comparator Contact       | CTC0 ~ CTC3     | -                 | *1 *2 | 1      |
    | CTCS | High-speed Counter Comparator Setting Value | -               | CTCS0 ~ CTCS3     | *3    | 1~4    |
    | TRM  | Digital Trimmer                             | -               | TRM0 ~ TRM7       | *1 *3 | 1~8    |
    | CM   | Control Memory                              | -               | CM0000 ~ CM3999   | *4    | 1~408  |


*1 읽기 전용
    *2 비트 전용
    *3 워드 전용

### KV-1000 시리즈 디바이스

| 영역   | 설명                                          | 비트              | 워드                | 비고   | 읽기개수   |
    |------|---------------------------------------------|-----------------|-------------------|------|--------|
    | R    | Relay                                       | R00000 ~ R59915 | R000 ~ R599       |      | 1~408  |
    | CR   | Control Relay                               | CR0000 ~ CR3915 | CR00 ~ CR39       |      | 1~408  |
    | DM   | Data Memory                                 | -               | DM00000 ~ DM65534 | *3   | 1~408  |
    | TM   | Temporary Data Memory                       | -               | TM000 ~ TM511     | *3   | 1~408  |
    | T    | Timer Contact                               | T0000 ~ T3999   | -                 | *2   | 1      |
    | TC   | Timer Current Value                         | -               | TC0000 ~ TC3999   | *4   | 1~120  |
    | TS   | Timer Setting Value                         | -               | TS0000 ~ TS3999   | *4   | 1~120  |
    | C    | Count Contact                               | C0000 ~ C3999   | -                 | *2   | 1      |
    | CC   | Count Current Value                         | -               | CC0000 ~ CC3999   | *4   | 1~120  |
    | CS   | Count Setting Value                         | -               | CS0000 ~ CS3999   | *4   | 1~120  |
    | CTH  | High-speed Counter Current Value            | -               | CTH0 ~ CTH1       | *4   | 1~2    |
    | CTC  | High-speed Counter Comparator Contact       | CTC0 ~ CTC3     | -                 | *1*2 | 1      |
    | CTCS | High-speed Counter Comparator Setting Value | -               | CTCS0 ~ CTCS3     | *4   | 1~4    |
    | TRM  | Digital Trimmer                             | -               | TRM0 ~ TRM7       | *1*4 | 1~8    |
    | CM   | Control Memory                              | -               | CM0000 ~ CM5999   | *3   | 1~408  |
    | MR   | Internal Auxiliary Relay                    | MR000 ~ MR999   | MR00000 ~ MR99915 |      | 1~408  |
    | LR   | Latch Relay                                 | LR000 ~ LR999   | LR00000 ~ LR99915 |      | 1~408  |
    | EM   | Extension Data Memory                       | -               | EM00000 ~ EM65534 | *3   | 1~408  |
    | FM   | File Register                               | -               | FM00000 ~ FM32766 | *3   | 1~408  |
    | Z | Index Register | - | Z01 ~ Z12 | *4 | 1~12  |

*1 읽기 전용
    *2 비트 전용
    *3 워드 전용
    *4 32비트 디바이스

### KV-3000/5000/5500 시리즈 디바이스

| 영역   | 설명                                          | 비트                | 워드                | 비고   | 읽기개수   |
    |:-------|:--------------------------------------------|:---------------------|:-------------------|:--------|:--------|
    | R    | Relay                                       | R00000 ~ R99915   | R000 ~ R999       |      | 1~408  |
    | CR   | Control Relay                               | CR0000 ~ CR3915   | CR00 ~ CR39       |      | 1~408  |
    | DM   | Data Memory                                 | -                 | DM00000 ~ DM65534 | *3   | 1~408  |
    | TM   | Temporary Data Memory                       | -                 | TM000 ~ TM511     | *3   | 1~408  |
    | T    | Timer Contact                               | T0000 ~ T3999     | -                 | *2   | 1      |
    | TC   | Timer Current Value                         | -                 | TC0000 ~ TC3999   | *5   | 1~120  |
    | TS   | Timer Setting Value                         | -                 | TS0000 ~ TS3999   | *5   | 1~120  |
    | C    | Count Contact                               | C0000 ~ C3999     | -                 | *2   | 1      |
    | CC   | Count Current Value                         | -                 | CC0000 ~ CC3999   | *5   | 1~120  |
    | CS   | Count Setting Value                         | -                 | CS0000 ~ CS3999   | *5   | 1~120  |
    | CTH  | High-speed Counter Current Value            | -                 | CTH0 ~ CTH1       | *5   | 1~2    |
    | CTC  | High-speed Counter Comparator Contact       | CTC0 ~ 3          | -                 | *1*2 | 1      |
    | CTCS | High-speed Counter Comparator Setting Value | -                 | CTCS0 ~ CTCS3     | *5   | 1~4    |
    | TRM  | Digital Trimmer                             | -                 | TRM0 ~ TRM7       | *1*5 | 1~8    |
    | CM   | Control Memory                              | -                 | CM0000 ~ CM5999   | *3   | 1~408  |
    | MR   | Internal Auxiliary Relay                    | MR00000 ~ MR99915 | MR000 ~ MR999     |      | 1~408  |
    | LR   | Latch Relay                                 | LR00000 ~ LR99915 | LR000 ~ LR999     |      | 1~408  |
    | EM | Extension Data Memory | -               | EM00000 ~ EM65534  | *3   | 1~408  |
    | FM | File Register         | -               | FM00000 ~ FM32766  | *3   | 1~408  |
    | Z  | Index Register        | -               | Z01 ~ Z12          | *5   | 1~12   |
    | B  | Link Relay            | B0000 ~ B3FFF   | B000 ~ B3FF        | *4   | 1~408  |
    | VB | Work Relay            | VB0000 ~ VB3FFF | VB000 ~ VB3FF      | *4   | 1~408  |
    | ZF | File Register (SQ)    | -               | ZF00000 ~ ZF131071 | *3   | 1~408  |
    | W  | Link Register         | -               | W0000 ~ W3FFF      | *3*4 | 1~408  |
    | VM | Work Memory           | -               | VM00000 ~ VM59999  | *3   | 1~408  |

*1 읽기 전용
    *2 비트 전용
    *3 워드 전용
    *4 16진수 표기
    *5 32비트 디바이스

{:.note}
> - 디바이스에 대한 자세한 내용은 KEYENCE 사용설명서를 참조 하십시오. 
> - 디바이스 영역 범위를 벗어나지 않도록 사용하여 주십시오.
> - 디바이스 영역 내에서 쓰기 할 수 없는 영역이 있을 수 있습니다.
> - 태그 입출력 주소 입력시 디바이스 영역은 대문자를 입력하여 주십시오. (ex : R, CR, DM 등)
> - CPU모듈에 따라 디바이스 범위 차이가 있을 수 있습니다. 각 CPU모듈 사용설명서를 참조 바랍니다.
> - C, T, CTC 디바이스는 KV Studio에서 프로그램에 사용되어야만 모니터 가능합니다. 사용되지 않은 디바이스를 모니터 하는 경우 에러 발생합니다.
> - CC, CS, TC, TS, CTCS 디바이스는 KV Studio에서 프로그램에 사용되지 않아도 모니터 가능하지만 사용되지 않은 디바이스 쓰기 시 에러 발생합니다.
> - CTC 디바이스는 디바이스 쓰기 시 0 (Off)의 값만 쓰기 할 수 있습니다. 1(On)의 값 쓰기 시 에러가 발생합니다.




















