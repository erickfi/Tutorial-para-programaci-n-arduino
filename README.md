# Tutorial para programación arduino
## Controlar un LCD usando software de programación
### Introducción
Dentro de la electrónica existen muchos controladores y microcontroladores que nos permiten realizar un proceso de forma controlada, entre ellos descata el uso del arduino, esto se debe a que ofrece una mayor disponibilidad de componentes con una programación no tan compleja, no obstante, para personas que no tienen conocimiento de programación utilizar arduino puede significar todo un desafío, por ello surgen diferentes sortware que permiten, por medio de bloques preprogramados, diseñar el circuito y proporcionar el código en caso de que se quiera realizar, de forma física, la simulación.

Ya que existen diversas aplicaciones en los que se puede usar un arduino como microcontrolador, mencionar todas y cada una de ellas resultaría extenso, es por ello que nos centraremos en una de las aplicaciones, que para mi parecer, tiene una aplicación más común, el control de un LCD.
### Objetivos

- Analizar y comprender el funcionamiento de el software visuino para la creación de códigos de arduino con el uso de bloques visuales.
- Crear y diseñar elementos visuales a través del control LCD con el uso de arduino.

### Marco Teórico

Dentro del proceso de control de un LCD existen algunos componentes que se deben conocer, ya que son fundamentales al momento de entender como funciona y como implementar un circuito usando arduino.

#### Arduino
Para las personas que empiezan a involucrarse en el mundo de la electrónica y el control, incluso para quienes llevan un largo período dentro de este campo, usar el Arduino se convierte en una herramienta indispensable. Existen varias definiciones o interpretaciones al momento de referirnos a que es Arduino, sin embargo, la más conocida y aceptada es:

> El arduino es una placa que tiene todos los elementos necesarios para conectar periféricos a las entradas y salidas de un microcontrolador. Es decir, es una placa impresa con los componentes necesarios para que funcione el microcontrolador y su comunicación con un ordenador a través de la comunicación serial.

##### ¿Cómo funciona Arduino?
Anteriormente se habia asociado al arduino con los microcontroladores por lo que su funcionamiento va a ser similar.
- **Cuenta con una interfaz de entrada.** Esta puede estar directamente unida a los periféricos , o conectarse a ellos a través de puertos.
- **La interfaz de entrada** Tiene como objetivo trasladar la información al microcontrolador.
- **El microcontrolador** Es la pieza que se encarga de procesar esos datos. Además, varía dependiendo de las necesidades del proyecto en el que se desee usar la placa, y existe una gran variedad de fabricantes y versiones disponibles.
- **Interfaz de salida.** Este se encarga de llevar la información procesada a los periféricos autorizados de hacer el uso final de esos datos. En algunos casos puede tratarse de otra placa en la que se centraliza y procesa la información de forma totalmente renovada, o sencillamente, puede ser una pantalla o un altavoz encargado de mostrar la versión final de los datos.

Existen diversos tipos de arduino, los cuales varían, no solo en costo sino también en aplicación. El arduino más utilizado es ***arduino uno***

![](https://github.com/erickfi/Simulaci-n-con-Arduino/blob/master/Imgs/Arduino.PNG)

Podemos diferenciar al arduino uno de los demás al observar los componentes que contiene: 

> - Arduino Uno es una placa electrónica basada en el microcontrolador ATmega328.

> - Cuenta con 14 entradas/salidas digitales, de las cuales 6 se pueden utilizar como salidas PWM (Modulación por ancho de pulsos) y otras 6 son entradas analógicas.

> - Incluye un resonador cerámico de 16 MHz, un conector USB, un conector de alimentación, una cabecera ICSP y un botón de reseteado.

##### Descripción general de la placa arduino

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Arduino%201%20partes.PNG)

Siguiendo las manecillas del reloj tenemos:

- Terminal de referencia analógica (naranja).
- Tierra digital (verde claro).
- Terminales digitales 2-13 (verde).
- Terminales digitales 0-1/ E/S serie – TX/RX (verde oscuro), estos pines no se pueden usar como digitales si se está usando comunicación en serie.
- Botón de reinicio – S1 (azul oscuro).
- Programador serie en circuito «In-circuit Serial Programmer» o «ICSP» (azul celeste).
- Terminales de entrada analógica 0-5 (azul claro).
- Terminales de alimentación y tierra (alimentación: naranja, tierras: naranja claro).
- Entrada de alimentación externa (9-12VDC) – X1 (rosa).
- Selector de alimentación externa o por USB SV1 (púrpura).
- USB (utilizado para subir programas a la placa y para comunicaciones serie entre la placa y el ordenador; puede utilizarse como alimentación de la placa) (amarillo).

