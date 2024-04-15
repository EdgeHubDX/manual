---
layout: default
grand_parent: Pages
parent: 필드 디바이스
title: 디바이스
nav_order: 2
---

{: .no_toc }
# 디바이스
디바이스는 DataWorX에 물리적으로 연결된 하위 필드 디바이스를 의미합니다.
디바이스는 PLC, Inverter, 전력량계 등의 단위 기기일 수도 있으며, 다른 시스템 및 서버 등 데이터를 수집하는 모든 대상을 DataWorX 입장에서는 디바이스로 관리합니다.
디바이스 관리를 위한, 디바이스리스트 이동 방법은 다음과 같습니다.

1. 왼쪽 Naviagation Tree에서 `FIELD DEVICES`을 누릅니다.
2. 왼쪽 Sub Navigation Tree에서 원하는 `채널명'을 누릅니다.
3. Field Deivce 내에서 이동은, Bradcrumbs의 `채널명`을 클릭하면, 해당 채널의 디바이스 목록으로 이동됩니다.

![DEVICE_LIST]({{ site.url }}/docs/pages/field-device/device/devicelist-1.png)

- TOC
{:toc}


## 디바이스 추가

1. 디바이스 추가 버튼을 클릭하여, 디바이스를 추가할 수 있습니다. 추가 방법은 2가지가 있습니다.

    1. 디바이스 리스트 테이블 상단의 디바이스 추가버튼을 클릭합니다.

    2. 왼쪽트리의 채널명 더보기에서 디바이스를 추가합니다.

    ![DEVICE_ADD]({{ site.url }}/docs/pages/field-device/device/deviceadd-1.png)

2. 디바이스명과 필요한 데이터를 입력하고 확인 버튼을 눌러 디바이스를 추가합니다.

    ![DEVICE_ADD_DETAIL]({{ site.url }}/docs/pages/field-device/device/deviceadd-detail-1.png)

    {: .note }
    Enable 토글을 OFF한 경우에는, 디바이스가 수집을 하지 않습니다.


## 디바이스 수정

1. 디바이스 수정 버튼을 클릭하여, 디바이스를 수정할 수 있습니다. 수정 방법은 3가지가 있습니다.

    1. 테이블 상단의 Toolbar 위치의 Toggle 버튼을 이용할 수 있습니다.

        ![DEVICE_TOGGLE]({{ site.url }}/docs/pages/field-device/device/deviceedit-toggle-2.png)

        1. Toggle 버튼을 `Edit`으로 변경  

        2. 테이블 디바이스명에 마우스를 올리면 나오는 `OPEN 버튼`을 누릅니다.

    2. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `디바이스 수정`을 누릅니다.

        ![DEVICE_MORE]({{ site.url }}/docs/pages/field-device/device/deviceedit-more-2.png)

    3. Field Device Tree의 디바이스명 오른편의 `더보기` > `디바이스 수정`을 이용할 수 있습니다.

        ![DEVICE_TREE]({{ site.url }}/docs/pages/field-device/device/deviceedit-tree-2.png)

2. 디바이스의 Basic(기본정보)/Detail(상세정보)를 수정 후, 확인 버튼을 눌러 수정 내용을 저장합니다.

    ![DEVICE_EDIT_DETAIL]({{ site.url }}/docs/pages/field-device/device/deviceedit-detail-2.png)

## 디바이스 정보

1. 디바이스 정보화면을 열어 디바이스 정보를 확인할 수 있습니다. 디바이스 정보를 여는방법은 3가지가 있습니다.
    1. 테이블 상단의 Toolbar 위치의 Toggle 버튼을 이용할 수 있습니다.

        ![DEVICE_TOGGLE]({{ site.url }}/docs/pages/field-device/device/deviceinfo-toggle-3.png)

        1. Toggle 버튼을 `Lock`으로 변경  

        2. 테이블 디바이스명에 마우스를 올리면 나오는 `OPEN 버튼`을 누릅니다.

    2. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `디바이스 정보`를 누릅니다.

        ![DEVICE_MORE]({{ site.url }}/docs/pages/field-device/device/deviceinfo-more-3.png)

    3. Field Device Tree의 디바이스명 오른편의 `더보기` > `디바이스 정보`를 이용할 수 있습니다.

        ![DEVICE_TREE]({{ site.url }}/docs/pages/field-device/device/deviceinfo-tree-3.png)

2. 디바이스의 Basic(기본정보)/Detail(상세정보)를 확인할 수 있습니다.

    ![DEVICE_DETAIL]({{ site.url }}/docs/pages/field-device/device/deviceinfo-detail-3.png)

## 디바이스 삭제

1. 디바이스 삭제 버튼을 클릭하여, 디바이스를 삭제할 수 있습니다. 삭제 방법은 3가지가 있습니다.

    1. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `디바이스 삭제`를 누릅니다.

        ![DEVICE_MORE]({{ site.url }}/docs/pages/field-device/device/devicedelete-more-4.png)

    2. Field Device Tree의 디바이스명 오른편의 `더보기` > `디바이스 삭제`을 이용할 수 있습니다.

        ![DEVICE_TREE]({{ site.url }}/docs/pages/field-device/device/devicedelete-tree-4.png)

    3. 다중삭제의 경우 테이블 리스트를 복수개 선택하여 사용 가능합니다.

        ![DEVICE_LIST]({{ site.url }}/docs/pages/field-device/device/devicedelete-list-4.png)

        1. 테이블 행을 클릭하여 다중 선택을 합니다.

            {: .highlight }
            `CTRL + A`로 전체 선택을 사용할 수 있습니다.  
            `SHIFT + Click`으로 여러개를 선택할 수 있습니다.  
            `CTRL + Click`으로 다중선택할 수 있습니다.  

        2. 테이블 상단에 나오는 `삭제 버튼`을 누릅니다.

2. Delete Devices 모달의 확인버튼을 클릭하면, 삭제가 완료됩니다.

    ![DEVICE_MODAL]({{ site.url }}/docs/pages/field-device/device/devicedelete-detail-4.png)
