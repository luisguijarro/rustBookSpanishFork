## !Hola, Mundo!

Ahora que ha instalado Rust, escriba su primer programa Rust. Cuando se aprende 
un nuevo lenguaje, es tradicional escribir un pequeño programa que imprima el 
texto "¡Hola, mundo!" En la pantalla, ¡así que haremos lo mismo aquí! 

> Nota: Este libro asume una familiaridad básica con la línea de comandos. 
> Rust no hace demandas específicas sobre su edición o herramientas o dónde 
> reside su código, por lo que si prefiere usar un entorno de desarrollo 
> integrado (IDE) en lugar de la línea de comandos, no dude en usar su IDE 
> favorito. Muchos IDE ahora tienen cierto grado de compatibilidad con Rust; 
> consulte la documentación del IDE para obtener más detalles. Recientemente, 
> el equipo de Rust se ha centrado en permitir un gran soporte de IDE, ¡y se ha 
> avanzado rápidamente en ese frente! 

### Crear un directorio de proyectos 

Empezaremos por crear un directorio para almacenar tu código de Rust. A Rust no 
le importa dónde vive su código, pero para los ejercicios y proyectos de este 
libro, le sugerimos que cree un directorio de *proyectos* en su directorio 
personal y que mantenga todos sus proyectos allí. 

Abra una terminal e ingrese los siguientes comandos para crear un directorio de 
*proyectos* y un directorio para el proyecto "¡Hola, mundo!" dentro del 
directorio *proyectos*. 

Para Linux, macOS y PowerShell en Windows, ingrese lo siguiente: 

```console
$ mkdir ~/projects
$ cd ~/projects
$ mkdir hello_world
$ cd hello_world
```

Para CMD de Windows, ingrese esto: 

```cmd
> mkdir "%USERPROFILE%\projects"
> cd /d "%USERPROFILE%\projects"
> mkdir hello_world
> cd hello_world
```

### Escribir y ejecutar un programa de Rust 

A continuación, cree un nuevo archivo fuente y llámelo *main.rs*. Los archivos 
Rust siempre terminan con la extensión *.rs*. Si usa más de una palabra en su 
nombre de archivo, use un guión bajo para separarlas. Por ejemplo, use 
*hello_world.rs* en lugar de *helloworld.rs*. 

Ahora abra el archivo *main.rs* que acaba de crear e ingrese el código en el 
Listado 1-1. 

<span class="filename">Filename: main.rs</span>

```rust
fn main() {
    println!("!Hola, mundo!");
}
```

<span class="caption">Listado 1-1: Un programa que imprime `¡Hola, mundo!`</span>

Guarde el archivo y vuelva a la ventana de su terminal. En Linux o macOS, 
ingrese los siguientes comandos para compilar y ejecutar el archivo: 

```console
$ rustc main.rs
$ ./main
!Hola, mundo!
```

En Windows, ingrese el comando `.\main.exe` instancia de `./main`:

```powershell
> rustc main.rs
> .\main.exe
!Hola, mundo!
```

Independientemente de su sistema operativo, la cadena "¡Hola, mundo!" debería 
imprimirse en la terminal. Si no ve este resultado, consulte la parte 
["Solución de problemas"][troubleshooting] <!-- ignore --> de la sección 
Instalación para conocer las formas de obtener ayuda. 

Si se imprimió `¡Hola, mundo!', ¡Enhorabuena! Has escrito oficialmente un 
programa de Rust. Eso lo convierte en un programador de Rust, ¡bienvenido! 

### Anatomía de un programa de Rust 

Repasemos en detalle lo que acaba de suceder en su programa "¡Hola, mundo!".
Aquí está la primera pieza del rompecabezas: 

```rust
fn main() {

}
```

Estas líneas definen una función en Rust. La función `main` es especial: 
siempre es el primer código que se ejecuta en cada programa ejecutable de 
Rust. La primera línea declara una función llamada `main` que no tiene 
parámetros y no devuelve nada. Si hubiera parámetros, irían entre 
paréntesis, `()`. 

Además, tenga en cuenta que el cuerpo de la función está envuelto entre 
llaves, `{}`. Rust los requiere en todos los cuerpos funcionales. Es un 
buen estilo colocar el corchete de apertura en la misma línea que la 
declaración de la función, agregando un espacio entre ellos. 

Si desea ceñirse a un estilo estándar en todos los proyectos de Rust, 
puede usar una herramienta de formateo automática llamada `rustfmt` para 
formatear su código en un estilo particular. El equipo de Rust ha incluido 
esta herramienta con la distribución estándar de Rust, como `rustc`, por 
lo que ya debería estar instalada en su computadora. Consulte la 
documentación en línea para obtener más detalles. 

Dentro de la función `main` se encuentra el siguiente código: 

```rust
    println!("!Hola, mundo!");
