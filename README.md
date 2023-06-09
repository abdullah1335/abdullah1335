- Abdullah Uraslı
-  Proje : Nokia 5110 ekranı ile nabız ölçer
-  Kodlar :
-  Word :[ROBOTİK KODLAMA.docx](https://github.com/abdullah1335/abdullah1335/files/11705031/ROBOTIK.KODLAMA.docx)

   
 -----------------------------------------------
 
- #include <LCD5110_Basic.h> 
- LCD5110 myGLCD(8, 9, 10, 11, 12); 
- #define USE_ARDUINO_INTERRUPTS true  
- #include <PulseSensorPlayground.h> 
- int nabiz; 
- int lcd_ledi = 6; 
- extern uint8_t SmallFont[];
- extern uint8_t BigNumbers[]; 
- const int PulseWire = 0; 
- const int LED13 = 13; 
- int Threshold = 580; 
- PulseSensorPlayground pulseSensor; 

- void setup() {
-   Serial.begin(9600);  
-   pulseSensor.analogInput(PulseWire); 
-   pulseSensor.blinkOnPulse(LED13);     
-   pulseSensor.setThreshold(Threshold); 
-   // put your setup code here, to run once:
-   digitalWrite(lcd_ledi, HIGH);
-   myGLCD.InitLCD(); 
-   myGLCD.setContrast(58); 
-   myGLCD.setFont(SmallFont); 
-   //myGLCD.drawBitmap(0,0, cmon, 84, 48);
-   myGLCD.print("Dakikadaki", CENTER, 0);
-   myGLCD.print("Nabziniz:", CENTER, 15); 
-   myGLCD.setFont(BigNumbers); 
-   myGLCD.printNumI(0, CENTER, 25); 
-   if (pulseSensor.begin()) {
-     Serial.println("Pulse sensörü objesini yarattık."); 
  } 

}
