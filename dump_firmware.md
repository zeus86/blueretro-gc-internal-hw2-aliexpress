# Guide to dump the flash:

## Step 1: Pinout...
...seems to be as follows:

top
```
1 2/VCC 3V3
2 25/GPIO0
3 3/EN
4 34/GPIO3
5 35/GPIO1
6 1/GND (square pin)
```
bottom (where the antenna is)

## Step 2: Board Info:
Use a TTL-Programmer, connection is as follows:

```
Programmer  -> ESP-Debug-Header  
  
3V3         -> VCC 3V3
GND         -> GND (Square Pin)
GND         -> 25/GPIO0 (Boot-Mode)
RX          -> 35/GPIO1
TX          -> 34/GPIO3
```

```
$ esptool.py  --port /dev/ttyUSB0 flash_id
esptool.py v4.8.1
Serial port /dev/ttyUSB0
Connecting...
Detecting chip type... Unsupported detection protocol, switching and trying again...
Connecting...
Detecting chip type... ESP32
Chip is ESP32-D0WDQ6 (revision v1.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: [REDACTED]
Stub is already running. No upload is necessary.
Manufacturer: c8
Device: 4017
Detected flash size: 8MB
Flash voltage set by a strapping pin to 3.3V
Hard resetting via RTS pin...
```

## Step 3: Dump Firmware:
```
$ esptool.py --baud 115200 --port /dev/ttyUSB0 read_flash 0x0 0x800000 iblueretro_stock-fw_8M.bin
esptool.py v4.8.1
Serial port /dev/ttyUSB0
Connecting...
Detecting chip type... Unsupported detection protocol, switching and trying again...
Connecting...
Detecting chip type... ESP32
Chip is ESP32-D0WDQ6 (revision v1.1)
Features: WiFi, BT, Dual Core, 240MHz, VRef calibration in efuse, Coding Scheme None
Crystal is 40MHz
MAC: [REDACTED]
Stub is already running. No upload is necessary.
Configuring flash size...
8388608 (100 %)
8388608 (100 %)
Read 8388608 bytes at 0x00000000 in 759.1 seconds (88.4 kbit/s)...
Hard resetting via RTS pin...
$
```

```
$ sha256sum iblueretro_stock-fw_8M.bin
b5d68df15420cda400ef869411441addc7c743c623fac86031af4a5977c63f9d  iblueretro_stock-fw_8M.bin
```
