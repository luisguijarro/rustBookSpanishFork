# Introduction

> Note: This edition of the book is the same as [The Rust Programming
> Language][nsprust] available in print and ebook format from [No Starch
> Press][nsp].

[nsprust]: https://nostarch.com/rust
[nsp]: https://nostarch.com/

Bienvenidos a *The Rust Programming Language*, un libro introductorio a Rust.
The Rust programming language le ayuda a escribir software más rápido y confiable .
La ergonomía de alto nivel y el control de bajo nivel a menudo están en desacuerdo en el diseño de los lenguajes de programación; Rust desafía ese conflicto. A través del equilibrio de poder
capacidad técnica y una gran experiencia de desarrollador, Rust te da la opción
para controlar los detalles de bajo nivel (como el uso de la memoria) sin todas las molestias
tradicionalmente asociado con tal control .

## Para quien es Rust

Rust es ideal para muchas personas por diversas razones. Veamos algunos de
los grupos más importantes. 

### Equipos de Desarrolladores 

Rust está demostrando ser una herramienta productiva para colaborar entre 
grandes equipos de desarrolladores con diferentes niveles de conocimiento 
de programación de sistemas. El código de bajo nivel es propenso a una variedad 
de errores sutiles, que en la mayoría de los otros lenguajes solo pueden 
detectarse mediante pruebas exhaustivas y una revisión cuidadosa del código por 
parte de desarrolladores experimentados. 
En Rust, el compilador juega un papel de guardián al negarse a compilar código 
con estos errores elusivos, incluidos los errores de concurrencia. Al trabajar 
junto con el compilador, el equipo puede dedicar su tiempo a concentrarse en la 
lógica del programa en lugar de perseguir errores. 

Rust también trae herramientas de desarrollo contemporáneas al mundo de la 
programación de sistemas: 

* Cargo, el administrador de dependencias y la herramienta de compilación 
  incluidos, hace que agregar, compilar y administrar dependencias sea sencillo 
  y consistente en todo el ecosistema de Rust.
* Rustfmt garantiza un estilo de codificación coherente entre los desarrolladores.
* Rust Language Server impulsa la integración del entorno de desarrollo integrado 
  (IDE) para completar el código y mensajes de error en línea. 

Al utilizar estas y otras herramientas en el ecosistema de Rust, los 
desarrolladores pueden ser productivos mientras escriben código a nivel de 
sistemas. 

### Estudiantes

Rust es para estudiantes y aquellos que estén interesados en aprender sobre 
conceptos de sistemas. Con Rust, muchas personas han aprendido sobre temas como el 
desarrollo de sistemas operativos. La comunidad es muy acogedora y feliz de 
responder las preguntas de los estudiantes. A través de esfuerzos como este libro, 
los equipos de Rust quieren hacer que los conceptos de sistemas sean más accesibles 
para más personas, especialmente aquellos que son nuevos en la programación. 

### Compañias

Cientos de empresas, grandes y pequeñas, utilizan Rust en la producción para una 
variedad de tareas. Esas tareas incluyen herramientas de línea de comandos, 
servicios web, herramientas DevOps, dispositivos integrados, análisis y 
transcodificación de audio y video, criptomonedas, bioinformática, motores de 
búsqueda, aplicaciones de Internet de las cosas, aprendizaje automático e incluso 
partes importantes del navegador web Firefox. 

### Desarrolladores de código abierto

Rust es para personas que desean crear el lenguaje de programación Rust, la 
comunidad, las herramientas de desarrollo y las bibliotecas de Rust. 
Nos encantaría que contribuyeses al lenguaje de programación Rust. 

### Personas que valoran la velocidad y la estabilidad 