#### LCD

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/LCD.jpg)

Las siglas LCD significan “Liquid Cristal Display” ó pantalla de cristal líquido. Es una pantalla plana basada en el uso de una sustancia liquida atrapada entre dos placas de vidrio, haciendo pasar por este una corriente eléctrica a una zona especifica, para que así esta se vuelva opaca, y además cuenta (generalmente) con iluminación trasera.

Ya que son componentes de uso común dentro de la electrónica, existe una gran variedad de LCD's, para determinar cuál es la más factible de utilizar se debe tener en cuenta:

- **Resolución:** Las dimensiones horizontal y vertical son expresadas en píxeles. Las pantallas HD tienen una resolucion nativa de 1366 x 768 píxeles (720p) y la resolucion nativa en las Full HD es de 1920 x 1080 píxeles (1080p).
- **Ancho de punto:** La distancia entre los centros de dos píxeles adyacentes. Cuanto menor sea el ancho de punto, tanto menor granularidad tendrá la imagen. El ancho de punto puede ser el mismo en sentido vertical y horizontal, o bien diferente (menos frecuente).
- **Tamaño:** El tamaño de un panel LCD se mide a lo largo de su diagonal, generalmente expresado en pulgadas (coloquialmente llamada área de visualización activa).
- **Tiempo de respuesta:** Es el tiempo que demora un píxel en cambiar de un color a otro.
- **Tipo de matriz:** Activa, pasiva y reactiva.
- **Ángulo de visión:** Es el máximo ángulo en el que un usuario puede mirar el LCD, es estando desplazado de su centro, sin que se pierda calidad de imagen.Las nuevas pantallas vienen con un angulo de vision de 178 grados
- **Soporte de color:** Cantidad de colores soportados. Coloquialmente conocida como gama de colores.
- **Brillo:** La cantidad de luz emitida desde la pantalla; también se conoce como luminosidad
- **Contraste:** La relación entre la intensidad más brillante y la más oscura.
- **Aspecto:** La proporción de la anchura y la altura (por ejemplo, 5:4, 4:3, 16:9 y 16:10).
- **Puertos de entrada:** Por ejemplo DVI, VGA, LVDS o incluso S-Video y HDMI.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Conexion%20arduino%20LCD.PNG)

Las LCD's se conectan al arduino, el cuál dará las instrucciones que la LCD mostrará, está conección se realizá entre pines de ambos componentes, sin embargo, los pines que se conectan dependerán de lo que se quiere presentar en la LCD.

#### Visuino
 ![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/visuino.png)
 
Visuino es el último software innovador de Mitov Software, es una herramienta de programación visual, similar a a Visual Studio pero enfocada a desarrollar para Arduino.
Visuino incorpora bastantes cosas positivas como la preselección de la placa Arduino con la que desarrollaremos, la selección de componentes que cargaremos y la creación del programa según diagramas lo que nos permite ir más rápidos con la creación de nuestros programas. En otras palabras se puede decir que;

> Visuino es un ambiente de programación basado en la tecnología Open Wire, en donde todo es conectado por una serie de diagramas y pines, así consigues tener un diseño de tu circuito electrónico con su correspondiente código para grabarlo en Arduino.

##### Entorno 

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Visuino%20entorno.jpg)

Visuino presenta un entorno cirtual, partiendo desde la posibilidad de elegir la placa de arduino que queremos utilizar, al mismo tiempo presenta una barra lateral de herramientas, donde podemos encontrar prácticamente todos los componentes que podriamos utilizar, dejando a un lado la personalización, finalmente presenta la opción de desplegar el código que se usaría para la tarjeta arduino así como cargarlo y probarlo.

***Nota:*** Para usar al 100 % visualino, y poder bajar el código se debe tener instalado el [IDE de arduino](https://www.arduino.cc/en/main/software).

##### Placas

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/placas.PNG)

