---
layout: default
grand_parent: Drivers
parent: Common
title: BACnetIP
nav_order: 1
---

{: .no_toc }
# BACnetIP 
- TOC
{:toc}

## 1. 통신드라이버 설정
### 1.1 EdgeHub 설정

1. 채널 추가   
    자세한 사용법은 [채널 페이지]({{ site.url }}/docs/pages/field-device/channel/#채널-추가)를 참고해 주세요

    -	채널추가 리스트에서 “BACnetIP”를 선택한 후 “확인” 버튼을 누릅니다. 

      ![CHANNEL_ATT1]({{ site.url }}/docs/drivers/common/BACnet-IP/channel-att-1.png)
2. 채널 속성 설정
 
      ![CHANNEL_ATT2]({{ site.url }}/docs/drivers/common/BACnet-IP/channel-att2-1.png)

    - 채널명 : 통신채널 이름을 입력합니다.
    - 채널 설명 : 통신채널 설명을 입력합니다.
    - 로컬 IP 주소 #1 : PC의 IP Address를 입력합니다.
    - 통신 TimeOut : 장비에게 데이터를 요청한 후 Time Out으로 처리하게 되는 시간을 말합니다.
    - 재시도 횟수 : 통신 실패시 재시도하는 횟수를 설정합니다.
    - 저장 : 저장 버튼을 누르면, 설정된 통신 채널 정보가 저장되고 상단의 채널 리스트에 표시 됩니다.

3. 디바이스 추가
   자세한 사용법은 [디바이스 페이지]({{ site.url }}/docs/pages/field-device/device/#디바이스-추가)를 참고해 주세요

4. 디바이스 속성 설정
   
   ![DEVICE_ATT]({{ site.url }}/docs/drivers/common/BACnet-IP/device-att-1.png)

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

    3. 인스턴스 No
        - 0 ~ 9999 의 정수값

    4. 속성 No
        - AI : Analog Input

        |속성 No| 설명|아이템 유무|
        |:------|:---|:---------|
        |75|	Object_Identifier|“아이템 No” ① 항목 참조|
        |77|Object_Name	||
        |79	|Object_Type||	
        |85	|Present_Value||	
        |28	|Description||
        |31	|Device_Type||	
        |111|	Status_Flags	|“아이템 No” ② 항목 참조|
        |36	|Event_State||
        |103|	Reliability||	
        |81	|Out_Of_Service	||
        |118|	Update_Interval||	
        |117|	Units	||
        |69	|Min_Pres_Value	||
        |65	|Max_Pres_Value	||
        |106|	Resolution	||
        |22	|COV_Increment	||
        |113|	Time_Delay	||
        |17	|Notification_Class	||
        |45	|High_Limit	||
        |59	|Low_Limit	||
        |25	|Deadband	||
        |52	|Limit_Enable|	“아이템 No” ② 항목 참조|
        |35	|Event_Enable|	“아이템 No” ② 항목 참조|
        |0	|Acked_Transitions|	“아이템 No” ② 항목 참조|
        |72	|Notify_Type	||

        - AO : Analog Output
         
        |속성 No|	설명|	아이템 유무|
        |:-----|:-----|:------------|
        |75	|Object_Identifier	|“아이템 No” ① 항목 참조|
        |77|	Object_Name	||
        |79|	Object_Type||	
        |85	|Present_Value||
        |28|	Description	||
        |31	|Device_Type	||
        |111|	Status_Flags	|“아이템 No” ② 항목 참조|
        |36	|Event_State||	
        |103|	Reliability	||
        |81|	Out_Of_Service	||
        |117|	Units	||
        |69|	Min_Pres_Value	||
        |65|	Max_Pres_Value	||
        |106|	Resolution	||
        |87	|Priority_Array	||
        |104	|Relinquish_Default	||
        |22	|COV_Increment	||
        |113|Time_Delay	||
        |17	|Notification_Class	||
        |45	|High_Limit	||
        |59	|Low_Limit	||
        |25	|Deadband||	
        |52	|Limit_Enable|	“아이템 No” ② 항목 참조|
        |35	|Event_Enable|“아이템 No” ② 항목 참조|
        |0	|Acked_Transitions|	“아이템 No” ② 항목 참조|
        |72	|Notify_Type	||

        - AV: Analog Value

        |속성 No|	설명	|아이템 유무|
        |75|	Object_Identifier	|“아이템 No” ① 항목 참조|
        |77|	Object_Name||	
        |79|	Object_Type||	
        |85|	Present_Value||	
        |28	|Description||	
        |111|	Status_Flags|	“아이템 No” ② 항목 참조|
        |36|	Event_State	||
        |103|	Reliability||	
        |81	|Out_Of_Service||	
        |117|	Units||	
        |87	|Priority_Array||	
        |104|	Relinquish_Default||	
        |22|	COV_Increment||	
        |113|	Time_Delay	||
        |17|	Notification_Class||	
        |45	|High_Limit	||
        |59	    |Low_Limit||	
        |25|	Deadband||	
        |52	|Limit_Enable|	“아이템 No” ② 항목 참조|
        |35|	Event_Enable|	“아이템 No” ② 항목 참조|
        |0	|Acked_Transitions|	“아이템 No” ② 항목 참조|
        |72	|Notify_Type	||

        - BI: Binary Input

       | 속성 No | 설명                | 아이템 유무            |   
        |-------|-------------------|----------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조    |
        | 77    | Object_Name       |                      |
        | 79    | Object_Type       |                      |
        | 85    | Present_Value     |                      |
        | 28    | Description       |                      |
        | 31    | Device_Type       |                      |
        | 111   | Status_Flags      | “아이템 No” ② 항목 참조     |
        | 36    | Event_State       |                      |
        | 103   | Reliability       |                      |
        | 81  | Out_Of_Service            |                      |
        | 84  | Polarity                  |                      |
        | 46  | Inactive_Text             |                      |
        | 4   | Active_Text               |                      |
        | 16  | Change_Of_State_Time      | “아이템 No” ④ 항목 참조     |
        | 15  | Change_Of_State_Count     |                      |
        | 115 | Time_Of_State_Count_Reset | “아이템 No” ④ 항목 참조     |
        | 33  | Elapsed_Active_Time       |                      |
        | 114 | Time_Of_Active_Time_Reset | “아이템 No” ④ 항목 참조    |
        | 113 | Time_Delay         |                      |
        | 17  | Notification_Class |                     |
        | 6   | Alarm_Value        |                     |
        | 35  | Event_Enable       | “아이템 No” ② 항목 참조     |
        | 0   | Acked_Transitions  | “아이템 No” ② 항목 참조    |
        | 72  | Notify_Type        |                    |

        - BO: Binary Output

        | 속성 No | 설명                        | 아이템 유무            |
        |-------|---------------------------|-------------------|
        | 75    | Object_Identifier         | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name               |                   |
        | 79    | Object_Type               |                   |
        | 85    | Present_Value             |                   |
        | 28    | Description               |                   |
        | 31    | Device_Type               |                   |
        | 111   | Status_Flags              | “아이템 No” ② 항목 참조  |
        | 36    | Event_State               |                   |
        | 103   | Reliability               |                   |
        | 81    | Out_Of_Service            |                   |
        | 84    | Polarity                  |                   |
        | 46    | Inactive_Text             |                   |
        | 4     | Active_Text               |                   |
        | 16    | Change_Of_State_Time      | “아이템 No” ④ 항목 참조  |
        | 15    | Change_Of_State_Count     |                   |
        | 115   | Time_Of_State_Count_Reset | “아이템 No” ④ 항목 참조  |
        | 33    | Elapsed_Active_Time       |                   |
        | 114   | Time_Of_Active_Time_Reset | “아이템 No” ④ 항목 참조  |
        | 66    | Minimum_Off_Time          |                   |
        | 67  | Minimum_On_Time    |                   |
        | 87  | Priority_Arrray    |                   |
        | 104 | Relinquish_Default |                   |
        | 113 | Time_Delay         |                   |
        | 17  | Notification_Class |                   |
        | 40  | Feedback_Value     |                   |
        | 35  | Event_Enable       | “아이템 No” ② 항목 참조  |
        | 0   | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        | 72  | Notify_Type        |                   |

        - BV: Binary Value

        | 속성 No | 설명                        | 아이템 유무            |
        |-------|---------------------------|-------------------|
        | 75    | Object_Identifier         | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name               |                   |
        | 79    | Object_Type               |                   |
        | 85    | Present_Value             |                   |
        | 28    | Description               |                   |
        | 111   | Status_Flags              | “아이템 No” ② 항목 참조  |
        | 36    | Event_State               |                   |
        | 103   | Reliability               |                   |
        | 81    | Out_Of_Service            |                   |
        | 46    | Inactive_Text             |                   |
        | 4     | Active_Text               |                   |
        | 16    | Change_Of_State_Time      | “아이템 No” ④ 항목 참조  |
        | 15    | Change_Of_State_Count     |                   |
        | 115   | Time_Of_State_Count_Reset | “아이템 No” ④ 항목 참조  |
        | 33    | Elapsed_Active_Time       |                   |
        | 114   | Time_Of_Active_Time_Reset | “아이템 No” ④ 항목 참조  |
        | 66    | Minimum_Off_Time          |                   |
        | 67    | Minimum_On_Time           |                   |
        | 87    | Priority_Array            |                   |
        | 104 | Relinquish_Default |                   |
        | 113 | Time_Delay         |                   |
        | 17  | Notification_Class |                   |
        | 6   | Alarm_Value        |                   |
        | 35  | Event_Enable       | “아이템 No” ② 항목 참조  |
        | 0   | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        | 72  | Notify_Type        |                   |

        - CD: Calendar

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 28    | Description       |                   |
        | 85    | Present_Value     |                   |

        - CM: Command

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 28    | Description       |                   |
        | 85    | Present_Value     |                   |

        - DV: Device

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 28    | Description       |                   |
        | 121   | Vendor_Name       |                   |
        | 120   | Vendor_Identifier |                   |
        | 56    | Local_Date        | “아이템 No” ③ 항목 참조  |
        | 57    | Local_Time        | “아이템 No” ③ 항목 참조  |

        - ER: Event Enrollment

        | 속성 No | 설명                 | 아이템 유무            |
        |-------|--------------------|-------------------|
        | 75    | Object_Identifier  | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name        |                   |
        | 79    | Object_Type        |                   |
        | 28    | Description        |                   |
        | 37    | Event_Type         |                   |
        | 72    | Notify_Type        |                   |
        | 36    | Event_State        |                   |
        | 35    | Event_Enable       | “아이템 No” ② 항목 참조  |
        | 0     | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        | 17    | Notification_Class |                   |

        - FI: File

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 28    | Description       |                   |

        - GR: Group

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 28    | Description       |                   |

        - LP: Loop

        | 속성 No | 설명                | 아이템 유무            |
        |-------|-------------------|-------------------|
        | 75    | Object_Identifier | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name       |                   |
        | 79    | Object_Type       |                   |
        | 85    | Present_Value     |                   |
        | 28    | Description       |                   |

        - MI: Multi-State-Input

        | 속성 No | 설명                 | 아이템 유무            |
        |-------|--------------------|-------------------|
        | 75    | Object_Identifier  | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name        |                   |
        | 79    | Object_Type        |                   |
        | 85    | Present_Value      |                   |
        | 28    | Description        |                   |
        | 31    | Device_Type        |                   |
        | 111   | Status_Flags       | “아이템 No” ② 항목 참조  |
        | 36    | Event_State        |                   |
        | 103   | Reliability        |                   |
        | 81    | Out_Of_Service     |                   |
        | 74    | Number_Of_States   |                   |
        | 110   | State_Text         |                   |
        | 113   | Time_Delay         |                   |
        | 17    | Notification_Class |                   |
        | 7     | Alarm_Values       |                   |
        | 39    | Fault_Values       |                   |
        | 35    | Event_Enable       | “아이템 No” ② 항목 참조  |
        | 0     | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        | 72    | Notify_Type        |                   |


        - MO: Multi-State-Output

        | 속성 No | 설명                 | 아이템 유무            |
        |-------|--------------------|-------------------|
        | 75    | Object_Identifier  | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name        |                   |
        | 79    | Object_Type        |                   |
        | 85    | Present_Value      |                   |
        | 28    | Description        |                   |
        |  31    | Device_Type        |                   |
        | 111   | Status_Flags       | “아이템 No” ② 항목 참조  |
        | 36    | Event_State        |                   |
        | 103   | Reliability        |                   |
        | 81    | Out_Of_Service     |                   |
        | 74    | Number_Of_States   |                   |
        | 110   | State_Text         |                   |
        | 87    | Priority_Arrray    |                   |
        | 104   | Relinquish_Default |                   |
        | 113   | Time_Delay         |                   |
        | 17    | Notification_Class |                   |
        | 40    | Feedback_Value     |                   |
        | 35    | Event_Enable       | “아이템 No” ② 항목 참조  |
        | 0     | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        |72|	Notify_Type||	

        - NC: Notification Class

        | 속성 No | 설명                 | 아이템 유무            |
        |-------|--------------------|-------------------|
        | 75    | Object_Identifier  | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name        |                   |
        | 79    | Object_Type        |                   |
        | 28    | Description        |                   |
        | 17    | Notification_Class |                   |
        | 86    | Priority           |                   |
        | 1     | Ack_Required       |                   |

        - PG: Program

        | 속성 No | 설명                  | 아이템 유무            |
        |-------|---------------------|-------------------|
        | 75    | Object_Identifier   | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name         |                   |
        | 79    | Object_Type         |                   |
        | 92    | Program_State       |                   |
        | 90    | Program_Change      |                   |
        | 100   | Reason_For_Halt     |                   |
        | 29    | Description_Of_Halt |                   |
        | 91    | Program_Location    |                   |
        | 28    | Description         |                   |
        | 48    | Instance_Of         |                   |
        | 111   | Status_Flags        | “아이템 No” ② 항목 참조  |
        | 103   | Reliability         |                   |
        | 81    | Out_Of_Service      |                   |

        - SC: Schedule

        | 속성 No | 설명                   | 아이템 유무            |
        |-------|----------------------|-------------------|
        | 75    | Object_Identifier    | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name          |                   |
        | 79    | Object_Type          |                   |
        | 85    | Present_Value        |                   |
        | 28    | Description          |                   |
        | 88    | Priority_For_Writing |                   |

        - MV: Multi-State-Value

        | 속성 No | 설명                 | 아이템 유무            |
        |-------|--------------------|-------------------|
        | 75    | Object_Identifier  | “아이템 No” ① 항목 참조  |
        | 77    | Object_Name        |                   |
        | 79    | Object_Type        |                   |
        | 85    | Present_Value      |                   |
        | 28    | Description        |                   |
        | 111   | Status_Flags       | “아이템 No” ② 항목 참조  |
        | 36    | Event_State        |                   |
        | 103   | Reliability        |                   |
        | 81    | Out_Of_Service     |                   |
        | 74    | Number_Of_States   |                   |
        | 110   | State_Text         |                   |
        | 87    | Priority_Array     |                   |
        | 104   | Relinquish_Default |                   |
        | 113   | Time_Delay         |                   |
        | 17    | Notification_Class |                   |
        | 7     | Alarm_Values       |                   |
        | 39    | Fault_Values       |                   |
        | 35    | Event_Values       | “아이템 No” ② 항목 참조  |
        | 0     | Acked_Transitions  | “아이템 No” ② 항목 참조  |
        |72	|Notify_Type||
     
    5. 아이템 No
        1.  OBJECT IDENTIFIER

        | 아이템 No | 설명           |   
        |--------|--------------|
        | 0      | Object Type  |   
        | 1      | Instance No  |

        2. Bit String

        | 아이템 No | 설명           |
        |--------|--------------|
        | 비트 위치값 | 해당 비트 위치 입력  |

        3. Date/Time

        | 아이템 No | Date  | Time    |
        |--------|-------|---------|
        | 0      | Week  | 100ms   |
        | 1      | Day   | Second  |
        | 2      | Month | Minute  |
        | 3      | Year  | Hour    |


        4. Date + Time

        | 아이템 No | 설명      |
        |--------|---------|
        | 0      | Week    |
        | 1      | Day     |
        | 2      | Month   |
        | 3      | Year    |
        | 4      | 100ms   |
        | 5      | Second  |




 

         
         
         
         
         
         
         

        










