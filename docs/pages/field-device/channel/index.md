---
layout: default
grand_parent: Pages
parent: 필드 디바이스
title: 채널
nav_order: 1
---

{: .no_toc }
# 채널
DataWorX는 물리적인 디바이스와 통신하기 위해서 프로그램에서 사용하기 위한 드라이버 및 통신에 대한 각종 설정을 채널이라는 단위로 관리합니다. 
채널 관리를 위한, 채널리스트 이동 방법은 다음과 같습니다.

1. 왼쪽 Naviagation Tree에서 `FIELD DEVICES`을 누릅니다.
2. Field Deivce 내에서 이동은, Bradcrumbs의 `FIELD DEVICES`를 클릭하면, 채널목록으로 이동됩니다.

![CHANNEL_LIST]({{ site.url }}/docs/pages/field-device/channel/channellist-1.png)

- TOC
{:toc}



## 채널 추가  

1. Field Device 트리에서 Field Device를 클릭 후, 추가 버튼을 누르면 추가할 채널의 드라이버를 추가하는 패널이 열립니다.

    ![CHANNEL_ADD]({{ site.url }}/docs/pages/field-device/channel/channel-add-1.png)

2. 원하는 채널 드라이버를 선택합니다.

    ![CHANNEL_DRIVER]({{ site.url }}/docs/pages/field-device/channel/channel-driver-1.png)

2. 채널 유형별 채널의 Basic(기본정보)/Detail(상세정보)를 입력하는 채널 속성 화면이 열립니다.

    ![CHANNEL_INPUT]({{ site.url }}/docs/pages/field-device/channel/channel-input-1.png)

3. 채널명과 필요한 데이터를 입력하고 저장 버튼을 눌러 채널을 추가합니다.

## 채널 수정

1. 채널 수정화면을 열어 수정을 시작합니다. 채널 수정을 여는방법은 3가지가 있습니다.

    1. 테이블 상단의 Toolbar 위치의 Toggle 버튼을 이용할 수 있습니다.

        ![CHANNEL_TOGGLE]({{ site.url }}/docs/pages/field-device/channel/channeledit-toggle-2.png)

        1. Toggle 버튼을 `Edit`로 변경  

        2. 테이블 채널명에 마우스를 올리면 나오는 `OPEN 버튼을 누릅니다.

    2. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `채널 수정`을 누릅니다.

        ![CHANNEL_MORE]({{ site.url }}/docs/pages/field-device/channel/channeledit-more-2.png)

    3. Field Device Tree의 채널명 오른편의 `더보기` > `채널 수정`을 이용할 수 있습니다.

        ![CHANNEL_TREE]({{ site.url }}/docs/pages/field-device/channel/channeledit-tree-2.png)

2. 채널의 Basic(기본정보)/Detail(상세정보)를 수정 후, 확인 버튼을 눌러 수정 내용을 저장합니다.

    ![CHANNEL_EDIT_SAVE]({{ site.url }}/docs/pages/field-device/channel/channeledit-save-2.png)

## 채널 정보

1. 채널 정보화면을 열어 채널 정보를 확인할 수 있습니다. 채널 정보를 여는방법은 3가지가 있습니다.
    1. 테이블 상단의 Toolbar 위치의 Toggle 버튼을 이용할 수 있습니다.

        ![CHANNEL_TOGGLE]({{ site.url }}/docs/pages/field-device/channel/channelinfo-toggle-3.png)

        1. Toggle 버튼을 `Lock`으로 변경  

        2. 테이블 채널명에 마우스를 올리면 나오는 `OPEN 버튼`을 누릅니다.

    2. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `채널 정보`를 누릅니다.

        ![CHANNEL_MORE]({{ site.url }}/docs/pages/field-device/channel/channelinfo-more-3.png)

    3. Field Device Tree의 채널명 오른편의 `더보기` > `채널 정보`를 이용할 수 있습니다.

        ![CHANNEL_TREE]({{ site.url }}/docs/pages/field-device/channel/channelinfo-tree-3.png)

2. 채널의 Basic(기본정보)/Detail(상세정보)를 확인할 수 있습니다.

    ![CHANNEL_DETAIL]({{ site.url }}/docs/pages/field-device/channel/channelinfo-deatail-3.png)

## 채널 삭제

1. 채널 삭제 버튼을 클릭하여, 채널을 삭제할 수 있습니다. 채널 삭제 방법은 3가지가 있습니다.

    1. 테이블 행 맨 오른쪽의, 더보기 버튼을 클릭하여 `채널 삭제`를 누릅니다.

        ![CHANNEL_MORE]({{ site.url }}/docs/pages/field-device/channel/channeldelete-more-4.png)

    2. Field Device Tree의 채널명 오른편의 `더보기` > `채널 삭제`을 이용할 수 있습니다.

        ![CHANNEL_TREE]({{ site.url }}/docs/pages/field-device/channel/channeldelete-tree-4.png)

    3. 다중삭제의 경우 테이블 리스트를 복수개 선택하여 사용 가능합니다.

        ![CHANNEL_TOGGLE]({{ site.url }}/docs/pages/field-device/channel/channeldelete-list-4.png)

        1. 테이블 행을 클릭하여 다중 선택을 합니다.

            {: .highlight }
            `CTRL + A`로 전체 선택을 사용할 수 있습니다.  
            `SHIFT + Click`으로 여러개를 선택할 수 있습니다.  
            `CTRL + Click`으로 다중선택할 수 있습니다.  

        2. 테이블 상단에 나오는 `삭제 버튼`을 누릅니다.

2. Delete Channels 모달의 확인버튼을 클릭하면, 삭제가 완료됩니다.

    ![CHANNEL_MODAL]({{ site.url }}/docs/pages/field-device/channel/channeldelete-confirm-4.png)
