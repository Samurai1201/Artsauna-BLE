# Artsauna-BLE
Reverse Engineering of the AI-Control App for sauna with chinese control unit by Shen Zhen EasyWay Technology Limited (i.e. Artsauna)

BLE Mac-Address: 9e:02:c8:a7:3a:76 (maybe different for other models? Use Lightblue on your phone to find the right bluetooth mac-address)

All commands the app issues are write requests to handle 0x0009, specifically to the following characteristics and service UUIDs:

All to handle 0x0009 -> char uuid: 0000ae01-0000-1000-8000-00805f9b34fb -> Service uuid: 0000ae00-0000-1000-8000-00805f9b34Tb


Results of scan using gatttool on linux host:
```
[9E: 02: C8: A7:3A: 76] [LE]> primary
attr handle: 0x0001, end grp handle: 0x0003 uuid: 00001800-0000-1000-8000-00805f9b34fb 
attr handle: 0x0004, end grp handle: 0x0006 uuid: 00001801-0000-1000-8000-00805f9b34fb 
attr handle: 0x0007, end grp handle: 0x000e uuid: 0000ae00-0000-1000-8000-00805f9b34Tb
[9E: 02: C8:A7:3A:76][LE]> characteristics 0x0001 0x0003
handle: 0x0002, char properties: 0x02, char value handle: 0x0003, uuid: 00002a00-0000-1000-8000-00805f9b34fb
[9E: 02: C8:A7:3A: 76] [LE]> characteristics 0x0004 0x0006
handle: 0x0005, char properties: 0x02, char value handle: 0x0006, uuid: 00002a05-0000-1000-8000-00805f9b34fb
[9E: 02: C8: A7:3A: 76] [LE]> characteristics 0x0007 0x000e
handLe: 0x0008, char properties: 0x08, char value handle: 0x0009, uuid: 0000ae01-0000-1000-8000-00805f9b34fb 
handle: 0x000a, char properties: 0x02, char value handle: 0x000b, uuid: 0000ae02-0000-1000-8000-00805f9b34fb 
handle: 0x000c, char properties: 0x10, char value handle: 0x000d, uuid: 0000ae03-0000-1000-8000-00805f9b34fb
```
