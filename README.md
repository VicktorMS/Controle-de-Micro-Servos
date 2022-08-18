# Controle de Micro Servos por Potenciometros
Projeto Com 4 Micro Servos controlados por 4 Potenciometros Usando Um Arduíno UNO.
Código Pronto pra uso em ".ino".

Código: 

#define potpin1  A0
#define potpin2  A1
#define potpin3  A2
#define potpin4  A3
 
#include <Servo.h>
 
Servo myservoBase;  
Servo myservoGarra;  
Servo myservoAltura; 
Servo myservoProfundidade; 
 
 
int val;    // variable to read the value from the analog pin
 
void setup()
{
  //Associa cada objeto a um pino pwm
  myservoBase.attach(3);
  myservoGarra.attach(5);
  myservoAltura.attach(9);
  myservoProfundidade.attach(11);
}
 
void loop()
{
 
  val = map(analogRead(potpin1), 0, 1023, 0, 179);
  myservoBase.write(val);
 
  val = map(analogRead(potpin2), 0, 1023, 0, 179);
  myservoGarra.write(val);
 
  val = map(analogRead(potpin3), 0, 1023, 0, 179);
  myservoAltura.write(val);
 
  val = map(analogRead(potpin4), 0, 1023, 0, 179);
  myservoProfundidade.write(val);
 
  delay(100);
}