Rust es para personas que anhelan velocidad y estabilidad en un lenguaje. 
Por velocidad, nos referimos a la velocidad de los programas que puede crear con 
Rust y la velocidad a la que Rust le permite escribirlos. Las comprobaciones del 
compilador de Rust garantizan la estabilidad mediante la incorporación de 
funciones y la refactorización. Esto contrasta con el frágil código heredado en 
lenguajes sin estas comprobaciones, que los desarrolladores a menudo tienen 
miedo de modificar. Al esforzarse por obtener abstracciones de costo cero, 
características de nivel superior que se compilan en código de nivel inferior 
tan rápido como el código escrito manualmente, Rust se esfuerza por hacer que el 
código seguro también sea un código rápido. 

El lenguaje Rust espera ser compatible con muchos otros usuarios también; los 
mencionados aquí son simplemente algunos de los principales interesados. 
En general, la mayor ambición de Rust es eliminar las compensaciones que los 
programadores han aceptado durante décadas al brindar seguridad *y* 
productividad, velocidad *y* ergonomía. Prueba Rust y comprueba si sus opciones 
funcionan para ti. 

## Para quien es este libro

Este libro asume que ha escrito código en otro lenguaje de programación, pero no 
hace ninguna suposición sobre cuál. Intentamos que el material sea ampliamente 
accesible para quienes tienen una amplia variedad de antecedentes en programación. 
No pasamos mucho tiempo hablando sobre qué es la programación * o cómo pensar en 
ella. Si es completamente nuevo en la programación, sería mejor que leyera un 
libro que proporcione específicamente una introducción a la programación. 

## Como usar este libro 

En general, este libro asume que lo está leyendo en secuencia de adelante hacia 
atrás. Los capítulos posteriores se basan en conceptos de capítulos anteriores, 
y es posible que los capítulos anteriores no profundicen en los detalles de un 
tema volviendose a tratar el tema en un capítulo posterior. 

Encontrará dos tipos de capítulos en este libro: capítulos de conceptos y 
capítulos de proyectos. En los capítulos de conceptos, aprenderá sobre un aspecto 
de Rust. En los capítulos del proyecto, crearemos pequeños programas juntos, 
aplicando lo que ha aprendido hasta ahora. Los capítulos 2, 12 y 20 son capítulos 
de proyectos; el resto son capítulos de conceptos. 

El capítulo 1 explica cómo instalar Rust, cómo escribir un programa 
"¡Hola, mundo!" y cómo utilizar Cargo, el administrador de paquetes y la 
herramienta de compilación de Rust. 
El capítulo 2 es una introducción práctica al lenguaje Rust. Aquí cubrimos 
conceptos a un alto nivel, y los capítulos posteriores proporcionarán detalles 
adicionales. Si quiere ensuciarse las manos de inmediato, el Capítulo 2 es el 
lugar indicado. Al principio, es posible que desee omitir el Capítulo 3, que 
cubre características de Rust similares a las de otros lenguajes de programación, 
y dirijirse directamente al Capítulo 4 para aprender sobre el sistema de propiedad 
de Rust. 
Sin embargo, si eres un aprendiz particularmente meticuloso que prefiere aprender 
cada detalle antes de pasar al siguiente, es posible que desees saltarte el 
Capítulo 2 e ir directamente al Capítulo 3, volviendo al Capítulo 2 cuando 
quieras trabajar en un proyecto aplicando los detalles que ha aprendido. 

El Capítulo 5 trata sobre estructuras y métodos, y el Capítulo 6 cubre 
enumeradores, expresiones `match` y la construcción de flujo de control` if let`. 
Usarás estructuras y enumeradores para crear tipos personalizados en Rust. 

En el Capítulo 7, aprenderá sobre el sistema de módulos de Rust y sobre las 
reglas de privacidad para organizar su código y su Interfaz de programación de 
aplicaciones pública (API). El Capítulo 8 analiza algunas estructuras de datos 
de colección comunes que proporciona la biblioteca estándar, como vectores, 
cadenas y mapas hash. 
El Capítulo 9 explora la filosofía y las técnicas de manejo de errores de Rust. 

