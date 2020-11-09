# Path Traversal 
----

## Descripción
----
La técnica de ataque Path Traversal permite a un atacante acceder a los archivos, 
directorios y comandos que potencialmente residen fuera del directorio raíz de 
documentos web. Un atacante puede controlar una URL de tal forma que el sitio web e
jecutará o mostrará la información de los archivos que son arbitrarios en cualquier p
arte del servidor web. Cualquier dispositivo que se exponga a una interfaz que se basa 
en HTTP es potencialmente vulnerable a un Path Traversal.

La mayoria de los sitios web prohíben el acceso de los usuarios a algún sitio específico 
del sistema de los archivos, normalmente denominado directorio "raíz del documento web" o "
raíz CGI". Estos directorios poseen los archivos que estan destinados al acceso del usuario 
y el ejecutable que es necesario para poder controlar la funcionalidad correcta de la aplicación 
web. Para poder ingresar a los archivos o activar los comandos en cualquier zona del sistema de 
los archivos, los ataques de trayectoria de rutas van a utilizar la capacidad de las secuencias 
de todos los caracteres especiales.

El ataque Path Traversal más elemental utiliza la secuencia de los caracteres especiales 
"../" para poder modificar la ubicación del recurso que es requerido en la URL. Aunque la 
gran mayoría de los servidores web que son populares van a evitar que esta técnica se escape 
de la raíz del documento web, las codificaciones que son alternativas de la secuencia "../" pueden 
impedir los filtros de seguridad. These method variations include valid and invalid Unicode-encoding 
("..%u2216" or "..%c0%af") of the forward slash character, backslash characters ("..\") on Windows-based 
servers, URL encoded characters "%2e%2e%2f"), and double URL encoding ("..%255c") of the backslash character.

Inclusive si el servidor web impide de forma correcta los intentos de trayectoria en la ruta de la URL, 
una aplicación web en sí misma puede ser muy vulnerable provocado por el manejo de forma incorrecta de 
la entrada que fue proporcionada por el usuario. Este es un problema muy común de las aplicaciones web
que utilizan los mecanismos de plantilla o cargan algún texto estático de los archivos. En las variaciones 
de los ataques, el valor del parámetro de la URL original se modifica por el nombrede uno de los archivos 
de órdenes dinámicos de la aplicación web. Provocando que, los resultados puedan mostrar el código fuente 
porque el archivo se interpreta como un texto en vez de como un archivo de órdenes ejecutable. Estás técnicas 
muchas veces utilizan caracteres especiales extras, como el punto (".") para poder revelar la lista del directorio 
de trabajo actual, o los caracteres que son NULOS "%00 para poder evadir las verificaciones elementales de
la extensión de los archivos.


Solución
---------


Asuma que toda la entrada es maliciosa. Utilice una estrategia de validación de entrada "aceptar bien conocidos", 
es decir, utilice alguna lista blanca de entradas aceptables que se ajuste de forma estricta a las especificaciones. 
Rechace cualquier entrada que no se adapte de forma estricta a las especificaciones, o cambielas por algo que sí 
lo haga. No confíe solamente en la búsqueda de entradas maliciosas o malformadas (es decir, no confíe en una lista 
negra). Sin embargo, las listas negras pueden ser muy útiles para detectar posibles ataques o diagnosticar que entradas 
están tan malformadas que se deberían rechazar directamente.

Al realizar la validación de entrada, usted debe considerar todas las propiedades potencialmente destacadas, incluida 
la longitud, el tipo de entrada, el rango completo de valores aceptables, las entradas faltantes o adicionales, la 
sintaxis, el sentido entre los campos que se encuentran relacionados y la conformidad con todas las reglas comerciales. 
Como un ejemplo de lógica de las reglas comerciales, "bote" puede ser válido de forma sintáctica porque solo posee 
caracteres que son alfanuméricos, pero no es válido si está esperando los colores como "rojo" o "azul". 

Para los nombres de los archivos, utilice las listas blancas que son estrictas y que limiten el grupo de caracteres 
que se van a utilizar. Si es posible, solo permita un solo carácter "." en el nombre del archivo para poder prevenir 
las vulnerabilidades y rechazar los separadores de directorios como por ejemplo "/". Utilice una lista blanca de las 
extensiones del archivo que sea permitida.

Advertencia: si usted intenta limpiar sus datos, tiene que hacerlo para que el resultado final no esté en la forma en 
el que estos puedan ser un peligro. Un mecanismo para desinfectar puede provcar la eliminación de caracteres como por 
ejemplo "." y ";" que pueden ser necesitados para varias explociones. Un atacante puede intentar burlar al mecanismo 
de desinfección para que este "limpie" los datos de una forma que puede ser muy peligrosa. Supongamos que el atacante 
logra inyectar un "." dentro de un nombre de un archivo (por ejemplo, "archivo sensi.tive") y el mecanismo que se encarga 
de desinfectar elimina el carácter que da como resultado que el nombre del archivo válido sea, "archivo sensible". Si ahora 
suponemos que los datos de entrada son seguros, entonces el archivo tiene la posibilidad de verse comprometido. 

Las entradas se deben decodificar y canonicalizar a la representación que se encuentra actualmente de manera interna de la aplicación antes de validarlas. Asegúrese de que su aplicación no pueda descodificar la misma entrada dos veces. Dichos errores podrían utilizarse para evadir los esquemas de la lista blanca ingresando entradas muy peligrosas luego de que se hayan verificado.

Utilice alguna función de canonicalización de una ruta que fue incorporada (como realpath() en C) la cual origina la versión canónica de la ruta de acceso, que produce la eliminación de forma efectiva de las secuencias ".." y los enlaces que son simbólicos.

Ejecute su codigo utilizando los privilegios más bajos que se necesitan para poder realizar todas las tareas que son necesarias. Si es posible, cree unas cuentas que se encuentren aisladas con provilegios limitados que solo se utilizan para una sola tarea. De esta forma, un ataque que sea exitoso no le proporcionará al atacante el acceso de forma inmediata al resto del software o su dominio. Por ejemplo, las aplicaciones de las bases de datos muy pocas veces requieren ejecutarse como el administrador de la base de datos, en especial en las operaciones que son cotidianas.

Cuando el grupo de los objetos que son aceptados, como nombre de los archivos o URL, es limitado o conocido, tiene que crear una asignación de un grupo de valores de entradas que son fijos (como ID numéricos) a los nombres de los archivos o URL que son reales, y además tiene que rechazar todas las otras entradas.

Ejecute su código en un dominio de "cárcel" o un dominio que sea similar el cual imponga los límites estrictos entre el proceso y el sistema operativo. Esto puede ser que restrinja de forma efectiva a qué archivos se pueden ingresar en un directorio particular o qué comandos puede utilizar su software.

Los ejemplos de niveles de sistema operativo incluyen el Unix chroot jail, AppArmor, and SELinux. Normalmente, el código proporcionado puede otorgar cierta protección. Por ejemplo, java.io.FilePermission en Java SecurityManager le permite especificar las restricciones en las operaciones de archivos.

Esto puede que no sea la solución viable, y solo limita el impacto al sistema operativo; el resto de tu aplicación puede estar expuesta.



