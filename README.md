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
6. STM32F401CC board has a PC13 internal LED, while program running this blue LED is ON when the temperature level under 30.0 degree Celcius. If temperature level is more than 30.0 degree Celcius PA1 port is on, if you connect a LED for this port, it will be on when the temperature is more than 30. degree Celcius.  
7. You can change degree of the LED's on level sicaklik variable. LED's on/off is controlled by sicaklik variable.


        if(sicaklik > 30 )
              {
               HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_SET);
               HAL_GPIO_WritePin(GPIOA, GPIO_PIN_1, GPIO_PIN_SET);
               LCD_print("YUKSEKSICAKLIK", 0, 5);
              }
              else
              {
               HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_RESET);
               HAL_GPIO_WritePin(GPIOA, GPIO_PIN_1, GPIO_PIN_RESET);
               LCD_print("==============", 0, 5);
	}
8. You can edit LCD messages of your prefering or you like, such as "YUKSEKSICAKLIK" as a "HIGH TEMP".
9. USART handle type definition variable &huart1 sends measurement variable level, sicaklik means temperature, yukseklik as altitude, basinc as pressure. You can change which you like. 


