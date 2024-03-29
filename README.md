# Apuntes de Python 3

Por Rober J


## 👩‍💻 Scripts

<details>
  <summary><strong>Ejemplos de código</strong></summary><br>
https://github.com/roberer/Python-Apuntes/tree/main/scripts
  
</details>

## 🐍 Introducción

<details>
  <summary><strong>Comenzar con Python</strong></summary><br>
  
<p>Este lenguaje aplicado a los Sistemas de Información Geográfica (SIG) se usa fundamentalmente para <strong>automatizar procesos o crear los nuestros propios</strong> en forma de <strong>scripts</strong> (pequeños códigos o programas). Por ejemplo, si quieres llevar a cabo una serie de operaciones de control de calidad (corrección de geometrías, control de atributos...) y cada una se ejecuta siempre bajo los mismos parámetros, podrías construir un script que realice todas esas operaciones para un conjunto de datos en vez de ir haciéndolo capa por capa.</p>
<p>Con estos scripts podremos <strong>crear plugins (QGIS) o add-ins (ArcGIS) que les aporten una interfaz gráfica</strong> para configurar los parámetros con los que trabajará dicho script según nuestras necesidades: las capas de entrada, los valores a calcular, la clase de resultado que queremos obtener y dónde almacenarlo...  </p>
<p>Podéis echar un vistazo a la clase de plugins que pueden crearse con Python explorando el <a rel="noreferrer noopener" href="https://plugins.qgis.org/plugins/" target="_blank">repositorio de plugins Python para QGIS</a> o el <a rel="noreferrer noopener" href="http://codesharing.arcgis.com/" target="_blank">repositorio de scripts de ArcGIS</a>.  </p>
<p>Y si queréis probar el código sin descargar nada antes, existen <a rel="noreferrer noopener" href="https://repl.it/languages/python3" target="_blank">consolas de Python online como esta</a> donde trastear libremente, con ciertas limitaciones por supuesto. </p>
<p>Si no, se pueden usar las consolas que vienen integradas en cada SIG   de escritorio o programas externos denominados Entorno de Desarrollo Integrado (IDE) para programar más cómodamente (las consolas de los SIG suelen estar algo limitadas). Entre los IDE más populares están Visual Estudio Code o PyCharm, y tan solo habrá que <a rel="noreferrer noopener" href="https://remot-technologies.com/configurar-pyqgis-y-vs-code/" target="_blank">configurarlos</a> para comenzar a programar en ellos. </p>
<p>⚠ Este post trata sobre los aspectos básicos de Python en su <strong>versión 3.x</strong> (Python3), utilizada por QGIS a partir de su versión 3. Sin embargo, QGIS en sus versiones 2.x y ArcGIS utilizan la versión 2 de Python. </p>
<br></details>
<details> 
  <summary><strong>Métodos y funciones</strong></summary><br>
<p>Una <strong>función</strong> es un código que se ejecuta al escribir su nombre y rellenar sus parámetros, haciendo que se lleven a cabo las operaciones de de dicho código. Las funciones se pueden tanto crear desde 0 como usar las que trae Python por defecto o las de sus librerías y/o módulos. </p>
<p>Para usar una variable basta con escribirla y rellenar sus parámetros. Por ejemplo, la función print() hace que se muestre aquello que está dentro de los paréntesis:</p>
<pre >print(5)
> 5
print('Geografía')
> Geografía</pre>
<p>Los <strong>métodos</strong> son <strong>funciones específicas para variables de una clase concreta</strong>, es decir, las variables u objetos de tipo numérico tendrán unos métodos distintos a los de texto o listas debido a su distinta naturaleza.</p>
<p>La forma de <strong>usar un método</strong> es 'llamar' a una <strong>variable de clase compatible</strong> con el método y, si fuera necesario, completar los argumentos necesarios para que pueda llevarse a cabo:</p>
<pre >variable.método(argumentos)</pre>
<h3><strong>Crear funciones</strong></h3>
<p>Es posible crear nuestras propias funciones en Python para no tener que repetir constantemente un código. Con ellas obtendremos el resultado de un cálculo que nosotros diseñemos para unos valores de entrada.</p>
<p>Por ejemplo, la siguiente función nos devolverá la media para dos valores de entrada:</p>
<pre >def media(x,y):
    resultado = (x + y)/2
    return resultado</pre>
<p>Con print() podemos ver cuál es el resultado de aplicar esta función a los valores 8 y 14:</p>
<pre >print(media(8,14))
> 11.0</pre>
<p><strong>Dentro de una función existen varias partes:</strong></p>
<ul><li>Cabecera - da nombre a la función (media) y establece los parámetros que se van a usar</li><li>Cuerpo - realiza operaciones con los parámetros definidos en la cabecera y devuelve un resultado mediante <em>return</em></li><li>Llamada - es la invocación de la función al usar su nombre e introducir parámetros reales</li></ul>
<p>Nuestra función podrá tener <strong>tantos argumentos como queramos</strong>, así como podrá crear variables que funcionen solo dentro de esa función, denominadas <strong>variables locales</strong> (las variables que funcionan para todo el programa se llaman <strong>variables globales</strong>)</p>
  
<br></details>
<details>
  <summary><strong>Clases y variables</strong></summary><br>
  
<p>Las <strong>variables </strong>en Python son un tipo de objeto en  los que se almacena un valor o conjunto de valores. Dependiendo de la <strong>clase </strong>o tipo de dato que almacene, la variable será de una clase u otra.</p>
<p>Las variables <strong>las creamos nosotros</strong> para almacenar algún tipo de información, dándoles el nombre que queramos y escribiendo el valor que queramos almacenar detrás del símbolo de igualdad:</p>
<pre >coord_x = 19
coord_y = -99
poblacion = 'Ciudad de México'
lugar = 'Mercado de San Camilito'</pre>
<p>La <strong>clase </strong>a la que pertenezca la variable dependerá del valor que almacenen:</p>
<ul><li>Las variables <em>coord </em>son de clase <em>int </em>o entero porque almacenan números enteros</li><li>Las variables <em>lugar </em>son de clase <em>str</em> porque almacenan cadenas de texto</li></ul>
<p>Podemos <strong>comprobarlo</strong> usando la función type() :</p>
<pre >print(type(coord_x))
> &lt;class 'int'>
print(type(coord_y))
> &lt;class 'int'>
print(type(poblacion))
> &lt;class 'str'>
print(type(lugar))
> &lt;class 'str'></pre>
<p>Usando print() podemos <strong>visualizar las variables</strong>. Para imprimir varias a la vez basta con separarlas por comas:</p>
<pre >print(poblacion)
> Ciudad de México
print(coord_x , coord_y)
> 19
 -99</pre>
