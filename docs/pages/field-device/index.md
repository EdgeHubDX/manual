---
layout: default
parent: Pages
title: 필드 디바이스
has_children: true
nav_order: 8
---

# Field Device
Field Device는 DataWorX에서 사용할 채널, 디바이스, 블록을 등록하고 관리하기 위한 메뉴입니다.
장비로부터 데이터를 수집하여 상위 프로세스로 전송하는 S/W입니다.
Field Device 메뉴에서 통신채널, 디바이스, 통신블록을 추가/설정 할 수 있습니다.
자세한 내용은 하위 페이지를 참고 바랍니다.

## 드라이버 목록  
현재 DataWorX에서 지원되는 디바이스 드라이버의 목록은 다음과 같습니다.

| 번호 | 통신 드라이버     | 설명                                | PROTOCOL           | 제조사        |
|----- |------------------|------------------------------------|--------------------|--------------|
| 1    | ModbusTCP        | ModbusTCP                          | TCP/UDP            | 공통          |
| 2    | XGKEnet          | XGKEnet                            | TCP/UDP            | LS ELECTRIC  |
| 3    | BACnetIP         | BACnetIP                           | UDP                | 공통          |
| 4    | ModbusRTU        | ModbusRTU                          | RS232/422/485      | 공통          |
| 5    | MelsecQEnet      | MITSUBISHI Q 시리즈 Ethernet        | TCP/UDP            | MITSUBISHI   |
| 6    | OmronE           | Omron Ethernet (FINS)              | TCP/UDP            | Omron        |
| 7    | ModbusRTUGW      | ModbusRTUGW                        | TCP/UDP            | 공통          |
| 8    | ABEthernetIP     | Allen-Bradley Ethernet/IP          | TCP/UDP            | ABB          |
| 9    | SiemensISOEnet   | Siemens ISO Ethernet               | TCP/UDP            | Siemens      |
| 10   | MelsecQSerial    | MITSUBISHI Q 시리즈 Serial          | RS232/422/485      | MITSUBISHI   |
| 11   | OmronS           | Omron CJ/CS Serial (Host Link)     | RS232/422/485      | Omron        |
| 12   | KeyenceE         | KEYENCE Ethernet                   | TCP/UDP            | KEYENCE      |
| 13   | MKEnet           | MASTER-K S Series Ethenet          | TCP/UDP            | LS ELECTRIC  |
| 14   | GlofaEnet        | GLOFA-GM Enet                      | TCP/UDP            | LS ELECTRIC  |
| 15   | MKCnet           | MASTER-K S Series Computer Link    | RS232/422/485      | LS ELECTRIC  |
| 16   | MelsecFXEthernet | MITSUBISHI FX Ethernet             | TCP/UDP            | MITSUBISHI   |
| 17   | GlofaCnet        | GLOFA-GM Cnet                      | RS232/422/485      | LS ELECTRIC  |
| 18   | MelsecFXSerial   | MITSUBISHI FX Serial               | RS232/422/485      | MITSUBISHI   |
| 19   | SiemensRK512     | Siemens RK512                      | RS232/422/485      | Siemens      |
| 20   | NaisS            | Panasonic Nais (FP 시리즈) Serial   | RS232/422/485      | Panasonic    |
| 21   | NXCCU            | Allen-Bradley NX-CCU               | RS232/422/485      | ABB          |
| 22   | OPCUAClient      | OPCUAClient                        | TCP/UDP            | 공통          |
| 23   | XGIEnet          | XGIEnet                            | TCP/UDP            | LS ELECTRIC  |
| 24   | XGREnet          | XGREnet                            | TCP/UDP            | LS ELECTRIC  |
| 25   | XGKCnet          | XGK Cnet                           | RS232/422/485      | LS ELECTRIC  |
| 26   | XGICnet          | XGI Cnet                           | RS232/422/485      | LS ELECTRIC  |
| 27   | XGKLoader        | XGK Loader                         | RS232              | LS ELECTRIC  |
| 28   | XGILoader        | XGI Loader                         | RS232              | LS ELECTRIC  |
| 29   | GlofaLoader      | GLOFA-GM Loader                    | RS232/422/485      | LS ELECTRIC  |
| 30   | MKLoader         | MASTER-K S Series Loader Port      | RS232              | LS ELECTRIC  |
| 31   | MelsecFXLoader   | MITSUBISHI FX Loader               | RS232/422/485      | MITSUBISHI   |
| 32   | MelsecASerial    | MITSUBISHI A Serial                | RS232/422/485      | MITSUBISHI   |
| 33   | MelsecAEthernet  | MITSUBISHI A Ethernet              | TCP/UDP            | MITSUBISHI   |
| 34   | CimonEnet        | CIMON Ethernet                     | TCP/UDP            | CIMON        |
| 35   | YASHSEnetSvr     | YASKAWA High-Speed Ethernet Server | TCP/UDP            | YASKAWA      |
| 36   | IEC61850Client   | IEC61850Client                     | TCP/UDP            | Common       |
| 37   | DNPMasterE       | DNPMaster Ethernet                 | TCP/UDP            | Common       |
| 38   | DNPMasterS       | DNPMaster Serial                   | RS232/422/485      | Common       |
  