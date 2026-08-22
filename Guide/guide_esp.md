
<h1 align="Left"> Guía ensamble </h1>

<h2 align="Left"> 1. Materiales Base</h2>

Para poder armar tu propio JK206, sea en su versión de macropad o de teclado 50%, necesitas los siguientes materiales:

|                           | Macropad                                    | Teclado                                     |
| ------------------------- | ------------------------------------------- | ------------------------------------------- |
| Switches mx               | 15 - 20 (dependiendo el número de encoders) | 57 - 60 (dependiendo el número de encoders) |
| Sockets hotswap kailh     | 15 - 20 (dependiendo el número de encoders) | 57 - 60 (dependiendo el número de encoders) |
| Encoders EC11             | 0 - 5                                       | 0 - 3                                       |
| Diodos 1n4148             | 20                                          | 60                                          |
| PCB JK206                 | 1                                           | 3                                           |
| Raspberry Pi Pico         | 1                                           | 1                                           |
| Pantalla OLED SSD1306 (0.91 o 0.96 pulgadas)  | 1 (opcional pero recomendada)               | 1 (opcional pero recomendada)               |
| Case                      | A preferencia                               | A preferencia                               |
| Keycaps                   | A preferencia                               | A preferencia                               |

Mas a continuación hablaremos de los tipos de case y que materiales en particular necesitan estos

Además de lo anterior, para poder realizar el montaje necesitarás de cautín/soldador y estaño, el flux de soldadura es opcional pero nunca viene mal para soldar

<h2 align="Left"> 2. Obtener la PCB </h2>

Para obtener las PCBs basta con tomar el gerber de la PCB (es un .zip) y mandarlo a hacer en una pagina de fabricación de PCBs. Solo hay que tener en cuenta que el número minimo de PCBs que se pueden mandar a hacer generalmente es de 5

<h2 align="Left"> 3. Preparar la PCB </h2>

Una vez tengas todos los materiales necesarios, toca empezar a soldar. Antes de empezar a soldar las piezas ten en cuenta lo siguiente según quieras montar un macropad o un teclado.

<h3 align="Left"> Para el macropad </h3>

Si estas montando el macropad, tienes que "habilitar" la opción de usar mas encoders en la PCB, para esto basta con unir los puntos de la PCB que se ven en la imagen, de forma que cada uno quede unido con quien tenga a sud derecha o izquierda

![guide_01](/assets/images/guide_01.png)

De forma que queden unidos de la siguiente manere

![guide_02](/assets/images/guide_02.png)

Esto se puede hacer tanto con cable UTP como con un jumper o uniendo directamente ambos puntos con estaño, basta con que haya continuidad entre ambos puntos

<h3 align="Left"> Para el teclado </h3>

Si estas montando el teclado, tienes que unir las 3 PCBs, para esto hay que unir filas y columnas; las columnas se unen en la parte superior de las PCBs de la siguiente forma:


![guide_03](/assets/images/guide_03.png)

Las filas se unen puenteando los puntos que se encuentran a los lados de la PCB junto al punto que le quede inmediatamente al lado de la otra PCB. Esto se hace en ambas intersecciones entre PCBs

![guide_04](/assets/images/guide_04.png)

No olvides que para evitar problemas posteriores con el montaje del teclado las 3 PCBs deben quedar completamente juntas y alineadas


<h2 align="Left"> 4. Soldar piezas </h2>

Ya con los preparativos listos, queda soldar los componentes en sus sitios correspondientes. Comienza colocando los diodos, estos van posicionados de forma que la parte que tiene una linea va hacia abajo, como se puede observar en la misma PCB

![guide_05](/assets/images/guide_05.jpg)

Lo siguiente sería soldar los sockets hotswap y los encoders, ten en cuenta que donde vayas a colocar enconders no hay que colocar sockets. Dependiendo de si estás armando un teclado o un macropad debes tener en cuenta las siguientes consideraciones:

<h3 align="Left"> Para el macropad </h3>

Los encoders se pueden colocar en el macropad de la siguiente forma

![guide_06](/assets/images/guide_06.png)

Las zonas verdes en el diagrama representan los puntos donde puenden colocarse los encoders. No es recomendable colocar dos encoders en posiciones que compartan el mismo número, pues por limitaciones del Raspberry Pi Pico y del diseño de la PCB estos serían reconocidos como un solo encoder; por lo que la formas recomendables de colocar los encoders serían las siguientes


![guide_07](/assets/images/guide_07.png)
![guide_08](/assets/images/guide_08.png)

<h3 align="Left"> Para el teclado </h3>

A pesar de tecnicamente poder poner encoders en la pcb de la izquierda en las posiciones 1, 2 y 3 mostradas en la sección anterior. Por cuestiones de usabilidad del teclado se recomienda solo poner un encoder en el extremo superior izquierdo.

