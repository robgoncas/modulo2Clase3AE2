
# Configuración de Live Sass Compiler en Visual Studio Code

## Paso 1: Instalar Visual Studio Code

1. Si no lo tienes instalado, descarga e instala [Visual Studio Code](https://code.visualstudio.com/).

## Paso 2: Instalar Live Sass Compiler

1. Abre Visual Studio Code.
2. Ve a la pestaña de extensiones (ícono de cuadrados en la barra lateral izquierda o presiona `Ctrl + Shift + X`).
3. Busca **Live Sass Compiler**.
4. Haz clic en **Instalar**.

## Paso 3: Crear un Proyecto y Archivos SCSS/SASS

1. Crea una nueva carpeta para tu proyecto.
2. Abre esta carpeta en Visual Studio Code (`File > Open Folder`).
3. Crea un nuevo archivo SCSS en tu proyecto, por ejemplo: `styles.scss`.

## Paso 4: Configurar la Compilación

Para configurar la compilación automática, necesitarás modificar tu archivo `settings.json`.

1. Presiona `Ctrl + Shift + P` para abrir la paleta de comandos.
2. Escribe `Preferences: Open Settings (JSON)` y selecciona la opción.
3. Agrega o modifica las siguientes configuraciones en el archivo `settings.json`:

   ```json
   {
       //Otras configuraciones
       "liveSassCompile.settings.formats": [
           {
               "format": "expanded",
               "extensionName": ".css",
               "savePath": "/css"
           }
       ],
       //Incluir todos los archivos SCSS en el proyecto
       "liveSassCompile.settings.includeItems": [
           "**/*.scss" 
       ],
        //Excluir archivos CSS de la compilación
       "liveSassCompile.settings.excludeItems": [
           "**/*.css" 
       ],
       //Autoprefixer
       "liveSassCompile.settings.autoprefix": ["> 1%", "last 2 versions"], 
   }
   ```

### Explicación de la Configuración

- **formats**: Define cómo se debe compilar el archivo SCSS. En este caso, se usa el formato `expanded` y se guarda en la carpeta `css`.
- **includeItems**: Define qué archivos deben incluirse en la compilación (todos los archivos SCSS en este caso).
- **excludeItems**: Define qué archivos deben excluirse de la compilación (en este caso, todos los archivos CSS).
- **autoprefix**: Configura Autoprefixer para añadir prefijos a las propiedades CSS según los navegadores definidos.

## Paso 5: Compilar SCSS a CSS

1. Abre tu archivo `styles.scss`.
2. En la esquina inferior derecha de Visual Studio Code, deberías ver un botón que dice "Watch Sass" o "Watch SCSS". Haz clic en él.
3. Cada vez que guardes cambios en tu archivo `styles.scss`, el archivo CSS correspondiente se generará automáticamente en la carpeta `css`.

## Paso 6: Verifica la Compilación

1. Crea un archivo HTML, por ejemplo: `index.html`.
2. Incluye el archivo CSS generado en tu HTML:

   ```html
   <!DOCTYPE html>
   <html lang="es">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <link rel="stylesheet" href="css/styles.css"> <!-- Asegúrate de que la ruta sea correcta -->
       <title>Mi Proyecto SCSS</title>
   </head>
   <body>
       <h1>¡Hola, mundo!</h1>
   </body>
   </html>
   ```

## Paso 7: Probar en el Navegador

1. Abre el archivo `index.html` en tu navegador para ver los estilos aplicados.

## Consejos Adicionales

- **Recargar el Navegador**: Cada vez que hagas cambios en el SCSS y guardes, asegúrate de recargar el navegador para ver los cambios reflejados.
- **Errores de Compilación**: Si hay errores en el archivo SCSS, Live Sass Compiler te mostrará un mensaje en la parte inferior de VS Code.
```
