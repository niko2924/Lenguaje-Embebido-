### Arduino

- Definicion de Arduino:

Es una aplicación  que permite programar diversas placas de desarrollo Arduino: Arduino UNO, Arduino MEGA, Arduino DUO, además, este software tiene plugins (módulos adicionales) que permiten programar otro tipo de placas de desarrollo. 

![Image text](https://www.ticarte.com/sites/su/styles/large/public/users/380/teaser/arduino-logosvg.png?itok=OemPVURn)

### Partes de Arduino 

![Image text](https://aprendiendoarduino.files.wordpress.com/2015/03/instalacion6.png?w=625&h=526)

1.	Barra de Navegación=> Permite al usuario acceder a Programas.
2.	Cuadro de Trabajo=>	Donde programa Arduino.
3.	Cuadro de Compilación=>	Proceso de compilación y ubicación del archivo .hex
4.	Barra de acceso=>	Permite compilar y cargar el código.
5.	Barra de Ubicación=>	Tipo de Arduino conectado y el puerto de comunicación.


### Partes del steck 

1.	Descripción del programa: Para reutilización de código, es necesario presentar una breve descripción del programa y su funcionalidad . 
2.	 Librerías : Son líneas de código ya construidas para el uso de ciertos aspectos de Arduino para una mayor facilidad y se llaman a estos subprogramas como métodos o subrutinas.
3.	Variables : Es un espacio de memoria donde se almacenan datos, se forma temporal o fija, dependiendo del tipo de dato se debe elegir la variable a usar, además de ellos es necesario primero declarar la variable con un nombre que la represente, pero si puede tener varios datos contenidos en una misma variable . 
4.	 Void Setup : Es el lugar donde configuramos al Arduino sobre que pines y como vamos a usar, en cada tema de programación observamos la forma de configurar correctamente .
5.	 Void Loop : Es un espacio de programa que se repetirá infinitas veces hasta que alguna variable cambie de estado o se desconecte de la fuente, es donde irá el programa que dará el accionamiento al Arduino . 
6.	 Void rutina : Rutinas de programación fuera del programa principal


### Entrada-Salidas 
Digitales de Proposito general

* Las placas de arduino tienen 14
terminales de salida digital de
propósito general. Cada terminal
esta representada por un
identificador numérico.
Este identificador es utilizado para
utilizar cada una de las terminales
durante la programación del
dispositivo.


### MANEJO DE VARIABLES DE NÚMEROS 
 
 * Las variables son espacios de memoria del micro
para almacenar datos temporales y que en el
tiempo de ejecución cambia de valor.

1. int           => Tipo de Dato 
2. led           => Nombre de la Variable 
3. =8            => Asignación del Valor 
4. ;             => Fin de Linea de Codigo


### MANEJO DE CONSTANTES

No cambian su valor en tiempo de ejecución. Son
útiles para prevenir que no se tenga errores.

#define

* Ventajas

No ocupa memoria para almacenar las constantes,
puesto que son remplazadas por sus valores
Si se usa en proyecto pequeños, como definir un
pin, una cadena, etcétera, es adecuado.

* Desventajas

No tienen tipo. Por lo que el compilador no podrá
avisar si algo esta mal
Son globales, por lo que se debe ser sumamente
cuidadosos al referirse a ellas.

### MANEJO DE CONSTANTES

Const

* Ventajas
Obedecen el ámbito de las funciones. Es
decir, se puede declarar dos constantes
con el mismo nombre en
diferentes funciones
También tiene la ventaja de que tiene tipo,
por lo que el compilador nos informará los
errores que puede que estemos
cometiendo.
const también permite declarar arreglos,
que #define no



### Bibliotecas de Arduino


* pinMode() 

Al hacer una llama a la rutina pinMode se le deja saber a Arduino si una terminal será utilizada como entrada o salida.

Sintaxis: pinMode(pin, MODO) 

MODO: INPUT o OUTPUT.

* digitalWrite() 

Una vez que se a especificado que una terminal de Arduino será utilizada como salida, se usa esta función para escribir un valor digital alto o bajo a dicha terminal.

 Sintaxis: digitalWrite(pin, ESTADO) 

ESTADO: HIGH o LOW.

* delay()

 Rutina de retardo universal, detiene el flujo de ejecución del sketch actual. 

Sintaxis: delay(ms) 

ms: numero de milisegundos a esperar. (1000 ms = 1 ).


* digitalRead() 

Después de especificar que una terminal se usará como entrada, se emplea esta función para leer un valor digital alto o bajo presente en dicha terminal. 

Sintaxis: digitalRead(pin)                                 pin -> Número de terminal a leer

* pullUP pullDown

Se consideran entradas digitales en el momento que nosotros recibimos 0 lógico o 1 lógico del exterior, sea desde un sensor, un switch, un botón, etc. 0 lógico : 0 voltios y 1,8 voltios 1 lógico: 2,1 voltios y 5 voltios


![Image text](https://www.arduino.cc/en/uploads/Guide/mkrfox_board.jpg)


### TIPOS DE LENGUAJE D PROGRAMCION 


### LENGUAJE DE PROGRAMACIÓN DE BAJO NIVEL

* Lenguaje máquina: 	 Es una colección de dígitos binarios o bits (0,1) que la computadora lee e interpreta.
Ejemplo: 1011000001100001



* Lenguaje ensamblador: 	Es un lenguaje donde genera códigos compactos, rápidos y eficientes.
Ejemplo: MOV AL,61h






### LENGUAJE DE PROGRAMACION DE ALTO NIVEL



* Traductor:	Traducen programas escritos en un lenguaje de programación al lenguaje máquina de la computadora.

* Compilador: 	Permite traducir todo un programa d e una sola vez, haciendo ejecución mas rápida y puede almacenarse para usarse luego. 