```

Esta línea hace todo el trabajo en este pequeño programa: imprime texto en 
la pantalla. Hay cuatro detalles importantes a tener en cuenta aquí. 

Primero, el estilo Rust es sangrar con cuatro espacios, no una tabulación. 

En segundo lugar, `println!` Llama a una macro de Rust. Si en su lugar 
llamara a una función, se ingresaría como `println` (sin el`!`). 
Discutiremos las macros de Rust con más detalle en el Capítulo 19. Por 
ahora, solo necesita saber que usar un `!` Significa que está llamando a 
una macro en lugar de a una función normal. 

En tercer lugar, verá la cadena `"¡Hola, mundo!"`. Pasamos esta cadena 
como argumento a `println!`, Y la cadena se imprime en la pantalla. 

Cuarto, terminamos la línea con un punto y coma (`;`), que indica que esta 
expresión ha terminado y la siguiente está lista para comenzar. La mayoría 
de las líneas de código de Rust terminan con un punto y coma. 

### La compilación y la ejecución son pasos separados 

Acaba de ejecutar un programa recién creado, así que examinemos cada paso 
del proceso. 

Antes de ejecutar un programa Rust, debe compilarlo usando el compilador 
Rust ingresando el comando `rustc` y pasándole el nombre de su archivo 
fuente, así: 

```console
$ rustc main.rs
```

Si tiene experiencia en C o C ++, notará que esto es similar a `gcc` o 
`clang`. Después de compilar con éxito, Rust genera un ejecutable binario. 

En Linux, macOS y PowerShell en Windows, puede ver el ejecutable 
ingresando el comando `ls` en su shell. En Linux y macOS, verá dos 
archivos. Con PowerShell en Windows, verá los mismos tres archivos que 
vería usando CMD. 

```console
$ ls
main  main.rs
```

Con CMD en Windows, debe ingresar lo siguiente: 

```cmd
> dir /B %= la opción /B indica que solo muestre los nombres de los archivos =%
main.exe
main.pdb
main.rs
```

Esto muestra el archivo de código fuente con la extensión *.rs*, el archivo 
ejecutable (*main.exe* en Windows, pero *main* en todas las demás plataformas) y, 
cuando se usa Windows, un archivo que contiene información de depuración con 
*Extensión .pdb*.
Desde aquí, ejecuta el archivo *main* o *main.exe*, así: 

```console
$ ./main # o .\main.exe en Windows
```

Si *main.rs* es su programa "¡Hola, mundo!", esta línea imprimiría `Hola,
mundo!` a tu terminal. 

Si está más familiarizado con un lenguaje dinámico, como Ruby, Python o JavaScript, 
es posible que no esté acostumbrado a compilar y ejecutar un programa en pasos 
separados. Rust es un lenguaje *compilado con anticipación*, lo que significa que 
puede compilar un programa y darle el ejecutable a otra persona, y ellos pueden 
ejecutarlo incluso sin tener Rust instalado. Si le da a alguien un archivo *.rb*, 
*.py* o *.js*, debe tener instalada una implementación de Ruby, Python o JavaScript 
(respectivamente). Pero en esos lenguajes, solo necesita un comando para compilar y 
ejecutar su programa. Todo es una compensación en el diseño del lenguaje. 

Solo compilar con `rustc` está bien para programas simples, pero a medida que su 
proyecto crezca, querrá administrar todas las opciones y facilitar el intercambio 
de su código. A continuación, le presentaremos la herramienta Cargo, que le ayudará 
a escribir programas de Rust del mundo real. 

[troubleshooting]: ch01-01-installation.html#troubleshooting