Visuino da la oportunidad de elegir la placa con la que queremos trabajar, ofreciendo una amplia gama de placas arduino entre otras, entre ellas encontramos:

- Arduino UNO
- Arduino Nano
- Arduino Pro 168
- Digital Loggers PLDuino
- Lynxmotion BotBoarduino

##### Componentes

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/componentes.PNG)

Visuino cuenta con una gran lista de componentes, enumerarla sería demasiado extenso, estas se agrupan por categorías, entre las cuáles están.

- Matemática
- Medición 
- Memorias
- Motores
- Generadores
- Entradas y salidas (analógicas)
- Integrados
- Fuentes de corriente y voltaje
- Sincronizadores
- Texto
- Controles remotos
- Convertidores
- Display's 
- Código binario
- Componenetes 

##### Barra de componentes

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/barra%20de%20componentes.PNG)

SE desplaza la clasificación de los componenes, cuenta con un buscador, y opciones que modifican esta visualizacón

##### Barra de herramientas

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Barra%20de%20herramientas.PNG)

Se presenta en la parte superior de la interfaz, entre sus opciones de izquierda a derecha están.
- Abrir, cerrar y guardar un documento
- Editar
- Ver
- Arduino, para obtener el y cargar el código
- Ayuda, donde se puede comunicar hasta con los creacdores del software.

##### Visualizador

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/visualizador.PNG)
 Ubicado debajo de la barra de herramientas, muestra el entorno general de la placa y el área sobre la que estamos trabajando.



#### IDE arduino

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Arduino%20IDE.PNG)

Arduino IDE es un editor de texto y compilador para programar y transferir el contenido de las instrucciones a la placa de Arduino en su lenguaje máquina. El lenguaje de programación utilizado es [Processing](https://processing.org/).

#### Tinkercad

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/tinkercad.png)

Tinkercad es una herramienta online gratuita de Autodesk que permite dibujar esquemas de forma similar a Fritzing. Además permite simulación de circuitos, e incluso podemos realizar la “programación virtual” de las placas Arduino y comprobar el funcionamiento, en otras palabras, es un simulador online.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/Tinker%20circuits.PNG)

La parte que nos interesa de tinkercad es la creación de ciruitos, la cuál presenta una interfaz agradable con el usuario, cuenta con una barra lateral izquierda donde se encuentran los componentes que puede requerir, lo único que se debe hacer es arrastrar y soltar.

### Manual de usuario
Se requiere tener instalados los programas presentados, para ello a continuación se presenta los links de descarga.

- [Visuino](https://www.visuino.com/download)
- [IDE arduino](https://www.arduino.cc/en/main/software)
- [Tinkercad](tinkercad.com)

La descarga e instlación de los programas es muy sencillo, solo se debe seguir lo siguiente:
- Descargamos el software desde la sección de descargas de la página.
- Terminada la descarga procedemos a ejecutar el programa, aceptamos la licencia de uso y siguimos los pasos que aparecen en el instalador.

***Nota:*** Tinkercad es un simulador online por lo que no necesita ser descargado para su uso.

---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
## Controlar un LCD usando visuino
Como se mencionó anteriormente arduino presenta una amplía gama de control, si usamos para controlar un LCD, debemos tener en cuenta que es lo que buscamos presentar, ya que dependiendo de esto, el código, o en nuestro caso la configuración del software serán diferentes.

A continuación se presenta la forma de controlar un LCD, conectado a un arduino, con el software visuino para presentar líneas de texto estático.

#### 1. Abrimos el software visuino, en herramientas de la placa elegimos ***arduino uno***
La opción de arduino uno viene por defecto, si no es así se debe elegir la opción, en caso de querer otra placa se debe buscar entre las opciones.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso%201.PNG)

#### 2. En el buscador de componentes escribimos ***lcd***
Al buscar lcd se nos presentan varias opciones elegimos la opción **I2C** del conjunto de ***Text***

Posterior procedemos a conectar la salida del LCD _(out)_ al pin _In_ del canal I2C.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso%202.PNG)

#### 3. Procedemos a agregar los elementos

##### 3.1 Damos click en el símbolo de herramientas del LCD.
Se desplegará un nuevo menú con las diferentes opciones que podemos agregar al LCD.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/PASO%203.1.PNG)

