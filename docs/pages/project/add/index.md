---
layout: default
grand_parent: Pages
parent: 프로젝트
title: 프로젝트 추가
nav_order: 2
---

{: .no_toc }
# 프로젝트 추가
DataWorX에서 사용할 프로젝트를 생성할 수 있습니다. 프로젝트 목록 페이지에서 버튼을 통해 해당 페이지로 이동할 수 있습니다.

- TOC
{:toc}

![New Project]({{ site.url }}/docs/pages/project/add/project-new.png)

![Project - Add]({{ site.url }}/docs/pages/project/add/project-add.png)

## 프로젝트 속성
- 프로젝트 명: 공백 또는 숫자로 시작할 수 없으며, 길이는 25 Byte로 제한됩니다. 특수문자는 `-`, `_`만 허용됩니다.
- 생성자: 현재 로그인한 사용자의 아이디가 자동으로 표시되며 변경할 수 없습니다.
- 경로: 경로 설정 페이지에서 경로를 추가할 수 있습니다. 자세한 내용은 [프로젝트 경로 페이지]({{ site.url }}/docs/pages/project/path/)를 참고하시기 바랍니다.

| 구분        | 속성               | 설명  |
| :---------- | :---------------- | :---- |
| 기본정보     | 프로젝트 명        | 프로젝트 이름 |
|              | 설명              | 프로젝트에 대한 설명 |
|              | 생성자            | 프로젝트를 생성한 사용자 아이디 |
| 세부정보     | 패키지 명          | 프로젝트 패키지 이름 |
|              | 경로              | 프로젝트가 저장될 경로 |
|              | 기본 IP 주소       | 기본 IP 주소 |
|              | 회선 이중화        | 프로젝트 회선 이중화 설정 |
|              | 예비 IP 주소       | 시스템 이중화 시 예비 IP 주소 |
| 비밀번호 설정 | 비밀번호 사용      | [프로젝트 비밀번호 설정](#비밀번호-설정) |
| 시스템 이중화 | 시스템 이중화 사용  | 🚧 지원 예정 🚧 |
| 실행모듈      | Data Process      | 실시간 데이터를 처리하는 모듈 |
|              | IO Manager        | 장비데이터를 수집하는 모듈 |
|              | Tag Historian     | 태그이력 데이터를 저장하는 모듈 |
|              | Alarm Manager     | 알람데이터를 관리 및 저장하는 모듈 |


### 비밀번호 설정
1. 비밀번호 설정 카드에서 비밀번호 사용 토글을 킵니다.
2. 카드 하단의 `비밀번호 설정` 텍스트 버튼을 클릭합니다.
3. 비밀번호 설정 모달에 원하는 비밀번호를 설정합니다.
4. 비밀번호가 설정되었다면 카드 하단의 텍스트 버튼의 체크표시가 파랑색으로 변경됩니다.

![Project - Password]({{ site.url }}/docs/pages/project/add/project-password.png)
![Project - Password Modal]({{ site.url }}/docs/pages/project/add/project-password-modal.png)
![Project - Password Set]({{ site.url }}/docs/pages/project/add/project-password-set.png)


## 프로젝트 파일
프로젝트가 생성되면 `[프로젝트 경로]/[프로젝트 명]`에 프로젝트를 위한 파일들이 생성됩니다.

### 생성 폴더

| 폴더        | 설명 |
| :---------- | :-- |
| Config      | 각종 설정 파일 |
| Database    | 프로젝트 엔지니어링 데이터베이스 |
| History     | 이력 데이터 |
| Log         | 로그 데이터 |
| LogicFlow   | LogicFlow 모듈 및 데이터 |

### 생성 파일
프로젝트 파일은 `[프로젝트명].lspx`으로 생성됩니다. 파일은 `JSON` 형식을 따릅니다.

```json
{
  "changeTime": "2024/04/03 17:33:50",
  "optLineRedundancy": false,
  "ipAddress1": "127.0.0.1",
  "ipAddress2": "",
  "type": 0,
  "version": "0.0.1",
  "redundancy": {
    "optSystemRedundancy": false,
    "isSerialMonitor": false,
    "serialPort": "",
    "isDeviceFailTransfer": false,
    "transferDelay": 60,
    "master": {
      "ipAddress1": "",
      "ipAddress2": "",
      "name": "",
      "path": ""
    },
    "standby": {
      "ipAddress1": "",
      "ipAddress2": "",
      "name": "",
      "path": ""
    },
    "isMaster": false
  },
  "package": "Standard",
  "name": "Demo",
  "path": null,
  "description": "",
  "creator": "admin",
  "optPassword": false,
  "password": "",
  "createTime": "2023/03/21 13:56:43",
  "DataProcess": true,
  "IOManager": true,
  "TagHistorian": true,
  "AlarmManager": true
}
```