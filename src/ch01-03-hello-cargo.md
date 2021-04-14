## ¡Hola, Cargo!

Cargo es el sistema de construcción y el administrador de paquetes de Rust. 
La mayoría de los rustáceos usan esta herramienta para administrar sus 
proyectos de Rust porque Cargo maneja muchas tareas por usted, como construir 
su código, descargar las bibliotecas de las que depende su código y construir 
esas bibliotecas. (Llamamos a las bibliotecas que su código necesita 
*dependencias*.) 

Los programas de Rust más simples, como el que hemos escrito hasta ahora, no 
tienen dependencias. Entonces, si hubiéramos construido el "¡Hola, mundo!" 
proyecto con Cargo, solo usaría la parte de Cargo que maneja la construcción 
de su código. A medida que escriba programas de Rust más complejos, agregará 
dependencias y, si comienza un proyecto con Cargo, será mucho más fácil 
agregar dependencias. 

Debido a que la gran mayoría de los proyectos de Rust usan Cargo, el resto de 
este libro asume que tú también estás usando Cargo. Cargo viene instalado con 
Rust si usó los instaladores oficiales discutidos en la sección 
["Instalación"][installation] <!-- ignore -->. Si instaló Rust por otros 
medios, verifique si Cargo está instalado ingresando lo siguiente en su 
terminal: 

```console
$ cargo --version
```

Si ve un número de versión, ¡lo tiene! Si ve un error, como `comando no 
encontrado`, consulte la documentación de su método de instalación para 
determinar cómo instalar Cargo por separado. 

### Crear un proyecto con Cargo 

Creemos un nuevo proyecto con Cargo y observemos en qué se diferencia 
de nuestro "¡Hola, mundo!" Original. proyecto. Vuelve a tu directorio 
de *proyectos* (o donde hayas decidido almacenar tu código). Luego, en 
cualquier sistema operativo, ejecute lo siguiente: 

```console
$ cargo new hola_cargo
$ cd hola_cargo
```

El primer comando crea un nuevo directorio llamado *hola_cargo*. Hemos 
llamado a nuestro proyecto *hola_cargo*, y Cargo crea sus archivos en 
un directorio con el mismo nombre. 

Vaya al directorio *hola_cargo* y enumere los archivos. Verá que Cargo 
ha generado dos archivos y un directorio para nosotros: un archivo 
*Cargo.toml* y un directorio *src* con un archivo *main.rs* adentro. 

También ha inicializado un nuevo repositorio de Git junto con un 
archivo *.gitignore*.
Los archivos Git no se generarán si ejecuta `cargo new` dentro de un 
repositorio Git existente; puedes anular este comportamiento usando 
`cargo new --vcs = git`. 

> Nota: Git es un sistema de control de versiones común. Puede cambiar 
`cargo new` para usar un sistema de control de versiones diferente o 
ningún sistema de control de versiones usando la bandera` --vcs`. 
Ejecute `cargo new --help` para ver las opciones disponibles. 

Abra *Cargo.toml* en el editor de texto que prefiera. Debería verse 
similar al código del Listado 1-2. 

<span class="filename">Nombre de fichero: Cargo.toml</span>

```toml
[package]
name = "hola_cargo"
version = "0.1.0"
authors = ["Your Name <you@example.com>"]
edition = "2018"

[dependencies]
```

<span class="caption">Listado 1-2: Contenido de *Cargo.toml* generado por `cargo
new` </span>

