# Iot-based-electricity-conservation-system
#define BLYNK_PRINT Serial
#include <ESP8266WiFi.h>
#include <BlynkSimpleEsp8266.h>
intpirPin = 14;
intrelayPin = 5;
intpirValue;
charauth[] = "b5whlJ5X5TIirBeH54r8PBWCdNgIZc1q"; //auth token
charssid[] = "username";
char pass[] = "password";
void setup()
{
Serial.begin(115200);
Blynk.begin(auth, ssid, pass);
pinMode(pirPin, INPUT);
pinMode(relayPin, OUTPUT);
}
voidpirSensor()
{
pirValue = digitalRead(pirPin);
Blynk.virtualWrite(V0, pirValue);
}
void loop()
{
Blynk.run();
pirSensor();
if (pirValue == HIGH)
  {
digitalWrite(relayPin,LOW );
  }
else
digitalWrite(relayPin,HIGH); 
void setup()
{
Serial.begin(9600);
}
void loop()
{
float average=0;
for(int i=0;i<1000;i++)
{
average=average+(.0264*analogRead(A0)-13.51;//for the 5A mode,
delay(1);
}
Serial.print(“Current:”);
Serial.print(average/1000);
Serial.println(“A”);
}
}
}