El Capítulo 10 profundiza en genéricos, rasgos y vidas, que le dan el poder de 
definir código que se aplica a múltiples tipos. 
El capítulo 11 trata sobre las pruebas, que incluso con las garantías de 
seguridad de Rust son necesarias para garantizar que la lógica de su programa sea 
correcta. 
En el Capítulo 12, crearemos nuestra propia implementación de un subconjunto de 
funciones de la herramienta de línea de comandos `grep` que busca texto dentro de 
los archivos. Para ello, usaremos muchos de los conceptos que discutimos en los 
capítulos anteriores. 

El capítulo 13 explora cierres e iteradores: características de Rust que 
provienen de lenguajes de programación funcionales. 
En el Capítulo 14, examinaremos Cargo con más profundidad y hablaremos sobre las 
mejores prácticas para compartir sus bibliotecas con otros. 
El Capítulo 15 analiza los punteros inteligentes que proporciona la biblioteca 
estándar y las características que habilitan su funcionalidad. 

En el Capítulo 16, analizaremos diferentes modelos de programación concurrente y 
hablaremos sobre cómo Rust lo ayuda a programar en múltiples subprocesos sin 
temor.
El Capítulo 17 analiza cómo se comparan los modismos de Rust con los principios 
de programación orientada a objetos con los que puede estar familiarizado. 

El Capítulo 18 es una referencia sobre patrones y coincidencia de patrones, que 
son formas poderosas de expresar ideas a través de los programas de Rust. 
El Capítulo 19 contiene una mezcla heterogénea de temas avanzados de interés, 
que incluyen Rust inseguro, macros y más sobre tiempos de vida, rasgos, tipos, 
funciones y cierres. 

En el Capítulo 20, completaremos un proyecto en el que implementaremos un 
servidor web multiproceso de bajo nivel. 

Por último, algunos apéndices contienen información útil sobre el idioma en un 
formato más parecido a una referencia. 
El Apéndice A cubre las palabras clave de Rust, el Apéndice B cubre los operadores 
y símbolos de Rust, el Apéndice C cubre los rasgos derivables proporcionados por 
la biblioteca estándar, el Apéndice D cubre algunas herramientas de desarrollo 
útiles y el Apéndice E explica las ediciones de Rust.

No hay una forma incorrecta de leer este libro: si quieres saltarte adelante, 
¡adelante!
Es posible que deba volver a los capítulos anteriores si experimenta alguna 
confusión. Pero haz lo que funcione para ti. 

<span id="ferris"></span>

Una parte importante del proceso de aprendizaje de Rust es aprender a leer los 
mensajes de error que muestra el compilador: estos lo guiarán hacia el código de 
trabajo.
Como tal, proporcionaremos muchos ejemplos que no se compilan junto con el mensaje 
de error que el compilador le mostrará en cada situación. Sepa que si ingresa y 
ejecuta un ejemplo aleatorio, ¡es posible que no se compile! 
Asegúrese de leer el texto que lo rodea para ver si el ejemplo que está intentando 
ejecutar es un error. Ferris también lo ayudará a distinguir el código que no está 
destinado a funcionar: 

| Ferris                                                                 | Significa                                        |
|------------------------------------------------------------------------|--------------------------------------------------|
| <img src="img/ferris/does_not_compile.svg" class="ferris-explain"/>    | ¡Este código no compila!                         |
| <img src="img/ferris/panics.svg" class="ferris-explain"/>              | ¡Este código entra en pánico!                    |
| <img src="img/ferris/unsafe.svg" class="ferris-explain"/>              | Este bloque de código contiene código inseguro.  |
| <img src="img/ferris/not_desired_behavior.svg" class="ferris-explain"/>| Este código no produce el comportamiento deseado.|

En la mayoría de las situaciones, lo llevaremos a la versión correcta de 
cualquier código que no se compile. 

## Código Fuente

Los archivos fuente a partir de los cuales se genera la versión original en 
inglés de este libro se pueden encontrar en 
[GitHub][book].

Los archivos fuente a partir de los cuales se genera la versión en 
español de este libro se pueden encontrar en 
[GitHub][esbook].

[book]: https://github.com/rust-lang/book/tree/master/src
[esbook]: https://github.com/luisguijarro/rustBookSpanishFork/tree/master/src