<p>Las variables son usadas para <strong>operar con los valores que almacenan</strong>:</p>
<pre >numero1 = 5
numero2 = 3
print(numero1 + numero2)
> 8</pre>
<p>Podemos <strong>modificar el valor de las variables</strong> siempre que queramos usando su nombre y guardando otro valor, sea del tipo que sea.</p>
<pre >mi_objeto = 5
mi_objeto = 'Cinco'
print(mi_objeto)
> Cinco</pre>
<p>Así como podemos <strong>intercambiar el valor de dos variables</strong>:</p>
<pre >A = 5
B = 10
A,B = B,A
print(A)
> 10</pre>
<p>También podemos <strong>borrarlas </strong>usando <em><strong>del</strong></em>:</p>
<pre >del mi_objeto</pre>
<p>⚠ En Python 2 para imprimir un resultado no es necesario hacer uso de los paréntesis. Basta con escribir <em>print </em>seguido de aquello que se quería imprimir. Esto es porque en Python 3 <em>print </em>pasó a considerarse una función y son siempre obligatorias. En Python 2 también funcionará si usamos los paréntesis. </p>
  
<br></details>

## 🧮 Datos 

<details>
  <summary><strong>Números</strong></summary><br>
 
<p>Los números no debe entrecomillarse, pues si no los tomará como si fuesen texto y no podrán usarse para hacer operaciones. Python puede usarse como una calculadora:</p>
<pre >print(5*3)
> 15
print('5*3')
> 5*3</pre>
<p>Hay <strong>dos tipos</strong> básicos de números que pueden almacenarse en Python: enteros o<strong> integer (int)</strong> y decimales o <strong>flotantes (float)</strong>:</p>
<pre >numero1 = 24
numero2 = 24.0
print(type(numero1))
> &lt;class 'int'>
print(type(numero2))
> &lt;class 'float'></pre>
<p>Si se hacen <strong>operaciones entre enteros y decimales</strong> el resultado pasará a ser de tipo decimal:</p>
<pre >print(3.7 + 3)
> 6.7
print(5/3)
> 1.6666666666666667</pre>
<p>⚠ En Python 2 las divisiones cuyo resultado es un decimal (como 5 entre 3) devuelven solo el número entero (5 entre 3 devolvería 1) Sin embargo, si en vez de dividir dos enteros convertimos uno de ellos en decimal (5.0 entre 3) entonces sí se devolvería el resultado con sus decimales. Esto es porque Python 3 convierte los valores automáticamente. En cualquier caso, al combinar enteros y decimales en una operación el resultado siempre será un decimal.</p>
<p>Python cuenta con una librería muy útil para <a href="https://docs.python.org/3/library/math.html">hacer toda clase de operaciones numéricas llamada <em><strong>math</strong></em></a> que, por lo general, <strong>es más precisa que las operaciones con operadores básicos.</strong></p>
  
<br></details>
<details>
  <summary><strong>Texto</strong></summary><br>
 
<p>El texto o también llamado <strong>cadenas (string)</strong> debe escribirse entrecomillado, ya sean comillas simples o dobles:</p>
<pre >print(hola)
> NameError: name 'hola' is not defined
print('hola')
> hola</pre>
<p>¿Por qué? Porque el texto sin comillas se reserva para nombrar las variables u objetos en las que almacenamos los valores.</p>
<h4><strong>Operar con el texto</strong></h4>
<p>Podemos <strong>operar </strong>con el texto <strong>concatenando </strong>cadenas:</p>
<pre >poblacion = 'Ciudad de México'
lugar = 'Mercado de San Camilito'
print(poblacion + ' - ' + lugar)
> Ciudad de México - Mercado de San Camilito</pre>
<p>Podemos <strong>concatenarlas varias veces</strong> usando el multiplicador. Cada caracter entrecomillado cuenta, por lo que tendremos que añadir nosotros los espacios y las comas para que la concatenación resulte legible:</p>
<pre >print((poblacion + ' - ' + lugar + ', ') * 5)
> Ciudad de México - Mercado de San Camilito, Ciudad de México - Mercado de San Camilito, Ciudad de México - Mercado de San Camilito, Ciudad de México - Mercado de San Camilito, Ciudad de México - Mercado de San Camilito,</pre>
<p>También podremos <strong>convertir una cadena a una lista</strong> con cada palabra usando el método .split() , en el que tendremos que indicar el separador existente entre cada palabra, en este caso, el espacio:</p>
<pre >PrograMapa = 'Cartografía y SIG'
print(PrograMapa.split(' '))
> ['Cartografía', 'y', 'SIG']</pre>
<p>Si queremos <strong>averiguar la longitud</strong> de una cadena habrá que usar len(), que devolverá un valor entero:</p>
<pre >print(len('PrograMapa'))
> 10</pre>
<p>También podemos averiguar si una cadena <strong>acaba con los caracteres que indiquemos</strong> usando <em>.endswith()</em>, muy útil si queremos comprobar extensiones de archivos:</p>
<pre >archivo = 'micapa.shp'
print(text.endswith('.gpkg'))
> False</pre>
<p>También es posible <strong>realizar operaciones con las mayúsculas y minúsculas</strong> de un texto:</p>
<pre >SIG = 'sistemas de Informacion GEOGRAFICA'
# Poner en minuscula
print(SIG.lower())
> sistemas de informacion geografica
## Poner todo en mayuscula
print(SIG.upper())
> SISTEMAS DE INFORMACION GEOGRAFICA
## Poner en mayuscula solo la primera letra de cada palabra:
print(SIG.title())
> Sistemas De Informacion Geografica
## Invertir mayusculas y minusculas
print(SIG.swapcase())
> SISTEMAS DE iNFORMACION geografica</pre>
<p>Otra interesante operación es la de <strong>invertir los caracteres</strong> de una cadena:</p>
<pre >palabra = 'SIG'
alreves = palabra[::-1]
print(alreves)
> 'GIS'</pre>
<h4><strong>Posiciones y subcadenas</strong></h4>
<p>Podemos acceder a los distintos caracteres que conforman nuestro texto o cadenas a través de la posición que estos ocupan dentro de ella indicándola entre corchetes [].</p>
<p>Hay que tener en cuenta que las posiciones comienzan desde el índice de posición 0, por lo que si nuestra cadena tiene por ejemplo 11 caracteres la última posición será la 10:</p>
<pre >cartografia = 'Mapas'
print(cartografia[0])
> M
print(cartografia[4])
> s</pre>
<p>Si quisiéramos contar desde el final usaríamos el índice de posición -1 y contaríamos hacia abajo:</p>
<img src="https://programapa.files.wordpress.com/2021/04/substrings.png?w=413"><figcaption><em>Fuente: http://www.nltk.org/book/ch03.html</em></figcaption></figure></div>
<p>Pueden usarse <strong>rangos </strong>para extraer conjuntos de caracteres llamados <strong>subcadenas</strong>. El rango seleccionará desde el primer caracter indicado (dejar en blanco para empezar desde el principio) hasta el caracter anterior al de la posición indicada: </p>
<pre >mapas = 'Cartografia'
print(mapas[:5])
> Carto
print(mapas[5:11])
> grafía</pre>
  