Teniendo en cuenta lo anterior, empieza a soldar los sockets hotswap y los encoders que vayas a colocar. Puede que tengas problemas con los sockets, pero si eres generoso con el estaño no habrán mayores dificultades

![guide_09](/assets/images/guide_09.jpg)
![guide_10](/assets/images/guide_10.jpg)
![guide_11](/assets/images/guide_11.jpg)

Ahora solo faltaría soldar el Raspberry Pi Pico y la pantalla OLED. Es necesario que la Raspberry tenga pines soldados para poderla poner en la PCB, así que en caso de que tu Raspberry no los tenga de antemano tendrás que soldarle tu mismo unas regletas Antes de colocarla en la PCB.


![guide_12](/assets/images/guide_12.png)

![guide_13](/assets/images/guide_13.jpg)


En cuanto a la pantalla OLED, su posicionamiento varía dependiendo de cual pantalla vayas a usar. En caso de tener una pantalla rectangular de 0.91 pulgadas esta quedaría sobre la Raspberry, mientras que una pantalla cuadrada de 0.96 pulgadas quedaría a la derecha.

![guide_14](/assets/images/guide_14.jpg)
![guide_15](/assets/images/guide_15.jpg)


Nota: para el montaje del teclado, tanto la Raspberry como la pantalla van únicamente en la PCB de la izquierda. El diseño de la PCB no está pensado para que tomen ninguna otra posición.

<h2 align="Left"> 5. Montaje </h2>

Aquí el proceso cambia según el tipo de montaje que se quiera realizar:

<h3 align="Left"> Para el montaje sandwich-case </h3>

Para este montaje relativamente sencillo vas a necesitar de estos materiales:

|                                   | Macropad                                    | Teclado                                     |
| --------------------------------- | ------------------------------------------- | ------------------------------------------- |
| Separadores de latón M2 8mm      | 4                                         | 4-12                                           |
| Tornillos M2 cabeza plana 5mm     | 8                                        | 8-24                                           |
| Plates acrílicos (preferiblemente 1.5mm de grosor, pero 2 mm también sirve)| [1 par](/Cases/Sandwich-Case/Macropad)              | [1 par](/Cases/Sandwich-Case/Keyboard)        |
|Pies antideslizantes | a gusto | a gusto |

Esta guía de montaje estará enfocada principalmente para el macropad, pero el montaje del JK206 en modo teclado es muy similar y la guía debería servir igualmente.

Para realizar el montaje del teclado o macropado lo primero será tomar el plate inferior y colocarle pies antideslizantes bajo preferencia del usuario.

![guide_16](/assets/images/guide_16.jpg)


Una vez hecho esto seguiría atornillar a éste los separadores

![guide_17](/assets/images/guide_17.jpg)

![guide_18](/assets/images/guide_18.jpg)


Nota: Los plates superior e inferior de la versión de teclado completo del JK206 tienen huecos para 12 separadores, aunque yo recomiendo usar solo 4 (en los espacios siguientes a los mas externos),pero queda la opción de colocar mas separadores si se desea una sensación mas rígida al escribir

Ya teniendo nuestro plate inferior ahora vamos a sujetar nuestra PCB al plate superior con los switches, para esto basta con colocar un par de switches en el plate para luego colocarlos juntos en la PCB

![guide_19](/assets/images/guide_19.jpg)

![guide_20](/assets/images/guide_20.jpg)

Despues de esto quedaría colocar los switches faltantes

![guide_21](/assets/images/guide_21.jpg)

Ya teniendo unidos plate, pcb y switches podemos atornillar el plate superior a los separadores que habíamos colocado anteriormente en el plate inferior

![guide_22](/assets/images/guide_22.jpg)

Y con esto ya tenemos nuestro teclado o macropad listo, solo faltaría colocar keycaps a nuestro gusto y disfrutar.

![guide_23](/assets/images/guide_23.jpg)

<h4 align="Left"> Mods recomendados: </h4>
En general el tape mod y el pe foam funciona bien con el montaje, fuera de eso no hay mucho mas que se pueda hacer.


<h2 align="Left"> 6. Instalación del firmware </h2>

Si quieres la configuración default del teclado o macropad, primero debes descargar el [archivo .uf2 correspondiente](/assets/uf2%20files/). 

Ya con el archivo descargado, debes conectar el teclado o macropad a tu PC mientras mantienes presionado el botón que se encuentra en la parte superior de la Raspberry Pi Pico, de esta forma verás que en tu gestor de archivos hay una nueva unidad de almacenamiento con un nombre similar a RPI-RP. 

Abre la unidad y pega ahí el archivo .uf2 que hayas descargado. La Raspberry Pi Pico debería en ese momento reiniciarse y el teclado o macropad ahora estaría funcionando.

Y con ésto ya deberías tener completamente funcional tu JK206 :D
