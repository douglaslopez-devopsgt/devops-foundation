# devops-foundation


Para realizar este tutorial es necesario tener instalado java jdk, maven y vscode

## Instalacion de Visual Studio Code

Para instalar Visual Studio Code en Windows, sigue estos pasos:

1. Ve al sitio web oficial de Visual Studio Code en https://code.visualstudio.com/.

2. Haz clic en el botón "Descargar" para descargar el instalador de Visual Studio Code para Windows.

3. Una vez descargado el archivo de instalación, haz doble clic en él para iniciar el proceso de instalación.

4. Se abrirá el asistente de instalación de Visual Studio Code. Haz clic en "Siguiente" para continuar.

5. Acepta los términos del acuerdo de licencia y haz clic en "Siguiente".

6. Elige la ubicación donde deseas instalar Visual Studio Code o simplemente deja la ubicación predeterminada y haz clic en "Siguiente".

7. En la siguiente pantalla, puedes elegir si quieres crear accesos directos en el menú de inicio y en el escritorio. Selecciona las opciones deseadas y haz clic en "Siguiente".

8. Finalmente, haz clic en "Instalar" para iniciar la instalación de Visual Studio Code en tu sistema.

9. Espera a que se complete la instalación. Una vez finalizada, marca la casilla "Ejecutar Visual Studio Code" y haz clic en "Finalizar".

¡Listo! Ahora tienes Visual Studio Code instalado en tu sistema Windows. Puedes ejecutarlo desde el menú de inicio o desde el acceso directo en el escritorio.


## Como instalar java y maven

Para instalar el JDK de Java y Maven en Windows, sigue estos pasos:

1. Instalar el JDK de Java:
   - Ve al sitio web de Oracle (https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) y descarga la última versión del JDK de Java.
   - Asegúrate de seleccionar la versión adecuada para tu sistema operativo Windows (por ejemplo, Windows x64 si tienes un sistema operativo de 64 bits).
   - Ejecuta el archivo de instalación descargado y sigue las instrucciones del instalador.
   - Durante la instalación, elige la ubicación donde deseas instalar el JDK. Toma nota de esta ubicación, ya que la necesitarás más adelante.

2. Configurar las variables de entorno:
   - Haz clic derecho en "Equipo" o "Este equipo" en el menú Inicio y selecciona "Propiedades".
   - En la ventana de propiedades del sistema, ve a la pestaña "Configuración avanzada del sistema".
   - Haz clic en el botón "Variables de entorno".
   - En la sección "Variables del sistema", busca la variable "Path" y haz clic en "Editar".
   - Agrega la ruta de instalación del JDK al valor de la variable "Path" agregando ";<ruta de instalación del JDK>\bin" al final. Por ejemplo, si instalaste el JDK en "C:\Program Files\Java\jdk-11.0.2", deberías agregar ";C:\Program Files\Java\jdk-11.0.2\bin".
   - Haz clic en "Aceptar" para guardar los cambios.

3. Verificar la instalación:
   - Abre una nueva ventana de línea de comandos (CMD) o reinicia la que ya tenías abierta.
   - Ejecuta el comando "java -version" para verificar que el JDK de Java se haya instalado correctamente. Deberías ver la versión de Java instalada en tu sistema.

4. Instalar Maven:
   - Ve al sitio web oficial de Apache Maven (https://maven.apache.org/download.cgi) y descarga la última versión de Maven.
   - Elige el archivo binario zip y descárgalo.
   - Crea una carpeta en tu sistema donde deseas instalar Maven. Por ejemplo, puedes crear una carpeta llamada "apache-maven" en la unidad C:.
   - Extrae el contenido del archivo zip descargado en la carpeta que creaste.
   - Toma nota de la ubicación de la carpeta de Maven, ya que la necesitarás más adelante.

5. Configurar las variables de entorno de Maven:
   - Sigue los mismos pasos 2 y 3 descritos anteriormente para configurar las variables de entorno.
   - Agrega una nueva variable de entorno llamada "M2_HOME" y establece su valor como la ubicación de la carpeta de Maven. Por ejemplo, si la carpeta de Maven está en "C:\apache-maven", entonces el valor de "M2_HOME" debería ser "C:\apache-maven".
   - Busca la variable "Path" en la sección "Variables del sistema" y haz clic en "Editar".
   - Agrega "%M2_HOME%\bin" al valor de la variable "Path". Por ejemplo, si "M2_HOME" es "C:\apache-maven", entonces deberías agregar ";C:\apache-maven\bin".
   - Haz clic en "Aceptar" para guardar los cambios.

6. Ver

ificar la instalación de Maven:
   - Cierra la ventana de línea de comandos actual y abre una nueva ventana de línea de comandos.
   - Ejecuta el comando "mvn -version" para verificar que Maven se haya instalado correctamente. Deberías ver la versión de Maven instalada en tu sistema.

¡Listo! Ahora tienes instalado el JDK de Java y Maven en tu sistema Windows. Puedes comenzar a utilizar Maven para gestionar tus proyectos de desarrollo de software en Java.