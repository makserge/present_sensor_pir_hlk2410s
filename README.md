# Human present sensor with PIR and HLK-LD2410S

Used this lamp "Motion Sensor Led Light Usb Charging Square Lamp for Bedroom Kitchen Stair Hallway Wardrobe Cupboard Lighting" (https://www.aliexpress.com/item/1005005112043055.html)

Based on sensor descibed here
https://www.reddit.com/r/Esphome/comments/1eiz70l/hybrid_batterybased_human_presence_sensor_v3/

1. Update firmware on HLK-LD2410S

Connect the LD2410S sensor to a computer via the USB to serial adaptor.
OT1 is the sensor's uart TX. 3.3V is is the sensor's 3.3v
Download the 3 files from Software Application section of Hi-Link's website (https://www.hlktech.com/en/Goods-224.html).
All files also mirrored here

Download and extract HLK-LD2410S_TOOL_v1.2.0.15.zip
(https://github.com/makserge/present_sensor_pir_hlk2410s/raw/main/HLK-LD2410S_TOOL_v1.2.0.15.zip)

Connect the LD2410S sensor from serial at bottom left, press Update FW button
Select the .bin firmware from the HLK-LD2410S(new_1.1.1).zip (https://github.com/makserge/present_sensor_pir_hlk2410s/raw/main/HLK-LD2410S(new_1.1.1).bin) and press Obtain Firmware Info then press Flash to update

Download HLK-LD2410S_TOOL_1.3.0.1.zip (https://github.com/makserge/present_sensor_pir_hlk2410s/raw/main/HLK-LD2410S_TOOL_1.3.0.1.zip)

Configure the max-range and min-range, in 0.7m steps
Set the absence time to 10s

2. Wiring
 
Connect PIR's output to pin1, radar's out  to pin2, photoresistor to pin3, mosfet input to pin4

3. Flashing ESPHome
   Open HA->Add-Ons->ESPHome->Open Web UI->New Device->Open ESPHome Web
   Press Boot on ESP32 and connect to computer
   Press Connect and select port "tty.usbmodem*" and the press Connect
   Press Prepare for first use then press Install then Close
   Connect to Wi-Fi network "esphome-web*"
   Open http://192.168.4.1/ in browser and connect to Wi-Fi
   Connect to main Wi-Fi network
   Open HA->Add-Ons->ESPHome->Open Web UI
   On new discovered device "ESPHome Web *" press Adopt
   Enter new name "BLE Presence Sensor" and press Adopt, then press Install
   
   
   
