---
layout: default
grand_parent: Drivers
parent: Panasonic
title: Nais Serial
nav_order: 1
---

{: .no_toc }
# Panasonic: Nais(FP 시리즈) Serial
- TOC
{:toc}

## 통신 드라이버 설정
### EdgeHub 설정
1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/index.html/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “OmronE”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/Panasonic/Nais-Serial/channel-add-1.png)

2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/Panasonic/Nais-Serial/channel-att-1.png)

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

    ![device_att]({{ site.url }}/docs/drivers/Panasonic/Nais-Serial/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - 디바이스 설명 : 디바이스 설명을 입력합니다.
    - PLC CPU 종류 : PLC CPU 종류를 선택합니다.
    - Station 번호 : PLC Cnet 모듈의 국번을 입력합니다.
    - 저장 : 저장하면 메인 화면의 디바이스 트리에 디바이스가 추가됩니다. 메인 화면의 태그 리스트에는 디바이스 관련 시스템 태그들이 자동으로 추가 됩니다.

5. Block 추가
    자세한 사용법은 [블록 페이지]({{ site.url }}/docs/pages/field-device/block/index.html/#블록-추가)를 참고해 주세요

6. Block 속성 설정
    ![block-att]({{ site.url }}/docs/drivers/Panasonic/Nais-Serial/block-att-1.png) 

    - “등록 정보” 트리에서 [새 블록]을 선택합니다.
    - Block 번호 : Block의 고유 번호 입니다. 각각의 Block은 서로 다른 Block 번호를 지정해 주어야 합니다.
    - 설명 : Block 설명을 입력합니다.
    - 시작 Address : Block의 시작 Address를 입력합니다.
        -. X,Y,R,DT,SV,EV,IX,IY 는 WORD단위 읽기를 사용한다.   
        예1) X,Y,R은 Bit단위 메모리이지만 WORD단위 읽기를 사용한다. X입력은 208점으로 X0~X12F까지 사용한다. 시작Address : X1, Block 크기 : 5한다면, X10~X5F의 데이터를 가져온다.   
        예2) EV,SV는 WORD단위 메모리이다. 따라서 WORD단위 읽기를 사용한다.   
        시작Address : EV0, Block 크기 : 20으로 한다면, EV0~EV19의 데이터를 가져온다.   
        예3) IX,IY는 WORD단위 메모리이지만 크기는 1WORD씩 즉, IX0, IY0만 존재한다.   
        시작Address : IX0, Block 크기 : 1으로 설정한다. IY도 마찬가지 이다.   
        예4) DT는 WORD단위 메모리이지만 범위는 DT9000~DT9111만 존재한다.   
        시작Address : DT9000, Block 크기 : 10으로 설정한다면, DT9000~DT9009의 데이터를 가져온다.   

        -. R9000 이상 ,T,C는 Bit단위 읽기를 사용한다. 시작 Address는 Bit단위이며, Block 크기는 1~8개만 가진다.   
        예1) 시작Address : T0, Block 크기 : 8한다면, T0~T7의 데이터를 가져온다.   
        예2) 시작Address : R9000, Block 크기 : 8한다면, R9000~R9007의 데이터를 가져온다.   

    - 통신 주기 : 해당 Block의 데이터 수집 주기를 msec 단위로 입력합니다.   
    - Block 크기 : 해당 구별자별 읽고자하는 갯수   
    - 저장 : 저장 버튼을 누르면, 설정된 Block 정보가 저장이 되고, 상단의 블록 리스트에 추가 됩니다.   
    - 삭제 : 삭제 버튼을 누르면, 현재 선택된 Blcok이 삭제됩니다.   


7. 입출력 주소
- 형식
- 아날로그 입력Address 사용예제
    DT100 	: DT영역의 100번째 Word값을 가져온다.
    SV10 	: 타이머 영역의 T10의 설정치값을 가져온다
    SV111	: 카운터 영역의 C111의 설정치값을 가져온다
- 디지털 입력Address 사용예제
    X10F	: X영역의 10*16+Fh(15)=160+15=175번째 접점의 값을 가져온다.
    R501	: 내부릴레이 R영역의 50*16+1h(1)=800+1=801번째 접점의 값을 가져온다.
    R9001	: 특수내부릴레이 R9001의 접점의 값을 가져온다.
    DT1280F	: 데이터레지스터 1280워드의 F(15)번째의 Bit값을 가져온다.

    | 메모리코드 | 특성             | 데이터형식 | C10/C14/C16 CPU 메모리번지  | C32/SL1 CPU 메모리번지             | 어드레스 적용예제      |
    |-------|----------------|-------|-------------------------------------------------------------------------------|-------------------------------|------------------------|
    | X     | 외부입력           | BIT   | 208점(X0~X12F)               |                               | DI : Xxxxx0~F(xxxx는 0~12의 십진수)   X12A                                          |
    | Y     | 외부출력           | BIT   | 208점(Y0~Y12F) 1008점(R0~X62F)       특수내부릴레이 64점(R9000~R9063)    |                  | DI : Yxxxx0~F(xxxx는 0~12의 십진수)   Y0F                                         |
    | R     | 내부릴레이          | BIT   | 208점(Y0~Y12F) 1008점(R0~X62F)      특수내부릴레이 64점(R9000~R9063) |              | DI : Rxxxx0~F(xxxx는 0~62의 십진수)   R19F (특수) DI : Rxxxx (xxxx는 9000~9063의 십진수) R9010  |
    | T     | 타이머            | BIT   | T0~T99       |                               | DI : Txxxx (xxxx는 0~99의 십진수)   T90                                                                                  |
    | C     | 카운터            | BIT   | C100~C143             |                 | DI : Cxxxx( xxxx는 100~143의 십진수), C108                       |
    | DT    | 데이터레지스터    | WORD  | 1660워드 (DT0~DT1659) | 6144워드 (DT0~DT6143)| AI : DTxxxx ( xxxx는 0~1659 or 0~6143의 십진수) DT1000    DI : DTxxxx0~F ( xxxx는 0~1659 or 0~6143의 십진수), DT1   |
    | SV    | 타이머/카운터경과치 영역  | WORD  | 144워드(SV0~SV143) 타이머 : 0~99, 카운터 : 100~143|          | AI : SVxxxx ( xxxx는 0~143 ) SV1 or SV100  |
    | EV    | 타이머/카운터 경과치 영역 | WORD  | 144워드(EV0~EV143) 타이머 : 0~99, 카운터 : 100~143|         | AI : EVxxxx ( xxxx는 0~143 ) EV40 or EV129  |
    | IX    | 인덱스레지스터        | WORD  | 1워드 ( IX0 )       |             | AI : IX0 (단지 1개워드) DI : IX_0(0~F)    IX0F    |
    | IY    | 인덱스레지스터        | WORD  | 1워드 ( IY0 )       |              | AI : IY0 (단지 1개워드) DI : IY_0(0~F)    IY01    | 

                                                        
                                                           

                                                                         


