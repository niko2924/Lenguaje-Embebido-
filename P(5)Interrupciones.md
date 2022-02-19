# Interrupciones 

![Esta es una imagen de ejemplo](https://learn.adafruit.com/system/assets/assets/000/021/334/medium640/components_interrupt.png?1416523011)

> Partes especiales de Arduino para poder trabajar por fases el programa.

### Interrupciones segun el arduino 
![Esta es una imagen de ejemplo](https://ardubasic.files.wordpress.com/2015/01/interrupciones_arduino.png)

Las interrupciones son útiles para hacer que las cosas sucedan de forma automática en los programas de microcontroladores, y
pueden ayudar a resolver problemas de
tiempo.

>attachInterrupt () es la función que no permite trabajar con interrupciones, es necesario la creación de subrutinas

## `AttachInterrupt()`

attachInterrupt(interrupt,ISR,modo

)

Interrupt: el número de la interrupción

ISR: Subrutina a llamar

Modo: Definir el modo de trabajo

 `LOW LEVEL`

 `CHANGE `

 `RISING`

Sintaxis:

attachInterrupt(0,INT0,CHANGE)

**Subrutina:**

Sintaxis:

void INT0 ( )
{

staado=1-estado ;

}
 
 ##  **Código Attach.ino**

 #define led 10

 volatile int state=LOW;

 `int` on=0;

 void setup() {
                       
 attachInterrupt (0,INT,`LOW`);
>Configuración de Interrupción

 pinMode(led,`OUTPUT`);

 }

 void loop() {

 if(on==1){

  `digitalWrite` ( led , state = ! state) ;
  >Estructura de toogle

 delay(500);

 }

 }

 void INT()

 {
 `on=1-on;`

 }
 > Subrutina de interrupción para activar al led 

##  **Código SerialEvent.ino**

#define led 10

volatile int state=LOW;

 `int` tiempo=500;

char inChar;

void loop() {

digitalWrite ( led , state = ! state) ;

delay(tiempo);

}
> Programación de toogle del led, con delay manejado por interrupciones 

void serialEvent(){

while (Serial.available()) {
>Subrutina de interrupción de comunicación serial 

inChar=(char)Serial.read();

if(inChar=='A'){
>Estructura de recepción de dato mediante interrupción

tiempo=100;

}

}

}




