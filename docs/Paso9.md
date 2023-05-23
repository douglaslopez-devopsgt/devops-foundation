

Para crear un token de GitHub para crear releases y luego guardarlo como un secreto de Actions, sigue estos pasos:

1. Ve a la página de configuración de tu cuenta de GitHub y haz clic en "Developer settings".

2. En la barra lateral izquierda, haz clic en "Personal access tokens".

3. Haz clic en "Generate new token".

4. Escribe un nombre descriptivo para el token en "Note".

5. Seleccione los permisos necesarios para crear releases. En este caso, debes seleccionar al menos "repo".

6. Haz clic en "Generate token".

7. Copia el token generado. Este es el único momento en el que podrás ver el token completo, por lo que asegúrate de guardarlo en un lugar seguro.

8. Vuelve a tu repositorio en GitHub y haz clic en la pestaña "Settings".

9. En la barra lateral izquierda, haz clic en "Secrets".

10. Haz clic en "New secret".

11. Escribe un nombre descriptivo para el secreto en "Name". Por ejemplo, "GITHUB_TOKEN".

12. Pega el token que copiaste anteriormente en "Value".

13. Haz clic en "Add secret".

14. El secreto se guardará y se podrá utilizar en tus acciones de GitHub como `${{ secrets.GITHUB_TOKEN }}`.

Ahora, puedes utilizar este secreto en tus acciones de GitHub para crear releases sin tener que incluir el token directamente en el archivo de acción.

## Construir Github action

Para crear un GitHub Action que construya una release de un archivo jar usando Gradle y Spring Boot, puedes seguir los siguientes pasos:

1. Crea un archivo de flujo de trabajo de GitHub Actions en tu repositorio. Puedes hacer esto haciendo clic en la pestaña "Acciones" en tu repositorio y luego haciendo clic en el botón "Nuevo flujo de trabajo". Dale un nombre descriptivo a tu flujo de trabajo y guarda el archivo como `nombre-del-archivo.yml` en la carpeta `.github/workflows/` de tu repositorio.

2. Define las propiedades básicas del flujo de trabajo, como la versión de la plataforma de ejecución y el evento que activará el flujo de trabajo. Por ejemplo, si quieres activar el flujo de trabajo cuando se empuja una nueva versión de código a la rama principal (`main`), puedes usar lo siguiente:

```
name: Crear Release de Jar
on:
  push:
    branches: [ main ]
```

3. Define los trabajos que se ejecutarán en el flujo de trabajo. Puedes definir uno o más trabajos, según sea necesario. Por ejemplo, si solo necesitas construir el archivo jar, puedes definir un trabajo como este:

```
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v2
    - name: Build Jar
      run: ./gradlew bootJar
```

4. El primer paso (`actions/checkout@v2`) clona tu repositorio en la máquina virtual que se ejecuta el flujo de trabajo. El segundo paso (`Build Jar`) ejecuta el comando `./gradlew bootJar` que construirá el archivo jar y lo colocará en el directorio `build/libs` del proyecto.

5. Si quieres agregar la acción para que también cree una release, puedes agregar otro paso que use el comando `create-release` de la API de GitHub. Por ejemplo:

```
- name: Crear Release
      id: create_release
      uses: actions/create-release@v1
      env:
        GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      with:
        tag_name: v1.0.0
        release_name: Release 1.0.0
        body: |
          Descripción de la release
        draft: false
        prerelease: false
    - name: Subir archivo Jar
      uses: actions/upload-artifact@v2
      with:
        name: build
        path: build/libs/*.jar
```

6. El paso `create-release` crea una nueva release en GitHub y `upload-artifact` sube el archivo jar generado por Gradle en el paso anterior.

7. Asegúrate de agregar el token de acceso a GitHub (`GITHUB_TOKEN`) como una variable de entorno. Puedes hacer esto en la sección "Secretos" de tu repositorio. 

Una vez que hayas guardado el archivo de flujo de trabajo en tu repositorio, el flujo de trabajo se ejecutará automáticamente cuando se empuje una nueva versión de código a la rama principal (`main`). La acción construirá el archivo jar y lo colocará en el directorio `build/libs`, y también creará una nueva release en GitHub y cargará el archivo jar como un artefacto.


## Para hacer un commit y un push a tu repositorio en Visual Studio Code, sigue estos pasos:

1. Abre el proyecto en Visual Studio Code.
2. Abre la sección de "Source Control" haciendo clic en el icono correspondiente en la barra lateral izquierda.
3. Haz clic en la sección "Changes" para ver los cambios que has realizado en tu proyecto.
4. Agrega los cambios que deseas confirmar haciendo clic en el signo "+" junto a cada archivo modificado o añadido. También puedes hacer clic en el botón "+ All" para agregar todos los cambios.
5. Escribe un mensaje descriptivo del commit en el cuadro de texto "Message" en la parte superior de la sección "Changes".
6. Haz clic en el botón "✓" para hacer el commit. 
7. Ahora, para hacer un push, haz clic en el botón "..." en la sección "Changes" y selecciona "Push" en el menú desplegable.
8. Si es necesario, ingresa tus credenciales de GitHub o de otra plataforma de alojamiento de repositorios.
9. Espera a que se complete el proceso de push.