<br></details>

<details>
  <summary><strong>Listas y tuplas</strong></summary><br>
 
  
<p>La clase lista o <em>list </em>son un tipo de objeto que almacena una colección de valores. </p>
<p>A esta clase pertenecen tanto las listas como las tuplas. La <strong>diferencia entre ellas está en que las listas pueden modificarse y las tuplas no</strong>, haciendo que las listas sean más flexibles pero ocupen más memoria (acceder es más lento) que las segundas.</p>
<p>Las listas se guardan entre corchetes [] y las tuplas entre paréntesis (), separando los valores usando comas:</p>
<pre >una_tupla = ('coordenadas', -45.8, 58)
una_lista = ['coordenadas', -45.8, 58]
print(una_lista)
> ['coordenadas', -45.8, 58]
print(una_tupla)
> ('coordenadas', -45.8, 58)</pre>
<p>Una misma lista o tupla puede almacenar valores de distinto tipo (texto, enteros, floats...) incluyendo objetos que guarden valores, cada uno ocupando una <strong>posición </strong>dentro de ella que podemos usar para acceder a dicho valor. <strong>Los índices de posición son los mismos que en las cadenas</strong>:</p>
<pre >print(una_lista[0])
> coordenadas</pre>
<p>Para <strong>modificar un valor de una lista</strong> (hacerlo con una tupla daría error), basta con indicar la posición que queremos modificar y asignarle un nuevo valor:</p>
<pre >coordenadas = [23.45, 37.01]
coordenadas[1] = 38
print(coordenadas)
> [23.45, 38]</pre>
<p>Para añadir nuevos elementos, eliminarlos, ordenarlos u otras operaciones tendremos que usar los métodos de lista:</p>
<h4><strong>Métodos y funciones de lista</strong></h4>
<figure><table><tbody><tr><td>lista.append(valor)</td><td><strong>Añade un valor</strong> al final de una lista</td></tr><tr><td>lista.extend(lista2)</td><td>Extiende la lista <strong>añadiendo </strong>los elementos de una <strong>segunda lista</strong></td></tr><tr><td>lista.insert(posición, variable)</td><td><strong>Inserta </strong>una variable en la posición indicada de la lista.</td></tr><tr><td>lista.remove(valor)</td><td><strong>Elimina</strong> el primer elemento de la lista cuyo valor es el indicado. Si nada en la lista tiene ese valor se produce un error.</td></tr><tr><td>lista.pop(posición)</td><td>Devuelve y <strong>elimina</strong> el elemento que se encuentre en la posición indicada. Si no se especifica una posición, lo hará de manera predeterminada con el último elemento de la lista.</td></tr><tr><td>del lista[posicion/rango]</td><td>Además de <strong>eliminar</strong> elementos por su posición, con <em>del</em> podemos eliminar elementos que se encuentren en un rango de posiciones que especificamos. Si establecemos el rango [:] se vaciará la lista sin borrarla.</td></tr><tr><td>lista.index(valor)</td><td>Devuelve el <strong>índice de posición</strong> del primer elemento de la lista cuyo valor coincida con el indicado. Si ningún elemento tiene ese valor, producirá error.</td></tr><tr><td>lista.count(valor)</td><td>Devuelve el <strong>número de veces</strong> que aparece el valor indicado en la lista</td></tr><tr><td>lista.sort( )</td><td>Si la lista está compuesta solo por números, esta se modificará para que estén <strong>ordenados</strong> de forma ascendente</td></tr><tr><td>sorted(lista)</td><td>Crea una <strong>nueva lista ordenando los valores</strong> numéricos de menor a mayor de la lista original</td></tr><tr><td>lista.reverse( )</td><td><strong>Invierte </strong>permanentemente el orden de los elementos de la lista</td></tr><tr><td>lista[-5:]+lista[:-5] </td><td><strong>Rota </strong>los elementos de una lista 5 posiciones hacia arriba </td></tr><tr><td>print(max(set(lista), key=lista.count))</td><td>Obtener el <strong>valor más repetido</strong> en una lista</td></tr><tr><td>lista = [x + 1 for x in range(10)]</td><td>Se pueden <strong>usar expresiones</strong> para rellenar de valores una lista nueva. En este caso la lista almacenará valores del 1 al 10 de uno en uno.</td></tr></tbody></table></figure>
  
<br></details>
<details>
  <summary><strong>Booleanos</strong></summary><br>
 
