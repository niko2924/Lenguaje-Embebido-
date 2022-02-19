### Memoria EEprom

Es una memoria no volátil que dispone el microcontrolador de Arduino que
nos permite guardar datos para poder recuperar en caso de pérdida de alimentación de nuestro dispositivo.
La gran desventaja que tiene la EEPROM es que tiene un número limitado de escrituras, por lo que debemos calcular cuántas veces se va a escribir en ella para calcular su vida útil con nuestro programa.

![Esta es una imagen de ejemplo](https://upload.wikimedia.org/wikipedia/commons/0/00/Silicon_Storage_Technology_39VF512.png))
### Libreria 


**EEPROM.read()**

 >Lee un byte de la posición de memoria que indica su parámetro. De fábrica, todas las posiciones de
memoria tienen escrito el valor 255.

*Sintaxis:
*EEPROM.read(dirección)
*Dirección: 0-1023

**EEPROM.write()**

  > Esta función escribe un byte en la posición indicada de la EEPROM.


Sintaxis:
EEPROM.write(dir, valor)
Dir: Dirección de memoria 0-1023
Valor: Valor a escribir

**EEPROM.update()**

> Escribe un byte en la EEPROM. El valor es escrito solo si es diferente al valor que esta previamente almacenado en esa posición de memoria

Sintaxis:
EEPROM.update(dir,val)
Dir: Dirección de memoria 0-1023
Val: Valor a escribir

**EEPROM.put()**

> Esta función escribe cualquier tipo de dato en la EEPROM. El valor es escrito solo si es diferente al valor que esta previamente almacenado
en esa posición de memoria, por lo que es mucho más versátil.

Sintaxis:
EEPROM.put(dir, valor)
Dir: Dirección de memoria 0-1023
Valor: Valor a escribir

**EEPROM.get()**

> Permite leer cualquier tipo de dato
en la EEPROM..


Sintaxis:
EEPROM.get(dir, valor)
Dir: Dirección de memoria 0-1023
Valor: nombre de variable para
guardar el dato

**Operador EEPROM[ ]**

> Este operador permite usar el identificador EEPROM[] como una matriz en la cual indicamos la
dirección.

Sintaxis:
EEPROM[dirección]
dirección: dirección en la memoria
(0 a 1023)

