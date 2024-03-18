#include <LiquidCrystal_I2C.h>
int led = 13;
int pirpin = 12;
int pirState = LOW;
int val = 0;
#define ldrpin 7
LiquidCrystal_I2C lcd(0x27,20,4);

void setup() {
pinMode(led, OUTPUT);
pinMode(pirpin, INPUT);
pinMode(ldrpin, INPUT);
Serial.begin(9600);
lcd.init();
lcd.backlight();
lcd.setCursor(1,0);
lcd.print("AUTOMATIC LIGHT");
lcd.setCursor(2,1);
lcd.print("  PURTIAY  ");
delay(2000);
lcd.clear();

}

void loop() {
  val = digitalRead(pirpin);
  if(val == LOW && digitalRead(ldrpin) == LOW){
    digitalWrite(led, LOW);
      lcd.setCursor(0,0);
      lcd.print("RUANG TERANG");
    if(pirState == HIGH){
      lcd.setCursor(0,1);
      lcd.print("Tidak Ada Gerakan");
      pirState == LOW;
    }
  }
  else{
  if(val == HIGH && digitalRead(ldrpin) == LOW){
    digitalWrite(led, LOW);
    lcd.setCursor(0,0);
    lcd.print("RUANG TERANG");
    if(pirState == LOW){
      lcd.setCursor(0,1);
      lcd.print("Ada Gerakan");
      pirState == HIGH;
    }
  }
  
  else{
    if(val == HIGH && digitalRead(ldrpin) == HIGH){
      digitalWrite(led, HIGH);
      lcd.setCursor(0,0);
      lcd.print("RUANG GELAP");
      if(pirState == LOW){
        lcd.setCursor(0,1);
        lcd.print("Ada Gerakan");
        pirState == HIGH;
      }
    }
  }
  }
  

}
