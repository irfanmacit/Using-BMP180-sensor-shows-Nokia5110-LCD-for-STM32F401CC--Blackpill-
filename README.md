# BMP180 sensor for STM32F401CC (Blackpill)
 This projeck is for STM32F401CC development board.
Setup project:
  1. BMP180 sensor
  2. Nokia5110 LCD screen
  3. STM32F401CC development board.

1. BMP180 sensor: you should connect its Vcc and Vss on your board, and signal SCL and SCA port should be connect board's PB06 and PB07 respectivelly. 
2. Nokia5110 LCD screen: some of point you should careful to connect between board and screen. if you see project ioc files which port will be use connection and how. Pleas never Forget the name of the Pin as you can see, it is very important to change the name of pin ;

3.      Nokia 5110 screen      STM32F401 board's Pin         Pin Name
           RST                      PA03                     LCD_RST
           CE                       PA04                     LCD_CE
           DC                       PA05                     LCD_DC
           DIN                      PA06                     LCD_DATA
           CLK                      PA07                     LCD_CLK
           
4. If you see measuments of the sensor, you can see it on your serial terminal by using USBTTL (there are many USBTTL tool such as CH340, PL2303 chipset), after you connect from the STM32 board to computer. Connection from STM32 board to computer you can use PA09 Tx --> USBTTL Rx and PA10 Rx --> USBTTL Tx port and then open your terminal window and data seems on the terminal. 
5. If you download my python interface for this project and properly setup this software you can see three important sensor data on the dashboard (coming soon). 
