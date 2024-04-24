---
layout: default
grand_parent: Pages
parent: 보고서
title: 보고서 제약사항
nav_order: 5
---

# 보고서 제약사항  
보고서 제약사항은 다음과 같습니다.  

1. 엑셀보고서에서 Sheet 1개에 추가할 수 있는 **최대 Tag 수**는 **100개**입니다.  
2. 엑셀 보고서의 Form 파일의 **개인 정보 옵션**에서 **저장 시 파일 속성의 개인 정보 제거** 항목이 `체크 해제` 되어있어야 보고서가 정상 동작합니다. 

    ![SECURITY]({{ site.url }}/docs/pages/report/constraint/security-1.png)

3. 년보 사용 관련  
  - 월별 12개 데이터를 표시할 경우 : 수집주기 1달인 수집 모델(통계값, 적산값)
  - 월별 365개 데이터를 표시할 경우 : 수집주기 1일인 로깅 그룹(정주기)







