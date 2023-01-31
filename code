#include <Wire.h> 
#include <LiquidCrystal_I2C.h>
LiquidCrystal_I2C lcd(0x27,16,2);  // set the LCD address to 0x27 for a 16 chars and 2 line display
void setup()
{
 lcd.init();                      // initialize the lcd 
 // Print a message to the LCD.
 lcd.backlight();

 Serial.begin(9600);
 
}
void loop()
{
 
  // Air Quality Measurement
int sv = analogRead(A0);
Serial.print("AQI: ");
Serial.print(sv , DEC);
Serial.println(" PPM");

if ( sv <= 400 ) 
{
  
lcd.setCursor(0,0) ;
lcd.print("Fresh Air");
lcd.setCursor(0,1) ;
lcd.print("AQI : ");
lcd.print(sv , DEC);
lcd.print(" PPM");
delay (1000) ;
}

else if ( sv > 400 && sv < 750 ) 
{
 
lcd.setCursor(0,0) ;
lcd.print("Air Quality:Good");

lcd.setCursor(0,1) ;
lcd.print("AQI : ");
lcd.print(sv , DEC);
lcd.print(" PPM");
delay (1000) ;
  
}
else if ( sv >= 750 && sv < 1200 )
{
lcd.setCursor(0,0) ;
lcd.print("Air Quality:Bad");
lcd.setCursor(0,1) ;
lcd.print("AQI : ");
lcd.print(sv , DEC);
lcd.print(" PPM");
delay (1000) ;
}
else if ( sv > 1200) 
{
lcd.setCursor(0,0) ;
lcd.print("Air Quality:Harm");
lcd.setCursor(0,1) ;
lcd.print("AQI : ");
lcd.print(sv , DEC);
lcd.print(" PPM");
delay (1000) ;
}

}