<p>La clase booleano o bool consiste en valores TRUE o FALSE resultado de comprobar si algo es verdadero o falso. Funciona tanto con números como con cadenas de texto:</p>
<pre >> print(4 == 5)
False
> print('satélite' == 'satélite')
True
</pre>
<p>En este caso se ha usado el operador de igualdad == para comprobar si dos valores son iguales o no.</p>
<p>Los booleanos son utilizados sobre todo en las <a href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/#estructuras_de_control">estructuras de control</a> para que se ejecuten unas funciones u otras según si se cumple o no una condición.</p>
<p>Los booleanos <strong>pueden ser tratados como valores enteros</strong>, en los que TRUE es 1 y FALSE es 0. Por ejemplo, pueden usarse para seleccionar los índices de posición 0 y 1 de una lista:</p>
<pre >SIG = ['AutoCAD','QGIS']
print(SIG[False])
> 'AutoCAD'
print(SIG[True])
> 'QGIS'</pre>
  
  
<br></details>
<details>
  <summary><strong>Convertir variables</strong></summary><br>
 
  
<p>Existen funciones para transformar una variable de una clase en otra para evitar errores. Hay conversiones que no se pueden hacer, como convertir un texto en número, pero sí podemos convertir por ejemplo números en cadenas:</p>
<h3><strong>Números a cadenas - función str()</strong></h3>
<p>Convierte <strong>tanto enteros como floats</strong> en cadenas:</p>
<pre >numero = str(5)
print(type(numero))
> &lt;class 'str'></pre>
<h3 ><strong>Floats a enteros - función int()</strong></h3>
<p>Elimina los decimales <strong>sin redondear</strong> para quedarse solo con el entero:</p>
<pre >numero = int(5.7)
print(numero)
> 5
print(type(numero))
> &lt;class 'int'></pre>
<h3 ><strong>Enteros a floats - función float()</strong></h3>
<p>Añade a un número entero el .0 para convertirlo en decimal:</p>
<pre >numero = float(5)
print(numero)
> 5.0
print(type(numero))
> &lt;class 'float'></pre>
  
<br></details>

## ⚙️ Estructuras de control 

<details>
  <summary><strong>Estructuras if-else </strong></summary><br>
 
  
<p>Las estructuras condicionales ejecutan un código u otro en función de si se cumple una condición o no:</p>
<h4><strong>If</strong></h4>
<p>Hace que se ejecute un código si se cumple una condición. Si no, se sigue con el resto de instrucciones del programa:</p>
<pre >poblacion = 13000
umbral = 10000
if poblacion > 10000:
    print('Es una ciudad')
> Es una ciudad</pre>
<h4><strong>If - Else</strong></h4>
<p>En este caso, si la condición del<em> if</em> no se cumple se ejecutará la del <em>else</em>:</p>
<pre >poblacion = 5000
umbral = 10000
if poblacion >= umbral:
    print('Es una ciudad')
else:
    print('Es un pueblo')
> Es un pueblo</pre>
<h4><strong>If - Elif - Else</strong></h4>
<p>Añadiendo el <em>elif</em> establecemos condiciones adicionales. Si alguna se cumple se ejecutará ignorando el resto, por ello es importante el orden en el que se colocan las condiciones:</p>
<pre >poblacion = 'Cádiz'
if poblacion == 'Málaga':
    print('Es Málaga')
elif poblacion == 'Cádiz':
    print('Es Cádiz')
else:
    print('No sabemos qué ciudad es')
> Es Cádiz</pre>
  
 
<h4><strong>Operadores condicionales</strong></h4>
  
  
<figure ><table><tbody><tr><td>&gt;</td><td>Mayor que</td></tr><tr><td>&lt;</td><td>Menor que</td></tr><tr><td>==</td><td>Igual que</td></tr><tr><td>&gt;=</td><td>Mayor o igual que</td></tr><tr><td>&lt;=</td><td>Menor o igual que</td></tr><tr><td>!=</td><td>Distinto de</td></tr></tbody></table></figure>
  
<br></details>
<details>
  <summary><strong>Bucles for</strong></summary><br>
 
  
<p>En los bucles<em> for</em> se repetirá un código un número de veces determinado por la cantidad de elementos que se encuentren en una lista.</p>
<p>Las listas son colecciones de elementos, tal y como explico en el post <a href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/">Fundamentos de Python 1</a>. Cada elemento de una lista ocupa una posición, y el número total posiciones marcará la cantidad de veces que se repetirá el código:</p>
<pre >lista = ['QGIS', 'ArcGIS', 'gvSig']
for n in lista:
    print(n)
> QGIS
> ArcGIS
> gvSig</pre>
<p>El bucle de este ejemplo lo que hace es que por cada elemento de la lista (denominado <em>n</em>) se imprimirá el nombre de dicho elemento. </p>
<p>Se pueden <strong>crear listas numéricas de forma automática</strong> usando la <strong>función range()</strong>, en la que especificaremos el valor máximo que alcanzará dicha lista:</p>
<pre >for n in range(4):
    print('GIS')
> GIS
> GIS
> GIS
> GIS</pre>
<p>También puede definirse el valor desde el que comenzará la lista <strong>range</strong> y el incremento entre uno y otro. Si no se especifica, como en el caso anterior, comenzará por el 0 y el incremento será de 1. En el siguiente ejemplo la lista irá del 4 al 12 incrementándose de 2 en 2:</p>
<pre >rango = range(4,12,2)
for numero in rango:
    print(numero)
> 4
> 6
> 8
> 10
</pre>
  
<br></details>
<details>
  <summary><strong>Bucles while</strong></summary><br>
 
  
<p>Este tipo de bucle repetirá un código mientras se cumpla una condición. En el siguiente ejemplo se comprueba que <em>a </em>sea menor que 5, que en caso afirmativo imprimirá una cadena y aumentará el valor de <em>a</em> en 1:</p>
<pre >a = 1
while a &lt; 5:
    print(str(a) + ' es menor que 5')
    a  += 1
> 1 es menor que 5
> 2 es menor que 5
> 3 es menor que 5
> 4 es menor que 5</pre>
<p>En el momento en el que el valor de <em>a</em> llegó a 5 se dejó de imprimir el texto. Si no aumentáramos el valor de <em>a</em> éste siempre sería menor que 5 y por tanto se imprimiría indefinidamente el texto en lo que se conoce como un <strong>bucle infinito</strong>. Cuando esto pasa hay que <strong>cancelar la ejecución del programa</strong>.</p>
<p>Para controlar estos bucles en los que no sabemos cuántas veces puede repetirse el código, usaremos las palabras reservadas <strong>continue y break</strong>:</p>
<ul><li>continue <strong>se salta un paso del bucle</strong> </li><li>break <strong>interrumpe el bucle</strong></li></ul>
<p>Estas funciones se ejecutarán si se cumple una condición, por lo que tendremos que incluir estructuras condicionales dentro del bucle. En el siguiente ejemplo, cuando <em>a</em> llega a 3 <strong>continue</strong> se lo salta:</p>
<pre >a = 1
while a &lt; 5:
    if a == 3:
        print('(nos saltamos el 3)')
        a += 1
        continue
    else:
        print(str(a) + ' es menor que 5')
        a  += 1
