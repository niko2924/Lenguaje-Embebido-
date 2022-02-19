## MÓDULOS DE COMUNICACIÓN
![Texto alternativo](https://i0.wp.com/www.zonamaker.com/images/contenido/impresora_3d/crea_impresora/3_electronica_imp/esquema_impresora.jpg)

Los  datos transmitidos por el puerto  serial pueden ser sometidos  aun formato de transmisión. Mas información en Arduino LanguageReference.
 una de  las impresoras  que se puede conectar con andruino  son  las computadoras  en 3D  con el andruino es mas  facil  armar una impresora 3D ya que esta lleva  cómo usa los periféricos usados (motores, display, botones, etc…).

Serial.begin() y el Serial.print() y su codificación detallamos a continuación 
## Serial.begin()
Rutina
para abrir el puerto serial
Junto a la apertura del puerto se
debe de definir la velocidad de
transmisión de datos.

### Sintaxis :

Serial.begin(SPEED)

SPEED: Velocidad en bits por
segundo.
## Serial.print
Esta rutina da inicio a la
transmisión de caracteres a través
del puerto serial.

### Sintaxis :
Serial.print
(VALOR)

VALOR:
cualquier tipo de dato,
desde cadenas hasta caracteres.

Aparte  de estos  codigos  va ya la programacion  para ello  se necesita una linea de codigo 

### blinkSerial.ino
Inicializa el puerto serial con una velocidad de transmisión de 9600 bits por
segundo. a continuacion se dara un extrato de la programacion:


int
led 13;

void
setup()
{

pinMode
(led OUTPUT);

Serial.begin
(9600) <-- Inicializa el puerto serial con una velocidad de transmisión de 9600 bits por
segundo.

}

void
loop() {

Serial.print
("ALTO/n");

digitalWrite
(led,HIGH);

delay
(1000);

Serial.println
("BAJO"); <-- El uso de
Serial.println () nos ahorra la necesidad de
cadena enviada.
incluir el carácter de retorno de línea (“ \n”) en cada

digitalWrite
led LOW(led;low);

delay
(1000);

}

## ENTRADA DE COMUNICACION SERIAL

![Texto alternativo](https://3.bp.blogspot.com/-5n--UZFuAxM/WW7jPz0eIJI/AAAAAAAABEU/oTHSQ--e02ECHtaqxkUUtY91Zid74w5NwCLcBGAs/s1600/96.png)

comunicación serial puede ser utilizada para adquisición de datos, control, depuración de código, etc. El concepto de comunicación serial permite la transmisión- recepción bit a bit de un byte completo, este método de comunicación puede alcanzar mayores distancias.

Este puerto es Full Duplex por lo que puede enviar y recibir
información al mismo tiempo, comportándose entonces como una
terminal de Entrada/Salida para lo cual  se utiuliza  dos  a 3 comandos  principales  que a continuacion se describre cada uno  y su sintaxis
### Serial.begin
Inicializa
el puerto serial de Galileo
y define el « baud rate » (Velocidad
de transmisión de datos).
### Sintaxis:
Serial.begin
(speed)
speed
--> Baud Rate
### Serial.available
Esta
función devuelve el numero
de bytes disponibles para ser
leidos en el puerto serial
### Sintaxis 
Serial.available()

### Serial.read
Lee los datos que entran en el
puerto serial.
Regresa
1 si no hay datos
disponibles.

### Sintaxis:
Serial.read().

Estos son los   principales  comandos  que se utilizan para la comunicacion a continuacion  se presentara  un ejemplo de la programacion  aplicando los comandos:

int
ledPin 13;

char
inByte 0; <--- Variable que recibirá el byte
de entrada en el puerto serial

void
setup( )  {

 Serial
begin (9600); <--- Inicializa el puerto serial con una velocidad de transmisión de 9600 bits por
segundo.

pinMode
(ledPin OUTPUT);

digitalWrite
(ledPin LOW) <---- La terminal 13 se
configura como salida.

} 

void
loop( ) {

if
(Serial.available()> 0) { <--- Se comprueba que existan
datos disponibles para su
lectura en el puerto serial

inByte =
Serial read( ); <---- Lectura del dato entrante en
el puerto serial

if(inByte ==== 'a') {

if(digitalRead(ledPin)) {
    
digitalWrite (ledPin,LOW) ; <----Encendido y apagado del LED.

}
else { 
digitalWrite(ledPin HIGH);<--- Encendido y apagado del LED.

}

}

}

} 

##  Teclado Matricial
![Texto alternativo](https://importienda.com/64-large_default/teclado-matricial-4x4-de-membrana-con-adhesivo-.jpg)

Estos
teclados matriciales están conformados por filas y
columnas, un teclado matricial de 4 × 4 tiene 4 filas y 4
columnas interconectadas entre si y si cada
intersección representaría un pulsador se tendría 16
pulsadores interconectados entre sí
## como funciona el teclado Matricial 
![Texto alternativo](https://www.prometec.net/wp-content/uploads/2014/10/Img_19_2-300x273.jpg)

Los teclados matriciales usan una combinación de filas y columnas para conocer el estado de los botones. Cada tecla es un pulsador conectado a una fila y a una columna. Cuando se pulsa una de las teclas, se cierra una conexión única entre una fila y una columna.

Vamos a ver un ejemplo con un pequeño teclado numérico de 16 teclas tipo los de los teléfonos móviles o los de los cajeros automáticos.
![Texto alternativo](https://www.prometec.net/wp-content/uploads/2014/10/matrix-keypad-300x244.jpg)

Lo más práctico es conectar el teclado a Arduino directamente, podemos usar cables de protoboard, o bien con un peine de pines para que no se suelte nada.
![Texto alternativo](https://www.prometec.net/wp-content/uploads/2014/10/Img_19_3.jpg)
  Antes de  poner en practica   diremos el problema  mas comun  al programar el keypad para que lo reconosca el andruino y este  es el dolor de cabeza  pero aqui daremos una breve  explicacion de como sulucionarlo 

  Lo primero es descargar la librería e instalarla. 
  es  ir a la sección de “Download, install and import” donde encontrareis keypad.zip. Descargadlo y para instalarla recordad que basta con hacer:

  ![Texto alternativo](https://www.prometec.net/wp-content/uploads/2014/10/IMg_19_4.jpg)

  o puede ir  a descargar  el codigo  de la pagina  oficial del andruino el cual encontramos en el siguiente enlace

  https://www.prometec.net/wp-content/uploads/2014/10/IMg_19_4.jpg

  a continuacion  se dara un ejemplo  de progamacion con el codigo keypad.ino :

  #include < Keypad.h> <--- Libreria de keypad

const byte ROWS = 4;  // FILAS

const byte COLS = 4;  // COLUMNAS

char keys[ROWS][COLS] = { <---Inicializar filas y columnas

{'7','8','9','*'},

{'4','5','6','*'},
                    <-----Creación de la matriz
{'1','2','3','-'},

{'#','0','=','+'}

};

byte
rowPins [ROWS] = {5, 4, 3, 2} ;

byte
colPins [COLS] = {9,8, 7, 6} ;

Keypad
keypad = Keypad( makeKeymap (keys), rowPins,
                                              <-----Orientación de pines y llamada de
librería
colPins , ROWS, COLS)

void setup( ) {
    Serial.begin (9600) ;

}

void loop() {

  charkey = keypad.getKey( );

if(key)

{

Serial.println(key) ;

}

}