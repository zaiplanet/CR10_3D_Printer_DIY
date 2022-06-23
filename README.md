# Board MKS Gen L v1.0 clone with Mainsail OS and Klipper firmware on Rasp pi 3B+.
# X,Y use TMC2208 and dual step Z use A4988 (Z and E1)
# BLTouch clone

1. Follow instruction of Mainsail OS
2. Disconnect power source with printer
3. Turn on Pi and connect USB cable with printer board (because Gen L can't dual power outsource with 5V from usb. If you don't disconnect power, you may shock yourself or damage your equipment)
4. Baud rate for serial port from 250000 or 115200
5. From cmd, search connect usb with 'ls /dev/serial/by-id/*'
6. Flash klipper to MCU follow this https://www.klipper3d.org/Installation.html#building-and-flashing-the-micro-controller
7. After flashing completed, disconnect usb cable. Turn off power Pi.
8. Use UART to connect Pi with Gen L
9. On the RPI, I used pins 8: TXD (data send), 9: ground, and 10: RXD (data receive).
10. I connected these wires to pins in the AUX-1 header of Gen L.
11. RPI pin 8 (data send) to MKS gen L RX (data receive) / RPI pin 9 (ground) to MKS gen L GND (ground) / RPI pin 10 (data recieve) to MKS gen L TX (data send)
   
   ![image](https://user-images.githubusercontent.com/58675403/175226012-9c2d7df7-666f-4cad-aa89-2f4641ef2888.png)
   
9. Then, powered up the RPI and ssh to pi : ssh@ip_address
10. From cmd run 'sudo raspi-config'
11. Select Interfacing Options -> Serial -> Select No to login shell over serial -> Select Yes to serial port hardware to be enabled.

![image](https://user-images.githubusercontent.com/58675403/175226722-cddd161e-96e0-42bc-808f-c695f7ef15e1.png)

![image](https://user-images.githubusercontent.com/58675403/175226771-ffaf4f7b-9944-41a4-b806-8d418de16157.png)

![image](https://user-images.githubusercontent.com/58675403/175226804-49b366d5-02a8-428c-8a67-c6a9eca2e1b8.png)

![image](https://user-images.githubusercontent.com/58675403/175226850-000ec417-6189-47ab-9bb1-1a606516a7ff.png)

14. Then rebooted, closed everything up, and powered up my printer.
16. Edit klipper config file follow this https://www.klipper3d.org/Config_Reference.html
17. Check klipper configuration follow this https://www.klipper3d.org/Config_checks.html


- Klipper Arduino pin map: https://github.com/Klipper3d/klipper/blob/master/config/sample-aliases.cfg
