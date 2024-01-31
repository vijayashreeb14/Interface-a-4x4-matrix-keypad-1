# Interfacing a 4x4 matrix keypad

## Aim: 
To simulate the interface of a 4x4 matrix keypad to ARM controller and display the output on 16X2 LCD for keys 4,5,6 only.

## Components required: 
STM32 CUBE IDE, Proteus 8 simulator .

## Keypad layout
![Keypad](https://github.com/Sripriya-Ranganathan/Interfacing-4x4-matrix-keypad/assets/139522903/b66a0414-4590-41d0-bb83-48588ee380b9)

## CIRCUIT DIAGRAM 
 
## Program
### Header files
#include "main.h"

#include <stdbool.h>

#include "lcd.h"

### Variables declaration
bool col1,col2,col3,col4;

### Functions declaration
void SystemClock_Config(void);

static void MX_GPIO_Init(void);

void key();

### User defined function definition
void key()

{

 ### Initialize the input and output pins of the keypad

  ---------

  ---------
 
  
  if(!col1)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, " -------\n");
	 	 
     HAL_Delay(500);
	 
  }
	
  else if(!col2)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	   
     HAL_Delay(500);
	 
  }
	
  else if(!col3)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	  
    HAL_Delay(500);
	 
  }
	
  else if(!col4)
	
  {
	
     Lcd_cursor(&lcd, 0,1);
	 	 
     Lcd_string(&lcd, "--------\n");
	   
     HAL_Delay(500);
	 
  }
	
  HAL_Delay(100);

}

### Main function

int main(void)

{

  HAL_Init();
  
  SystemClock_Config();
  
  MX_GPIO_Init();
  
  Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
	
 Lcd_PinType pins[] = {GPIO_PIN_3, GPIO_PIN_2, GPIO_PIN_1, GPIO_PIN_0};

 Lcd_HandleTypeDef lcd;

 lcd = Lcd_create(ports, pins, GPIOB, GPIO_PIN_0, GPIOB, GPIO_PIN_1, LCD_4_BIT_MODE);
 
   while (1)
   
    {
  
  ### function call
  
    key();
	 
  }

}

## Output screen shots of proteus

## Result :
Interfaced a 4x4 matrix keypad with ARM microcontroller and displayed the output on 16X2 LCD for keys 4,5,6 in simulation.