> 1 es menor que 5
> 2 es menor que 5
> (nos saltamos el 3)
> 4 es menor que 5</pre>
<p>Aquí, cuando<em> a</em> llega a 4 <strong>break </strong>interrumpe el bucle:</p>
<pre >a = 1
while a &lt; 5:
    if a == 4:
        print('aquí se interrumpe el bucle')
        break
    else:
        print(str(a) + ' es menor que 5')
        a  += 1
> 1 es menor que 5
> 2 es menor que 5
> 4 es menor que 5
> aquí se interrumpe el bucle</pre>
  
<br></details>

## 🚪 Acceso a los datos

<details>
  <summary><strong>Rutas y codificación de caracteres</strong></summary><br>
 
<p>Las rutas a archivos o <em>paths</em> se escribirán dentro de la clase <em>string</em>, es decir, tendrán que ir entrecomilladas:</p>
<pre >ruta = 'C:\Users\Yo\Documentos\Programación\Python'</pre>
<p>Son de vital importancia para indicar la carpeta de la que queremos coger nuestras capas y/o dónde queremos guardar los resultados de nuestros geoprocesos.</p>
<p>Las barras que separan los directorios pueden dar problemas dependiendo de sistema operativo que se use. En Windows, se puede usar la doble barra para evitarlos:</p>
<pre >ruta = 'C:\\Users\\Yo\\Documentos\\Programación\\Python'</pre>
<p>Otra forma de evitar problemas con los caracteres es añadir una <em>r</em> antes de las comillas, tal y como muestro en el apartado sobre caracteres 👇</p>
<h4><strong>Codificación de caracteres</strong></h4>
<p>Una de las cosas a las que debemos prestar atención a la hora de operar con texto es la codificación de caracteres.</p>
<p>La codificación de caracteres es la forma en que el sistema traduce los caracteres al lenguaje binario de los ordenadores. Existen diversos tipos de codificación, y para <strong>averiguar el que usa nuestro sistema</strong> ejecutaremos el siguiente código:</p>
<pre >import sys
print(sys.getdefaultencoding())
> utf-8</pre>
<p>Si queremos <strong>cambiar la codificación</strong> usada en nuestro script para que, por ejemplo, admita tildes o eñes, tendremos que colocar la siguiente línea al inicio del script:</p>
<pre ># -*- coding: utf-8
</pre>
<p>⚠ En Python 3 la codificación por defecto es unicode o utf-8 (admite tildes, eñes, etc.) mientras que en Python 2 la codificación por defecto es ASCII y tendríamos que usar la sentencia anterior para cambiarlo.</p>
<h4><strong>Caracteres especiales ASCII</strong></h4>
<p>También debemos prestar atención a este tipo de caracteres. Son caracteres que puestos juntos en un texto desempeñan <strong>funciones especiales</strong>. Suele usarse la barra \ seguido de algún otro caracter:</p>
<figure ><table><thead><tr><th  data-align="center">Caracter</th><th  data-align="center">Función</th></tr></thead><tbody><tr><td  data-align="center">\t</td><td  data-align="center">Tabulación</td></tr><tr><td  data-align="center">\n</td><td  data-align="center">Salto de línea</td></tr><tr><td  data-align="center">\'</td><td  data-align="center">Apóstrofe</td></tr></tbody></table></figure>
<p>Esto puede generarnos problemas al manejar cadenas cuando programemos. Por ejemplo, si tenemos una ruta estilo C:\Users\Usuario\nuevos_archivos, la ruta no se leerá correctamente porque tiene un <strong>\n</strong> que hace que lea un salto de línea en ese momento. La solución sería usar un <strong>raw text</strong> para anular estos caracteres especiales añadiendo una <strong>r</strong> antes de la ruta:</p>
<pre >ruta = r'C:\Users\Usuario\nuevos_archivos'</pre>
<p>Pero también pueden resultar útiles. Por ejemplo, el caracter especial de apóstrofe \' resulta útil cuando queremos incluirlo dentro de un texto que ya está entrecomillado, puesto que los apóstrofes se usan para que Python reconozca las cadenas de texto y si metemos uno de por medio quedaría otro por ahí suelto que generaría error:</p>
<pre >print('Guns N' Roses')
> SyntaxError: invalid syntax
print('Guns N\' Roses')
> Guns N' Roses</pre>
<p >⚠ Nota: para evitar problemas con las rutas y cadenas en general en Python 2 existe la función raw_input() que aplicada a una cadena es equivalente a añadir la <em>r </em></p>
  
<br></details>


<details>
  <summary><strong>Directorios</strong></summary><br>
 
  
<p>Para acceder al sistema de archivos del ordenador y realizar operaciones como crear carpetas, listar o borrar archivos, etc. Python necesita <strong>importar el módulo <em>os</em></strong>, el cual recoge las funciones necesarias para ello:</p>
<pre >import os</pre>
<h3 ><strong>Funciones del módulo <em>os</em></strong></h3>
<figure ><table><tbody><tr><td>os.listdir(ruta)</td><td>Devuelve una lista con todos los archivos de una ruta</td></tr><tr><td>os.mkdir(ruta) </td><td>Crea un directorio en la ruta especificada incluyendo su nombre</td></tr><tr><td>os.remove(ruta)</td><td>Borra un archivo </td></tr><tr><td>os.rmdir()</td><td>Borra un directorio solo si está vacío</td></tr><tr><td>os.rename('ruta del archivo','nuevo nombre')</td><td>Cambia el nombre de un archivo</td></tr><tr><td>os.path.exists()</td><td>Devuelve un booleano (true o false) en función si el directorio o archivo existe</td></tr><tr><td>os.path.basename()</td><td>Devuelve una cadena con el nombre del directorio</td></tr><tr><td>os.path.splitext()</td><td>Devuelve una lista con dos elementos: el nombre del archivo y su extensión</td></tr><tr><td>os.isdir()</td><td>Devuelve un booleano en función de si la ruta indicada es o no un directorio</td></tr><tr><td>os.path.join(ruta, "nombrearchivo.extensión")</td><td>Une una ruta con el nombre de un archivo, ahorrándonos el escribir nosotros la contrabarra </td></tr><tr><td>os.system('comando')</td><td>Permite ejecutar comandos de la consola de comandos del PC.</td></tr></tbody></table></figure>
<h3 ><strong>Crear un directorio</strong></h3>
<p>Para crear un directorio conviene <strong>comprobar antes si existe</strong>:</p>
<pre >import os
ruta = "C:/ruta/carpeta"
if os.path.exists(ruta):
    print("Ya existe")
else:
    os.mkdir(ruta)
    print("Creado")</pre>
<h3 ><strong>Listar los archivos de un directorio</strong></h3>
<p>Usando listdir() podemos <strong>crear una lista</strong> con los nombres de los archivos existentes en una ruta junto a su extensión:</p>
<pre >import os
ruta = "C:\\ruta\\carpeta"
lista_ficheros = os.listdir(ruta)
print(lista_ficheros)</pre>
<h3 ><strong>Obtener nombres y extensiones de los archivos</strong></h3>
<p>Si quisiéramos obtener solo los nombres de los archivos o solo sus extensiones, habría que aplicar la función os.path.splitext() a cada elemento de la lista generada por os.listdir():</p>
<pre >import os
ruta = "C:\\ruta\\carpeta"
lista_ficheros = os.listdir(ruta)
for fichero in lista_ficheros:
    nombres = os.path.splitext(fichero)[0]
    extensiones = os.path.splitext(fichero)[1]
    print(nombres)
    print(extensiones)
</pre>
<p>Hay que tener en cuenta que también listará las carpetas que se encuentren en el directorio, y estas no cuentan con extensión.</p>
<h3 ><strong>Filtrar archivos por tipo</strong></h3>
<p>Siguiendo con lo anterior, podemos quedarnos en una nueva lista solo con los archivos de cierto tipo comprobando que su extensión coincida con la que indiquemos en una variable:</p>
<pre >import os
ruta = "C:\\ruta\\carpeta"
lista_capas = os.listdir(ruta)
lista_shapes = []
filtro = ".shp"
for capa in lista_capas:
    extensiones = os.path.splitext(capa)[1]
    if extensiones == filtro:
        lista_shapes.append(capa)
print(lista_shapes)</pre>
  
<br></details>
<details>
  <summary><strong>Ficheros</strong></summary><br>
 
  
<p>Los ficheros o archivos son una clase de Python que corresponde a la información almacenada en un fichero que se encuentre en nuestro ordenador. Python puede abrir y modificar multitud de tipos de fichero, incluidos los comúnmente usados por los SIG como Shapefiles, GeoPackages, GeoTIFF...</p>
<p>Sin embargo, para trabajar con los ficheros SIG en Python conviene antes conocer cómo operar a nivel básico con ficheros de texto, ya sean .txt o .csv, que suelen guardar información también necesaria en los SIG.</p>
<h3 ><strong>Abrir un fichero</strong></h3>
<p>Para operar con los ficheros tendremos que abrir un fichero y <a href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/">almacenarlo en una variable</a>:</p>
<pre >fichero = open(r'C:\Users\Yo\Documentos\Python\miarchivo.ext', 'r')</pre>
<p>El fichero podrá <a rel="noreferrer noopener" href="https://uniwebsidad.com/libros/python/capitulo-9/sobre-el-objeto-file" target="_blank">abrirse de distintas formas según convenga</a>, aunque las principales son los modos de lectura y escritura:</p>
<figure ><table><tbody><tr><td>open(‘ruta’,’r’)</td><td>Abrir un fichero en modo lectura (no se podrá modificar)<br>Genera error si no existe el archivo.</td></tr><tr><td>open(‘ruta’,’w’)</td><td>Abrir un fichero en modo escritura (permite modificarlo)<br>Si no existe se creará.</td></tr></tbody></table></figure>
<p >⚠ <strong>Si surge algún problema</strong>, asegúrate de que la ruta es correcta y que has incluido la extensión del fichero. Además, la ruta debe estar entrecomillada para que sea tomada como texto. También suele ocurrir que al copiar y pegar rutas se incluyan caracteres especiales (\u202aC), lo cual se suele arreglar borrando y escribiendo de nuevo los primeros caracteres. Por último, las barras de separación pueden originar <a rel="noreferrer noopener" href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/#texto" target="_blank">caracteres especiales ASCII</a>, por lo que es aconsejable colocar una r delante de la ruta (tal y como se ve en el ejemplo de arriba) para que la ruta sea un raw text.</p>
<h3 ><strong>Crear un fichero</strong></h3>
<p>Para crear un fichero nuevo hay que usar el método open() en modo escritura (w) e indicar una ruta de vuestro ordenador junto al nombre y extensión que tendrá el nuevo fichero. Ningún archivo en el directorio elegido debe tener el mismo nombre que el archivo que vamos a crear.</p>
<h3 ><strong>Métodos de fichero</strong></h3>
<p>Como toda clase en Python, los ficheros tienen sus propios métodos con los que hacer distintas operaciones con ellos. La variable con el fichero abierto se puede usar, entre otros, con los siguientes métodos:</p>
<figure ><table><tbody><tr><td>fichero.read()</td><td>Devuelve el contenido del fichero en una cadena de texto</td></tr><tr><td>fichero.readline()</td><td>Devuelve una línea del fichero en una cadena de texto</td></tr><tr><td>fichero.readlines()</td><td>Devuelve una lista que almacena cada<br>línea del fichero en una posición</td></tr><tr><td>fichero.write('texto')</td><td>Escribe en el fichero el texto indicado</td></tr><tr><td>fichero.close()</td><td>Cierra el fichero para que los datos escritos se vean correctamente</td></tr></tbody></table></figure>
<h3 ><strong>Ver un fichero</strong></h3>
<p>Para ver un archivo en Python tendremos que crear un bucle for  que imprima cada una de las líneas del archivo almacenadas en la lista que devuelve el método readlines(). Al final del código cerramos el archivo:</p>
<pre >fichero = open(r'C:\Users\Yo\Documentos\Python\miarchivo.ext', 'r')
for linea in fichero.readlines():
    print(linea)
fichero.close()
> linea 1
> linea 2
> linea 3
...</pre>
<h3 ><strong>Acceder a las columnas de un archivo</strong></h3>
<p>En ficheros de texto que contengan tablas, podremos usar el <a rel="noreferrer noopener" href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/#texto" target="_blank">método split()</a> para convertir cada línea en una lista que separe cada una de los valores que contenga, pudiendo así acceder a su posición.</p>
<p>Por ejemplo, tenemos la siguiente tabla en un fichero .txt y queremos acceder solo a la primera y tercera columna:</p>
<pre><code>0 1 2 3 4
3 4 8 6 2
4 5 8 9 7</code></pre>
<p>Guardaremos la tabla en un objeto y haremos que a cada línea extraida con readlines() se le aplique split() indicando que el archivo separa los valores con espacios.</p>
<p>La lista que genera split() la almacenamos en una nueva variable en la que podremos seleccionar qué columnas imprimimos según su posición:</p>
<pre >fichero = open(r'C:\Users\Yo\Documentos\Python\miarchivo.ext', 'r')
for linea in fichero.readlines():
    columnas = linea.split(' ')
    print(columnas[0], columnas[2])
fichero.close()
> 0 2
> 3 8
> 4 8</pre>
<h3 ><strong>Escribir en un fichero</strong></h3>
<p>Para escribir en un fichero habrá que abrirlo (o crearlo) en <strong>modo escritura</strong> (w) y <strong>usar el método write()</strong> sobre él para añadirle el texto que queramos. No olvidar cerrar el fichero con close().</p>
<p>En el siguiente ejemplo se crea una lista y se escribe cada uno de los elementos que contiene en un nuevo archivo:</p>
<pre >capitales_andalucia = ['Córdoba', 'Jaén', 'Almería', 'Cádiz', 'Granada', 'Sevilla', 'Málaga']
fichero = open(r'C:\Users\Yo\Documentos\Python\andalucia.txt', 'w')
for ciudad in fichero:
    fichero.write(ciudad + '\n')
fichero.close()</pre>
<p>Como le hemos dicho que añada el caracter especial ASCII de salto de página \n cada elemento se escribirá en una línea distinta:</p>
<figure><img src="https://programapa.files.wordpress.com/2021/01/image-4.png?w=285" alt="" class="wp-image-4697"/></figure>
<h3 ><strong>Copiar datos de un fichero a otro</strong></h3>
<p>Podemos hacer selecciones de datos de un fichero para guardarlas en uno nuevo que solo contenga esa información filtrada.</p>
<p>Por ejemplo, podemos seleccionar aquellas ciudades del ejemplo anterior que empiecen con la letra C y guardarlas en un nuevo fichero de texto:</p>
<pre >ciudades = open(r'C:\Users\Yo\Documentos\Python\andalucia.txt', 'r')
ciudades_C = open(r'C:\Users\Yo\Documentos\Python\andalucia_C.txt', 'w')
for ciudad in ciudades.readlines():
    if ciudad[0] == 'C':
        ciudades_C.write(ciudad)
    
ciudades.close()
ciudades_C.close()
</pre>
<p>Los saltos de línea ya estaban guardados en el archivo de lectura porque los incluimos nosotros antes, de modo que al copiarlo están en el nuevo archivo:</p>
<figure><img src="https://programapa.files.wordpress.com/2021/01/image-5.png?w=288" alt="" class="wp-image-4699"/></figure>
  
<br></details>
<details>
  <summary><strong>Inputs</strong></summary><br>
 
  
<p>Los inputs son valores que el usuario de un programa informático introduce de forma dinámica para obtener un resultado. Podemos hacer que un programa requiera que el usuario introduzca datos para seguir ejecutándose mediante la función input().</p>
<p>Por ejemplo, podemos modificar el script anterior para que se calcule la media de dos valores cualesquiera que introduzca el usuario:</p>
<pre >def media(x,y):
    resultado = (x + y)/2
    return resultado
print('¡Averigua la media de dos números!')
num1 = float(input('Introduce un número: '))
num2 = float(input('Introduce otro número: '))
print(media(num1,num2))</pre>
<p>Se ha forzado el input mediante la función de conversión de variables float() para que los números sean siempre tomados como floats y no como texto.</p>
<p>También se puede añadir un pequeño mensaje dentro de la función en formato string para guiar al usuario. </p>
<p >⚠ En Python 2 hay dos clases de inputs: <em>input()</em> permite diferenciar entre números y texto si hacemos uso o no de las comillas, y <em>raw_input()</em> convierte todo a texto.  En Python 3, la función <em>input()</em> devuelve todo como texto (sustituyendo a <em>raw_input()</em>) y tendremos que usar funciones de conversión. Si queremos que el procedimiento sea automático y sea Python quien decida (similar al <em>input()</em> de Python 2) tendremos que usar la función <em>input()</em> dentro de la función <em>eval()</em>. </p>
  
<br></details>

## ⚠️ Errores

<details>
  <summary><strong>Mensajes de error</strong></summary><br>
  
<figure ><table><tbody><tr><td>SyntaxError</td><td>El código está mal escrito y tiene errores de sintaxis</td></tr><tr><td>AttributeError</td><td>Intentamos un método sobre un objeto que no lo permite (como aplicar un método de lista a un número)</td></tr><tr><td>ValueError:</td><td>Usamos un valor incompatible dentro de una función </td></tr><tr><td>IndexError</td><td>Cuando se señala una posición que no existe en una cadena o lista</td></tr><tr><td>NameError</td><td>Se llama a una variable que no está asignada o función que no existe</td></tr><tr><td>IOError</td><td>Cuando se intenta abrir un archivo no existe</td></tr><tr><td>TypeError</td><td>Cuando hacemos operaciones con valores incompatibles (como tratar de sumar una cadena y un número)</td></tr><tr><td>ZeroDivisionError</td><td>Intentamos dividir entre 0</td></tr><tr><td>KeyError:</td><td>Cuando falta una llave en un diccionario y queremos acceder a ella</td></tr></tbody></table></figure>
 
<br></details>

<details>
  <summary><strong>Errores y excepciones</strong></summary><br>
    
<p>En el ámbito de la programación podemos encontrar fundamentalmente <strong>3 tipos de errores</strong> dependiendo de su origen:</p>
<h3 ><strong>Errores de sintaxis</strong></h3>
<p>Son el resultado de escribir sin respetar las reglas sintácticas de un código: no cerrar paréntesis o comillas, no indentar bien el código, escribir mal el nombre de una función... por lo que tienen fácil solución.</p>
<p>Cuando se produce uno de estos errores el intérprete devuelve el mensaje <em><strong>SyntaxError</strong></em>. Además, se suele indicar el lugar del código donde se ha producido el error.</p>
<h3 ><strong>Errores semánticos</strong></h3>
<p>Esta clase de errores se producen cuando el código programado no devuelve el resultado esperado porque nuestro código no está haciendo lo que habíamos planeado. En estos casos, el intérprete no devuelve mensaje de error, por lo que tendremos que<strong> fijarnos en el resultado</strong> que hemos obtenido para averiguar dónde está el problema.</p>
<h3 ><strong>Errores de ejecución: excepciones</strong></h3>
<p>Estos errores surgen cuando el código no puede seguir ejecutándose, por lo que detienen el programa y se devuelve un mensaje de error. Se les suele llamar <strong>excepciones</strong>.</p>
<p>¿Cuándo deja un código de poder ejecutarse? El origen es muy diverso, ya que puede venir dado por errores en la programación del código (por ejemplo si intenta sumar un número y una cadena) o por cuestiones ajenas a él, como intentar leer un archivo que se encuentre dañado.</p>
<p>Por ejemplo, ¿qué le ocurriría al código que creamos en el apartado input si el usuario en vez de introducir un número introduce una palabra como puede ser el número escrito en letras? Devolvería un error que le imposibilitaría seguir ejecutándose:</p>
<pre >> ValueError: could not convert string to float: 'veinte'</pre>
<p>Esto es porque el input del usuario se intenta a convertir a float para que no existan errores en las operaciones que calculan la media, pero como contamos en el apartado de la <a href="https://programapa.wordpress.com/2021/01/23/fundamentos-de-python-1-variables-clases-funciones-y-metodos/#convertir_variables">conversión de variables</a>, no se puede transformar caracteres a números.</p>
<p>¿Cómo se <strong>evitan</strong> esta clase de errores? A través del <strong>control de excepciones</strong> y las <strong>validaciones</strong>.</p>
  
<br></details>
<details>
  <summary><strong>Control de excepciones</strong></summary><br>
 
  
<p>Consiste en crear bloques de código alternativos que se ejecutarán en caso de que nuestra primera opción falle. La estructura que sigue es la siguiente:</p>
<ul><li>try - primer bloque de código que se ejecutará.</li><li>except - en caso de existir un error, se ejecutará este segundo bloque. Si no hay error, se saltará.</li><li>finally - este último bloque es opcional, y siempre se ejecutará.</li></ul>
<pre >def media(x,y):
    resultado = (x + y)/2
    return resultado
print('¡Averigua la media de dos números!')
try:
   num1 = float(input('Introduce un número: '))
   num2 = float(input('Introduce otro número: '))
   print(media(num1,num2))
except:
   print('Algo ha fallado')
finally:
   print('Prueba otra vez')</pre>
<p>Se pueden usar tantos <em>except </em>como distintos errores queramos identificar. Para ello, basta con añadir el nombre del error a continuación del <em>except</em>:</p>
<pre>except ValueError:
   print('Has introducido una palabra en vez de un número')
except:
   print('Algo ha fallado')</pre>
  
<br></details>
<details>
  <summary><strong>Validaciones y contadores</strong></summary><br>
 
  
<h4><strong>Validaciones: while True</strong></h4>
<p>Las validaciones son una vuelta de tuerca al control de excepciones para que el programa no tenga ejecutarse manualmente de nuevo en caso de encontrar una excepción, sino que podemos pedir al usuario que intente introducir de nuevo un valor en caso de que no lo haya hecho correctamente la primera vez. </p>
<p>Es lo que se conoce como <strong>programación defensiva</strong>: prever los errores del usuario para asegurarnos de que utiliza bien el programa.</p>
<p>La forma de crear validaciones es crear un bucle <em>while True,</em> un truco con el que creamos un bucle infinito (verdadero siempre es verdadero) que no se detendrá a menos que usemos un <em>break</em>.</p>
<p>Cuando se produzca un error, <em>continue</em> nos mandará de nuevo al inicio del bucle, osea al <em>try</em>, y si este se ejecuta correctamente pasará al <em>else</em>, que lo cerrará usando <em>break</em>:</p>
<pre >print('¡Averigua la media de dos números!')
while True:
    try:
        num1 = float(input('Introduce un número: '))
        num2 = float(input('Introduce otro número: '))
        print(media(num1,num2))
    except ValueError:
        print('No has introducido un número')
        continue
    else:
        break</pre>
<p>Una vez que los inputs son correctos, el bucle podrá ejecutar la sentencia <em>else</em> y detenerse con <em>break</em>. En caso de haber seguido utilizando <em>finally</em> en lugar de <em>else</em>, de poco nos habría servido el <em>continue</em> pues <em>finally </em>siempre se ejecuta.</p>
<h4><strong>Contadores</strong></h4>
<p>En Python es posible programar contadores para establecer un máximo número de intentos que vaya a tener el usuario para introducir bien los datos. Basta con crear una variable contador y sumarle 1 cada vez que se repita el error, estableciendo un límite a partir del cual el bucle se interrumpirá y no dejará intentarlo de nuevo:</p>
<pre >contador = 0
print('¡Averigua la media de dos números!')
while True:
    try:
        num1 = float(input('Introduce un número: '))
        num2 = float(input('Introduce otro número: '))
        print(media(num1,num2))
    except ValueError:
        print('No has introducido un número')
        contador += 1
        if contador >= 3:
           print('Has superado el límite de intentos')
           break
        else:
           continue
    else:
        break</pre>
  
<br></details>

