

## Para clonar un repositorio utilizando HTTPS desde GitHub, sigue estos pasos:

1. Ve al repositorio que deseas clonar en GitHub.
2. Haz clic en el botón "Code" (código) que se encuentra arriba de la lista de archivos del repositorio.
3. Selecciona "HTTPS" como opción de clonación.
4. Copia la URL HTTPS que se muestra.
5. Abre la terminal en tu sistema local.
6. Navega hasta la ubicación en la que deseas clonar el repositorio.
7. Escribe el siguiente comando para clonar el repositorio:

   ```
   git clone [URL HTTPS del repositorio]
   ```

   Por ejemplo:

   ```
   git clone https://github.com/tu-usuario/tu-repositorio.git
   ```

8. Presiona Enter para ejecutar el comando.

El repositorio se clonará en tu sistema local. Si el repositorio es privado, se te pedirá que ingreses tus credenciales de GitHub para autenticarte antes de que se te permita clonarlo.


## Abre el repositorio usando vscode

1. En la terminal navega al directorio del repositorio con el comando 

```
cd <nombre del repositorio>
```

2. Escribe el siguiente comando para abrir visual studio code

```
code .
```