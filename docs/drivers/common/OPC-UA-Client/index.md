---
layout: default
grand_parent: Drivers
parent: Common
title: OPC UA Client
nav_order: 4
---

{: .no_toc }
# OPC UA Client
- TOC
{:toc}

## 통신 드라이버 설정
### EdgeHub 설정
1. 채널 추가
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/index.html/#채널-추가)를 참고해 주세요

    채널추가 리스트에서 “OmronE”를 선택한 후 “확인” 버튼을 누릅니다.

    ![channel_add]({{ site.url }}/docs/drivers/common/OPC-UA-Client/channel-add-1.png)

2. 채널 속성 설정

    ![channel_att]({{ site.url }}/docs/drivers/common/OPC-UA-Client/channel-att-1.png)

   - 채널 명 : 통신채널 이름을 입력합니다. 
   - 채널 설명 : 통신채널 설명을 입력합니다. 
   - 로컬 IP 주소 #1 : PC의 IP Address를 입력합니다.
   - 로컬 IP 주소 #2 : 라인 이중화를 사용할 경우 사용하게 될 두번째 IP Address를 입력합니다.
   - 통신TimeOut : 장비에서 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다. 통신 오류를 판별하는 근거가 됩니다.
   - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
   - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시됩니다

3. Device 추가
    자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/index.html/#디바이스-추가)를 참고해 주세요

4. Device 속성 설정

    ![device_att]({{ site.url }}/docs/drivers/common/OPC-UA-Client/device-att-1.png)

    - 디바이스 명 : 디바이스 이름을 입력합니다. 
    - URL : 접속할 OPC UA 서버의 URL을 입력합니다.
    - Period(msec) : 데이터를 취득할 주기를 설정합니다.
    - Encryption : 메시지 보안을 위한 옵션을 선택합니다. 선택한 옵션이 접속할 OPC UA 서버에서 지원 가능한지 확인이 필요합니다.
    - Authentication : 접속을 위한 옵션을 선택합니다. 선택한 옵션이 접속할 OPC UA 서버에서 지원 가능한지 확인이 필요합니다.
        - Anonymous : 인증없이 접속을 시도합니다.
        - Usernmae/Password : 사용자 ID, Password를 이용하여 접속합니다.


    {:.note}
    >☞ Usernmae : 4~16자만 허용, 특수문자는 언더바(“_”)만 허용 ex) Edge_User 등등
    >☞ Password : 4~16자만 허용 ex) edge123!@# 등등

    - Certificate/Private Key : 인증서를 이용하여 접속 합니다. 기본값은 기본 인증서로 설정되어 있습니다.

    {:.note}
    >☞ 기본 인증서는 아래의 위치에 있습니다.  
    >
    >|Certificate	|[EdgeHub 설치 폴더]\bin\ IODriver\certificate_infou_opcuaclient.der|
    >|Private Key	|[EdgeHub 설치 폴더]\bin\IODriver\ private_infou_opcuaclient.pem |
    >
    >☞ 인증서를 이용한 통신을 하기 위해서는 아래의 사항을 준수해 주십시오.
    >1. 접속하려는 서버의 인증서가 아래의 위치에 저장되어 있어야 합니다.
    >|서버 인증서 저장 폴더	|[EdgeHub 프로젝트 폴더]\Config\ |
    >
    >2. 클라이언트의 인증서가 접속하려는 서버에서 지정하는 위치에 저장되어 있어야 합니다.(서버 설정 확인 필요)
    >3. 유효한 인증서를 사용하지 않을 경우 서버에서 접속이 거부 될 수 있습니다.

    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

5. 입출력 주소
    - 입출력 주소 형식 : Namespace ID와 Node 정보로 구성되어 있습니다. 
        - Node ID 타입 Numeric : [Name Space ID],[Node ID]
        - Node ID 타입 String 		  : [Nmae Space ID],[Node Name] 혹은 [Nmae Space ID],[“Node Name”]
    - 샘플 :  2,2007 ,  2,Test_A_001

    {:.note}
    >☞ Node ID 타입
    >Node ID 타입은 Numeric 과 String 만 지원 합니다.
    >
    >☞ Data 타입
    >Node의 Data 타입과 EdgeHub Tag 타입이 일치하지 않을 경우 읽기/쓰기가 불가 할 수도 있습니다.
    >지원 가능한 Data Type 은 다음과 같습니다.
    >
    >| OPC UA 데이터 타입 | EdgeHub 장비 데이터 타입    |
    >|---------------|--------------------|
    >| Boolean       | BOOL                 |
    >| SByte         | INT8                 |
    >| Int16         | INT16                |
    >| Int32         | INT32                |
    >| Int64         | INT64                |
    >| Byte          | UINT8                |
    >| UInt16        | UINT16               |
    >| UInt32        | UINT32               |
    >| UInt64        | UINT64               |
    >| Float         | FLOAT                |
    >| Double        | DOUBLE               |
    >| String        | STRING               |

    예제 1) Unified Automation 에서 제공하는 UaExpert를 이용하여 서버의 Item을 검색한 결과가 아래와 같을 때 입출력 주소는 “2,2007”, 장비 데이터 타입은 “UINT16”을 입력한다.

    ![unit16]({{ site.url }}/docs/drivers/common/OPC-UA-Client/unit16-1.png)

    예제 2) Unified Automation 에서 제공하는 UaExpert를 이용하여 서버의 Item을 검색한 결과가 아래와 같을 때 입출력 주소는 “2,Demo.Static.Scalar.Ini16”, 장비 데이터 타입은 “INT16”을 입력한다.

    ![int16]({{ site.url }}/docs/drivers/common/OPC-UA-Client/int16-1.png)


    

