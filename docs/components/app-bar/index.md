---
layout: default
parent: Components
title: 애플리케이션 바
nav_order: 1
---

{: .no_toc }
# 애플리케이션 바
DataWorX의 전역적인 설정, 현재 시각 확인, 프로젝트 관련 설정을 수행할 수 있는 컴포넌트 입니다. 

- TOC
{:toc}

![App Bar]({{ site.url }}/docs/components/app-bar/app-bar.png)

## BI 이미지
- 클릭 시 프로젝트 목록 페이지로 이동할 수 있습니다.

![BI]({{ site.url }}/docs/components/app-bar/bi.png)


## 프로젝트 바
- 프로젝트 오픈 시 프로젝트 설정을 위한 아이템이 표시됩니다. 자세한 내용은 [프로젝트 바 페이지]({{ site.url }}/docs/components/project-bar/)를 참고하시기 바랍니다.

![Project Bar]({{ site.url }}/docs/components/app-bar/project-bar.png)

## 현재 시각
- 현재 시각을 표시합니다.

![Current Time]({{ site.url }}/docs/components/app-bar/current-time.png)

## 사용자 메뉴
- 현재 로그인한 사용자의 아이디를 표시합니다. 
- 클릭 시 다음과 같은 메뉴가 표시됩니다.
  - 프로필: 사용자의 정보를 수정하는 페이지로 이동할 수 있습니다.
  - 로그아웃: 현재 로그인한 사용자의 세션을 종료할 수 있습니다.

![User Items]({{ site.url }}/docs/components/app-bar/user-items.png)

## 설정 메뉴
- 클릭 시 다음과 같은 메뉴가 표시됩니다.
  - 라이선스 관리: 관리자 권한의 사용자에게 표시됩니다. 라이선스 관리 페이지로 이동할 수 있습니다.
  - 사용자 관리: 관리자 권한의 사용자에게 표시됩니다. 사용자 관리 페이지로 이동할 수 있습니다.
  - 테마 설정: 사용자의 선호에 따라 애플리케이션의 테마를 `Light` 또는 `Dark`로 설정할 수 있습니다.
  <!-- - 언어 설정: 사용자의 선호에 따라 애플리케이션에서 사용되는 언어를 설정할 수 있습니다. -->

![Setting Items]({{ site.url }}/docs/components/app-bar/setting-items.png)

## 도움 메뉴
- 클릭 시 다음과 같은 메뉴가 표시됩니다.
  - I/O 드라이버 목록: I/O 드라이버 목록 페이지로 이동할 수 있습니다.
  - 시스템 정보: 시스템 정보 페이지로 이동할 수 있습니다.
  - About: 어바웃 페이지로 이동할 수 있습니다.

![Help Items]({{ site.url }}/docs/components/app-bar/help-items.png)