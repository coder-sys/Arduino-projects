#include<Adafruit_SSD1306.h>
#include<Adafruit_GFX.h>
#include<Wire.h>
#include<Adafruit_AM2320.h>
#include<SoftwareSerial.h>
#include "TFMini.h"
#define OLED_RESET 4;s
Adafruit_SSD1306 display(OLED_RESET);
Adafruit_AM2320 am2320 = Adafruit_AM2320();
SoftwareSerial myser(10,11);
TFMini tfmini;
void setup(){
  Wire.begin();
  am2320.begin();
  display.begin(SSD1306_SWITCHCAPVCC,0x3C);
  myser.begin(TFMINI_BAUDRATE);
  tfmini.begin(&myser);
  
}
void loop(){
  delay(2000);
  float h = am2320.readHumidity();
  float t = am2320.readTemperature();
  float d = tfmini.getDistance();
  float s_s = tfmini.getRecentSignalStrength();
  display.setTextSize(1);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.print("sup!");
  display.setCursor(0,3);
  display.print(h);
  display.setCursor(0,6);
  display.print(s_s);
  display.setCursor(1,6);
  display.print(t);
  display.setCursor(2,0);
  display.print(d);
  display.display();
}
