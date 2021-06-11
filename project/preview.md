```
#include "dht.h"
#include <Wire.h>
#include <LiquidCrystal.h>
const int pino DHT11 = A7
dht DHT;


#define pinoRele 53
#define dht_pin A7
#define endereço 0x27

int ValAnalonIn = 0
int pinoAnalog = A14
LiquidCrystal_I2C lcd(endereco,16,2);

void setup(){
  lcd.int();
  Serial.begin(9600);
  Serial.println("Bem Vindo");
  pinMode(pinoRele, OUTPUT):
}


void loop (){
DHT.red11(pinoDHT11);
Serial.print("Umidade: ");
Serial.print(DHT.humdity);
Serial.print("%");
Serial.print("/ Temperatura: ");
Serial.print(DHT.temperature, 0);
Serial.println("*C");
delay(2000);


// Sensor de umidade do solo

ValAnalogIn = analogRead(pinoAnalog);
int Porcento = map(ValAnalogIn, 1023, 0, 0, 100);
Serial.print(Porcento);
Serial.println("%");

if (Porcento <=45) {
  Serial.println("Irrigando ...");
  digitalWrite(pinoRele, HIGH);
}
else if (Porcento <=75) {
  Serial.println("Médio");
  digitalWrite(pinoRele, LOW);
}
else if (Porcento = 100){
  Serial.println ("Umido");
  delay(1000);
}

//lcd

lcd.setBacklight(HIGH)
lcd.setCursor(0,0)
lcd.print("Sensor tempera-");
lcd.setCursor(0,1);
lcd.print("ura");
lcd.setCursor(3,1);
lcd.print("Temp = ");
lcd.print (DHT.temperature, 0 );
delay(1000);
lcd.setCursor(0,0)
lcd.print("Sensor Umidade ");
lcd.setCursor(0,1);
lcd.print("Umi = ");
lcd.print(Porcento);
lcd.print("    ");
delay(1000);


```

