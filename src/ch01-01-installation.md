## Instalación

El primer paso es instalar Rust. Descargaremos Rust a través de "rustup", una 
herramienta de línea de comandos para administrar las versiones de Rust y las 
herramientas asociadas. Necesitará una conexión a Internet para la descarga. 

> Nota: Si prefiere no utilizar "rustup" por alguna razón, consulte [the Rust 
> installation page](https://www.rust-lang.org/tools/install) para otras opciones.

Los siguientes pasos instalan la última versión estable del compilador de Rust.
Las garantías de estabilidad de Rust aseguran que todos los ejemplos del libro que 
se compilan continuarán compilándose con las versiones más recientes de Rust. 
El resultado puede diferir ligeramente entre versiones, porque Rust a menudo 
mejora los mensajes de error y las advertencias. En otras palabras, cualquier 
versión más nueva y estable de Rust que instale siguiendo estos pasos debería 
funcionar como se esperaba con el contenido de este libro. 

> ### Notación de línea de comando 
>
> En este capítulo y a lo largo del libro, mostraremos algunos comandos utilizados 
> en la terminal. Todas las líneas que debe ingresar en una terminal comienzan con 
> "$". No es necesario que escriba el carácter "$"; indica el inicio de cada 
> comando. Las líneas que no comienzan con "$" suelen mostrar el resultado del 
> comando anterior. Además, los ejemplos específicos de PowerShell usarán `>` en 
> lugar de `$`. 

### Instalación de `rustup` en Linux o macOS 

Si está usando Linux o macOS, abra una terminal e ingrese el siguiente comando: 

```console
$ curl --proto '=https' --tlsv1.2 https://sh.rustup.rs -sSf | sh
```

El comando descarga un script e inicia la instalación de la herramienta `rustup`, 
que instala la última versión estable de Rust. Es posible que se le solicite su 
contraseña. Si la instalación es exitosa, aparecerá la siguiente línea: 

```text
Rust is installed now. Great!
```

Además, necesitará algún tipo de vinculador. Es probable que ya haya uno 
instalado, pero cuando intentas compilar un programa Rust y obtienes errores que 
indican que un vinculador no se pudo ejecutar, eso significa que no hay un 
vinculador instalado en tu sistema y tendrás que instalar uno manualmente. Los 
compiladores de C generalmente vienen con el enlazador correcto. Consulte la 
documentación de su plataforma para saber cómo instalar un compilador de C. Además, 
algunos paquetes comunes de Rust dependen del código C y necesitarán un 
compilador C. Por lo tanto, podría valer la pena instalar uno ahora. 

### Instalación de `rustup` en Windows 

En Windows, vaya a [https://www.rust-lang.org/tools/install][install] y siga las 
instrucciones para instalar Rust. En algún momento de la instalación, recibirá un 
mensaje que le explicará que también necesitará las herramientas de compilación de 
C++ para Visual Studio 2013 o posterior. La forma más sencilla de adquirir las 
herramientas de compilación es instalar [Build Tools for Visual Studio 2019]
[visualstudio]. 
Cuando se le pregunte qué cargas de trabajo instalar, asegúrese de seleccionar 
"Herramientas de compilación de C++" y de que se incluyan el SDK de Windows 10 y 
los componentes del paquete de idioma inglés. 


[install]: https://www.rust-lang.org/tools/install
[visualstudio]: https://visualstudio.microsoft.com/visual-cpp-build-tools/

El resto de este libro utiliza comandos que funcionan tanto en *cmd.exe* como 
en PowerShell.
Si hay diferencias específicas, le explicaremos cuál usar. 

### Actualización y desinstalación 

Después de haber instalado Rust a través de `rustup`, actualizar a la última 
versión es fácil. Desde su shell, ejecute el siguiente script de actualización:

```console
$ rustup update
```

Para desinstalar Rust y `rustup`, ejecute el siguiente script de desinstalación 
desde su shell: 

```console
$ rustup self uninstall
```

### Solución de problemas 

Para verificar si tiene Rust instalado correctamente, abra un shell e ingrese 
esta línea: 

```console
$ rustc --version
```

Debería ver el número de versión, el hash de confirmación y la fecha de 
confirmación de la última versión estable que se ha lanzado en el siguiente 
formato: 

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

Si ve esta información, ¡ha instalado Rust correctamente! Si no ve esta 
información y está en Windows, verifique que Rust esté en su variable de 
sistema "% PATH%". Si todo es correcto y Rust aún no funciona, hay varios 
lugares en los que puede obtener ayuda. El más fácil es el canal #beginners en 
[the official Rust Discord][discord]. Allí, puedes charlar con otros rustáceos 
(un apodo tonto que nos llamamos a nosotros mismos) que pueden ayudarte. Otros 
recursos excelentes incluyen [the Users forum][users] y [Stack Overflow][stackoverflow]. 

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: https://stackoverflow.com/questions/tagged/rust

### Documentación Local 

La instalación de Rust también incluye una copia local de la documentación, 
para que pueda leerla sin conexión. 
Ejecute `rustup doc` para abrir la documentación local en su navegador. 

Siempre que la biblioteca estándar proporcione un tipo o función y no esté 
seguro de qué hace o cómo usarlo, utilice la documentación de la interfaz de 
programación de aplicaciones (API) para averiguarlo. 
