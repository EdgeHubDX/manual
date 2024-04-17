---
layout: default
parent: Pages
title: 사용자 관리
nav_order: 4
---

{: .no_toc }
# 사용자 관리
DataWorX 사용자 관리를 위한 페이지입니다. 애플리케이션 바를 통해 해당 페이지로 이동할 수 있습니다.

{: .note }
해당 페이지는 관리자 권한만 사용 가능합니다.

![Member - Item]({{ site.url }}/docs/pages/member/member-item.png)

- TOC
{:toc}


## 사용자 목록
현재 DataWorX에 추가된 사용자 목록을 확인할 수 있습니다.

![Member]({{ site.url }}/docs/pages/member/member.png)


## 사용자 추가
- 사용자 목록 카드의 우측 상단의 `+` 버튼을 클릭하면 사용자 추가 페이지로 이동합니다.
- 사용자 아이디: 영문, 숫자, 특수문자 `-`, `_`를 사용하여  3 - 30자로 설정할 수 있습니다.
- 사용자 명: 영문, 한글을 사용하여 3 - 30자로 입력할 수 있습니다. 

| 권한     | 설명         |
| :------- | :---------- |
| Admin    | 사용자 관리, 프로젝트 엔지니어링, 런타임 전환, 제어 등 모든 권한이 주어집니다. |
| Engineer | Admin 권한에서 사용자 관리, 라이선스 관리를 제외한 모든 권한이 주어집니다. |
| Operator | 프로젝트를 감시할 수 있습니다. |

![Member - Add]({{ site.url }}/docs/pages/member/member-add.png)


## 사용자 정보 수정
사용자 목록의 메뉴 버튼을 클릭하면 수정 페이지로 이동할 수 있습니다. 

![Member - Edit Item]({{ site.url }}/docs/pages/member/member-edit-item.png)

{: .note }
아이디는 변경할 수 없습니다.

![Member - Edit]({{ site.url }}/docs/pages/member/member-edit.png)


## 비밀번호 설정
사용자 정보 카드 하단 우측에 `비밀번호 설정` 버튼을 클릭한 후 오픈된 비밀번호 설정 모달을 통해 비밀번호를 수정할 수 있습니다. 

![Member - Password]({{ site.url }}/docs/pages/member/member-password.png)


## 사용자 삭제
사용자 목록의 메뉴 버튼을 클릭하면 사용자를 삭제할 수 있습니다. 

![Member - Delete]({{ site.url }}/docs/pages/member/member-delete.png)

{: .note }
최초 관리자 `admin`은 삭제할 수 없습니다.

![Member - Multi Delete]({{ site.url }}/docs/pages/member/member-multi-delete.png)

{: .highlight}
`Ctrl`키와 `Shift`키를 이용해 사용자를 다중 선택하여 삭제할 수 있습니다.

