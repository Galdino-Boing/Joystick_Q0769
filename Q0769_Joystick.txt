// INCLUSÃO DE BIBLIOTECAS
#include <myPushButton.h>
#include <Joystick.h>

// DEFINIÇÕES DE PINOS
#define pinX A0
#define pinY A1
//#define pinX2 A3
//#define pinY2 A4

#define pinBotA 2
#define pinBotB 3
#define pinBotC 4
#define pinBotD 5
#define pinBotE 6
#define pinBotF 7
#define pinBotG 8
#define pinBotH 9

#define pinBotJ 10
#define pinBotK 11

// INSTANCIANDO OBJETOS
myPushButton botA(pinBotA, 20);
myPushButton botB(pinBotB, 20);
myPushButton botC(pinBotC, 20);
myPushButton botD(pinBotD, 20);
myPushButton botE(pinBotE, 20);
myPushButton botF(pinBotF, 20);
myPushButton botG(pinBotG, 20);
myPushButton botH(pinBotH, 20);

myPushButton botJ(pinBotJ, 20);
myPushButton botK(pinBotK, 20);

// DECLARAÇÃO DE FUNÇÕES


// DECLARAÇÃO DE VARIÁVEIS


void setup() {
  Serial.begin(9600);
  Joystick.begin();

  pinMode(pinX, INPUT);
  pinMode(pinY, INPUT);
  //pinMode(pinX2, INPUT);
  //pinMode(pinY2, INPUT);
}

void loop() {
  botA.lerBotao(); botB.lerBotao(); botC.lerBotao(); botD.lerBotao(); 
  botE.lerBotao(); botF.lerBotao(); botG.lerBotao(); botH.lerBotao();
  botJ.lerBotao(); botK.lerBotao();

  int anguloX = map(analogRead(pinX), 0, 1023, -126, 127);
  int anguloY = map(analogRead(pinY), 0, 1023, 127, -126);
  //int anguloX2 = map(analogRead(pinX2), 0, 1023, -126, 127);
  //int anguloY2 = map(analogRead(pinY2), 0, 1023, 127, -126);
  
  
  if(botA.pressed()) Joystick.pressButton(0);
  if(botB.pressed()) Joystick.pressButton(1);
  if(botC.pressed()) Joystick.pressButton(2);
  if(botD.pressed()) Joystick.pressButton(3);
  if(botE.pressed()) Joystick.pressButton(4);
  if(botF.pressed()) Joystick.pressButton(5);
  if(botG.pressed()) Joystick.pressButton(6);
  if(botH.pressed()) Joystick.pressButton(7);

  if(botJ.pressed()) Joystick.pressButton(8);
  if(botK.pressed()) Joystick.pressButton(9);

  if(botA.released()) Joystick.releaseButton(0);
  if(botB.released()) Joystick.releaseButton(1);
  if(botC.released()) Joystick.releaseButton(2);
  if(botD.released()) Joystick.releaseButton(3);
  if(botE.released()) Joystick.releaseButton(4);
  if(botF.released()) Joystick.releaseButton(5);
  if(botG.released()) Joystick.releaseButton(6);
  if(botH.released()) Joystick.releaseButton(7);

  if(botJ.released()) Joystick.releaseButton(8);
  if(botK.released()) Joystick.releaseButton(9);

  Joystick.setXAxis(anguloX);
  Joystick.setYAxis(anguloY);
  //Joystick.setXAxis(anguloX2);
  //Joystick.setYAxis(anguloY2);
}

// IMPLEMENTO DE FUNÇÕES