##### 3.2 Agregamos el componente texto
Seleccionamos la opción _Text Field_ del panel izquierdo (flecha azul) y agregamos la función con la opción del panel derecho (flecha roja).

Se puede cambiar el nombre con el que se llamará a este texto, y procederemos a cerrar el menú.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso3.2.PNG)

##### 3.3 Agregamos el mensaje
Seleccionamos el LCD y observamos que el panel inferior izquierdo presenta una serie de opciones.

Nos dirigimos a la opción _Elements_ (flecha roja), y buscamos el nombre que le dimos a nuestra variable de texto (flecha azul), en mi caso _Texto 1_, en la opción _Initial Value_ escribimos el mensaje que queremos presentar, este se presentará en 1 línea si ejecutamos el programa.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso%203.3.PNG)

##### 3.4 Agregar otra línea de texto
Para agregar una segunda linea de texto repetimos el proceso desde el **paso 3.1**, sin embargo, hay algunas variaciones.

Para que el texto se presente en la siguiente linea debemos cambiar dos valores, iniciamos el valor de _column_ (flecha roja) en 3, y cambiamos a 1 el valor de _Row_ (flecha azul)

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso%203.4.PNG)

#### 4. Procedemos a obtener el código
Damos click en el símbolo de arduino de la barra de herramientas de la parte superior (flecha roja), y automáticamente se nos genera el código en una ventana del IDE de arduino.

Si tenemos nuestro arduino conectado para ser usado, damos click en _compilar y cargar_ (flecha azul).

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/paso%204.PNG)

## Simulación en Tinkercad
Tinkercad nos permite simular circuitos y observar lo que ocurriría si los hicieramos en tiempo real, sin embargo, tu software está un poco descontinuado por lo que no tiene todas las opciones disponibles, esto no quiere decir que no se pueda realizar la simulación sino que, hay que hacer algunos ajuste.
### 1. Llamamos al arduino
Tinkercad nos ofrece una serie de arduinos con distintas aplicaciones, o la base para poder desarrollar el nuestro, sin embargo, hay que tener en cuenta que las tarjetas integradas que actualmente tienen los LCD no están en el software, por lo general nos presenta la siguiente opción.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/LCD%20tinkercad.PNG)

### 2. Arreglamos el código
Al elegir el arduino, automáticamente se presenta un código genérico, con algunos comentarios e instrucciones de como modificarlo, eliminando la mayoría de los comentarios el código genérico.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/generico%20tinkercad.PNG)

Para adaptar el mismo circuito a nuestro objetivo y de una forma más simplificada podemos hacerlo con el siguiente código.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/codigo%20corregido.PNG)

### 3. Simular
Al simular en tinkercad, observamos que si realizamos el mismo código en un arduino físico, el LCD nos presentaría.

![](https://github.com/erickfi/Tutorial-para-programaci-n-arduino/blob/master/Imagenes/simulaci%C3%B3n%20tinkercad.PNG)

## Conclusiones

- El arduino en un microcontrolador que nos permite controlar como se desarrolla un circuito.
- Las conexiones en los pines del arduino depende de lo que queremos conseguir.
- Un LCD es una interfaz que se acciona por acción de la corriente en un determinado punto del área.

## Recomendaciones

- Elegir el LCD que mejor se adapte al proceso que se quiera mostrar, para ello tener en cuenta los componentes que tiene, asi como los pines de conexión con el arduino.
- No todos los programas pueden leer códigos desarrollados por terceros, para ello tener en cuenta el cambio que hay que realizar en el código para la simulación.

## Bibliografía
- http://www.iescamp.es/miarduino/2016/01/21/placa-arduino-uno/
- https://www.ecured.cu/LCD_(pantalla_de_cristal_l%C3%ADquido)#:~:text=Una%20pantalla%20LCD%20(liquid%20crystal,fuente%20de%20luz%20o%20reflectora.
- https://www.hwlibre.com/visuino-una-herramienta-de-programacion-para-los-creadores-de-hardware/
- https://www.programoergosum.com/cursos-online/arduino/253-curso-de-iniciacion-a-arduino/software-arduino-ide

## Anexos
- [video tutorial](https://www.youtube.com/watch?v=tOtAcL7KxtQ&feature=youtu.be)
