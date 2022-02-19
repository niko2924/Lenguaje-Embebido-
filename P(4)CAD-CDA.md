# Entradas Analógicas
![Esta es una imagen de ejemplo](http://robots-argentina.com.ar/didactica/wp-content/uploads/PINOUT-ANALOGICO.png)

>Las tarjetas de arduino **generalmente cuentan con
6 entradas analógicas (A0 – A5)**.

Estas entradas funcionan como convertidores
Analógico a Digital (ADCs) de 10 bits

El voltaje de referencia de las entradas analógicas se 
puede ajustar mediante el pin Vin y el jumper Vin.
El jumper Vin es utilizado para configurar un voltaje 
de referencia de 5V

 ## `analogRead()`.

 Esta función es utilizada para leer un valor analógico de alguna de las terminales de entrada A0 a A5. 
 
 Este valor es representado por
 10 bits, arrojando valores enteros (int) entre 0 y 1023.


 Esta función tarda cerca de 100 microsegundos para leer una
 entrada analógica, por lo que el máximo número de lecturas es de
 10,000 por segundo.


 Sintaxis:  
 `analogRead()`

 Donde pin es el número de la terminal analógica a leer (A0 – A5)

 ## Código
 **AnalogInput.ino**

 `int` sensorPin = A0;
>Se declara una variable que representará la 
terminal analógica A0

 `int` ledPin = 13;

 `int` sensorValue = 0;
 >Variable que recibirá el valor analógico representado por 10 bits.

 `void` setup() {

 pinMode(ledPin, OUTPUT); 

 }
 >La terminal 13 se configura como salida.

 `void` loop() {

 sensorValue = analogRead(sensorPin);
 >Lectura de la terminal Analógica A0.

 digitalWrite(ledPin, HIGH);
 >Se cambia el estado del pin de salida enttre AlTO Y BAJO.

 delay(sensorValue);

 digitalWrite(ledPin, LOW);
 >Se cambia el estado del pin de salida enttre AlTO Y BAJO.

 delay(sensorValue);
 }

 # Salidas Análogas 

 ![Esta es una imagen de ejemplo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRBN2FR6R3LisN1mM7kIudaN7F4s_ngwB19sw&usqp=CAU)

 Se puede generar salidas análogas 
 tan pronto como sale de su caja, y no requiere hardware extra.

 Las salidas análogas son 
 generadas por medio de señales 
 PWM

_No todas las terminales de Arduino son capaces de generar una salida 
análoga, solo aquellos que están marcados con una tilde (~) junta a su 
identificador de terminal, son capaces de generar este tipo de señal._

`analogWrire()`

![Esta es una imagen de ejemplo](https://educaendigital.com/wp-content/uploads/2020/02/Captura-de-pantalla-2020-02-03-a-las-6.33.23.png)

La llamada a esta rutina indica a
una terminal de salida que debe de
generar una señal PWM de manera
continua con el ciclo de trabajo
indicado.

La señal PWM genera con esta
rutina se mantiene de manera
continua en la terminal de salida
hasta que se escribe un nuevo
`analogWrire()` a la misma terminal, o se ejecuta un 
`analogWrire()` o `digitalRead()`.

Sintaxis:

analogWrite(pin, CICLO)

CICLO: 0 a 255.

## Código fade.ino

`int` led = 9;

`int` brightness = 0;

`int` fadeAmount = 5;

`void setup`() {

`pinMode`(led,`OUTPUT`);

}

>`OUTPUT` Terminal 9 toma el rol de salida 

`void loop`() {

`analogWrite`(led, brightness);
brightness = brightness + fadeAmount;
>Escribir la cantidad de “brillo” que queremos obtener del led. En 
este casa el 100% de ciclo de trabajo esta representado por 
255.

`if` (brightness == 0 || brightness == 255)
fadeAmount = -fadeAmount;
>Una vez que se alcanza alguno de los valores 
máximos, se invierte de signo para alcanzar el valor 
opuesto de “brillo”

`delay`(`30`);

}

A continuación se muestra un [Link](https://youtu.be/CK9-RhWYriA "Librerias de Arduino").
# Control Servos

![Esta es una imagen de ejemplo](https://www.makerelectronico.com/wp-content/uploads/2020/04/tutorial-servomotor-arduino-2.png)

Biblioteca Servo.h

permite manejar 
de manera simple un servo motor.

Sin embargo requiere una actualización 
para mejorar la experiencia en el 
desplazamiento del motor.

> Que es un Servo Motor?

Un servo, es un pequeño motor que 
puede colocar su eje en una posición 
deseada y mantener esa posición. 
Las instrucciones al servomotor son 
enviadas en forma de señales PWM.

Donde diferentes ciclos de trabajo 
indican diferentes posiciones la Servo 
motor

`Servo myservo()`

 Es una librería 
orientada a objetos, cada servo a 
controlar debe estar ligado a un 
objeto del tipo Servo.

Cada objeto es independiente.

Sintaxis:

Servo (ID)

ID: Identificador del Servo.

`myservo.attach()`

La rutina attach() debe ser 
invocada con un objeto del tipo 
servo. 

Esta rutina indica en que pin 
de Galileo se encuentra el servo 
motor físicamente.

Sintaxis:

myservo.attach(PIN)

PIN: Terminal a la que se 
encuentra conectado el 
servomotor.

`myservo.write()`

Por medio de esta función se 
indica la posición que el servo 
motor debe de tomar.

Sintaxis:

myservo.write(VALUE)

VALUE: Posición del servo motor

## Código servo.ino

#include <Servo.h>
>Importar la librería Servo.h

int servoPin = 9;

Servo myServo;
>Creación de un objeto de la clase Servo. Igual que en programación 
orientada a objetos

void setup() {

myServo.attach(servoPin);

}
>Asignar el pin 9 al objeto Servo. Todas las operaciones sobre el objeto 
‘myservo’ se reflejaran en el pin 9.

void loop() {

myServo.write(19);
>Envió de señal de control al servo motor para 
asignar una nueva posición.

delay(1000);

myServo.write(180);

delay(1000);