Este archivo está en el formato [*TOML*](https://toml.io) <!-- ignore --> 
(*Tom's Obvious, Minimal Language*), que es el formato de configuración de Cargo. 

La primera línea, `[package]`, es un encabezado de sección que indica que las 
siguientes declaraciones están configurando un paquete. A medida que agreguemos 
más información a este archivo, agregaremos otras secciones. 

Las siguientes cuatro líneas establecen la información de configuración que Cargo 
necesita para compilar su programa: el nombre, la versión, quién lo escribió y la 
edición de Rust que debe usar. Cargo obtiene su nombre y la información de correo 
electrónico de su entorno, por lo que si esa información no es correcta, corrija 
la información ahora y luego guarde el archivo. Hablaremos sobre la clave de 
"edición" en el Apéndice E. 

La última línea, `[dependencies]`, es el comienzo de una sección para que enumere 
cualquiera de las dependencias de su proyecto. En Rust, los paquetes de código se 
denominan *crates*. No necesitaremos otras crates para este proyecto, pero lo 
haremos en el primer proyecto del Capítulo 2, por lo que usaremos esta sección de 
dependencias. 

Ahora abra *src/main.rs* y eche un vistazo: 

<span class="filename">Nombre de Fichero: src/main.rs</span>

```rust
fn main() {
    println!("¡Hola, mundo!");
}
```

Cargo ha generado un "¡Hola, mundo!" programa para usted, como el que 
escribimos en el Listado 1-1. Hasta ahora, las diferencias entre nuestro 
proyecto anterior y el proyecto que genera Cargo son que Cargo colocó el 
código en el directorio *src* y tenemos un archivo de configuración 
*Cargo.toml* en el directorio superior. 

Cargo espera que sus archivos fuente vivan dentro del directorio *src*. El 
directorio del proyecto de nivel superior es solo para archivos README, 
información de licencia, archivos de configuración y cualquier otra cosa que 
no esté relacionada con su código. El uso de Cargo le ayuda a organizar sus 
proyectos. Hay un lugar para todo y todo está en su lugar. 

Si comenzó un proyecto que no usa Cargo, como hicimos con el proyecto 
"¡Hola, mundo!", puede convertirlo en un proyecto que utilice Cargo. Mueva 
el código del proyecto al directorio *src* y cree un archivo *Cargo.toml* 
apropiado. 

### Construcción y ejecución de un proyecto de Cargo 

Ahora veamos qué es diferente cuando creamos y ejecutamos el programa 
"¡Hola, mundo!" programa con Cargo! Desde su directorio *hola_cargo*, cree 
su proyecto ingresando el siguiente comando: 

```console
$ cargo build
   Compiling hola_cargo v0.1.0 (file:///projects/hola_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 2.85 secs
```

Este comando crea un archivo ejecutable en *target/debug/hola_cargo* 
(o *target\debug\hola_cargo.exe* en Windows) en lugar de en su directorio 
actual. Puede ejecutar el ejecutable con este comando: 

```console
$ ./target/debug/hola_cargo # o .\target\debug\hola_cargo.exe en Windows
¡Hola, mundo!
```

Si todo va bien, `¡Hola, mundo!` Debería imprimirse en la terminal. Ejecutar 
`cargo build` por primera vez también hace que Cargo cree un nuevo archivo 
en el nivel superior: *Cargo.lock*. Este archivo realiza un seguimiento de 
las versiones exactas de las dependencias en su proyecto. Este proyecto no 
tiene dependencias, por lo que el archivo es un poco escaso. Nunca 
necesitará cambiar este archivo manualmente; Cargo gestiona su contenido por 
usted. 

Acabamos de construir un proyecto con `cargo build` y lo ejecutamos con 
`./Target/debug/hello_cargo`, pero también podemos usar `cargo run` para 
compilar el código y luego ejecutar el ejecutable resultante todo en un 
comando: 

```console
$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.0 secs
     Running `target/debug/hola_cargo`
¡Hola, mundo!
```

Observe que esta vez no vimos resultados que indicaran que Cargo estaba 
compilando `hola_cargo`. Cargo descubrió que los archivos no habían 
cambiado, por lo que simplemente ejecutó el binario. Si hubiera modificado 
su código fuente, Cargo habría reconstruido el proyecto antes de 
ejecutarlo y habría visto este resultado: 

```console
$ cargo run
   Compiling hola_cargo v0.1.0 (file:///projects/hola_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.33 secs
     Running `target/debug/hola_cargo`
¡Hola, mundo!
```

Cargo también proporciona un comando llamado `cargo check`. Este comando 
verifica rápidamente su código para asegurarse de que se compila pero no 
produce un ejecutable: 

```console
$ cargo check
   Checking hola_cargo v0.1.0 (file:///projects/hola_cargo)
    Finished dev [unoptimized + debuginfo] target(s) in 0.32 secs
```

¿Por qué no querrías un ejecutable? A menudo, `cargo check` es mucho más 
rápido que `cargo build`, porque omite el paso de producir un ejecutable. 
Si está comprobando continuamente su trabajo mientras escribe el código, 
¡el uso de `cargo check` acelerará el proceso! Como tal, muchos rustáceos 
ejecutan `cargo check` periódicamente mientras escriben su programa para 
asegurarse de que se compile. Luego ejecutan `cargo build` cuando están 
listos para usar el ejecutable. 

Recapitulemos lo que hemos aprendido hasta ahora sobre Cargo: 

* Podemos construir un proyecto usando `cargo build`. 
* Podemos construir y ejecutar un proyecto en un solo paso usando "cargo run". 
* Podemos construir un proyecto sin producir un binario para verificar errores 
  usando `cargo check`. 
* En lugar de guardar el resultado de la compilación en el mismo directorio 
  que nuestro código, Cargo lo almacena en el directorio *target/debug*. 

Una ventaja adicional de usar Cargo es que los comandos son los mismos sin 
importar en qué sistema operativo esté trabajando. Entonces, en este punto, ya 
no brindaremos instrucciones específicas para Linux y macOS en comparación con 
Windows. 

### Construir para Lanzamiento

Cuando su proyecto finalmente esté listo para su lanzamiento, puede usar 
`cargo build --release` para compilarlo con optimizaciones. Este comando creará 
un ejecutable en *target/release* en lugar de *target/debug*. Las 
optimizaciones hacen que su código de Rust se ejecute más rápido, pero 
activarlas alarga el tiempo que tarda su programa en compilarse. Es por eso que 
hay dos perfiles diferentes: uno para desarrollo, cuando desea reconstruir 
rápidamente y con frecuencia, y otro para construir el programa final que le 
dará a un usuario que no se reconstruirá repetidamente y que se ejecutará tan 
rápido como posible. Si está comparando el tiempo de ejecución de su código, 
asegúrese de ejecutar `cargo build --release` y compare con el ejecutable en 
*target/release*. 

### Cargo como Convención 

Con proyectos simples, Cargo no proporciona mucho valor con respecto al uso de 
`rustc`, pero demostrará su valor a medida que sus programas se vuelvan más 
complejos.
Con proyectos complejos compuestos por varias cajas, es mucho más fácil dejar 
que Cargo coordine la construcción. 

Aunque el proyecto `hola_cargo` es simple, ahora usa muchas de las herramientas 
reales que usará en el resto de su carrera en Rust. De hecho, para trabajar en 
cualquier proyecto existente, puede usar los siguientes comandos para verificar 
el código usando Git, cambiar al directorio de ese proyecto y compilar: 

```console
$ git clone example.org/someproject
$ cd someproject
$ cargo build
```

Para obtener más información sobre Cargo, consulte [its documentation]

[its documentation]: https://doc.rust-lang.org/cargo/

## Resumen 

¡Ya ha tenido un gran comienzo en su viaje por Rust! En este capítulo, 
ha aprendido a: 

* Instale la última versión estable de Rust usando `rustup`.
* Actualice a una versión más reciente de Rust.
* Abrir documentación instalada localmente.
* Escribe y ejecuta un programa "¡Hola, mundo!" usando `rustc` directamente.
* Cree y ejecute un nuevo proyecto utilizando las convenciones de Cargo.

Este es un buen momento para construir un programa más sustancial para 
acostumbrarse a leer y escribir código Rust. Entonces, en el Capítulo 2, 
crearemos un programa de juego de adivinanzas.
Si prefiere comenzar por aprender cómo funcionan los conceptos de 
programación comunes en Rust, consulte el Capítulo 3 y luego regrese al 
Capítulo 2. 

[installation]: ch01-01-installation.html#installation
