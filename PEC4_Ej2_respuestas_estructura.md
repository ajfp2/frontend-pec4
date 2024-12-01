# Ejercicio 2 – Hola Mundo con Angular (1.25 punto)

1. (0.75 puntos) ¿Qué comando debes utilizar para crear un nuevo proyecto Angular utilizando Angular CLI denominado ecommerce? `ng new ecommerce` o para la v19 de angular `ng new ecommerce --no-strict --standalone=false` para hacerlo como se pide en la PEC.
Con Angular Cli crea el proyecto angular ecommerce y explica brevemente la estructura y ficheros que ha generado Angular CLI:

    + Ficheros de configuración en la raíz del proyecto:
      + `tsconfig.app.json`: Contiene la configuración mas particular de la App
      + `tsconfig.json`: Tiene la configuración general de Typescript
      + `angular.json`: Contiene la configuración del proyecto
      + `package.json`: Es el responsable de mantener los metadatos sobre los paquetes/bibliotecas que usa como dependencias.
      + `package.lock.json`: Mantiene el historial de los paquetes/bibliotecas instaladas y optimiza de forma en que se generan las dependencias del proyecto. y los contenidos de la carpeta /node_modules.
      + `.editorconfig`: Es para el editor de texto, para definir estilos de codificación y permite a los editores leer el formato de archivo y cumplir con los estilos definidos.
      + `.gitignore`: Es para indicar a git que archivos o directorios debe obiar.
    + Directorio `/node_modules`: Carpeta donde se instalan las dependencias(paquetes, bibliotecas) del proyecto.
    + Directorio `/src`:
      + `index.hmtl`: Archivo de entrada de nuestro proyecto, aqui se define `<app-root></app-root>` que es el marcador para cargar el código de nuestra aplicación.
      + `main.ts`: Decide que archivos se deben cargar, identifica que módulo angular carga cuando se inicia la aplicación.
      + `style.css`: Hoja de estilos generales para toda la app
      + Directorio `/assets`: En la versión v19 no se crea este directorio, pero era para imagenes, o plantillas css ...
      + Directorio `/app`: Código del proyecto.
        + `app.component.*`: Arhivos que impulsan la funcionalidad de la app y son los principales.
        + `app.module.ts`: Archivo de configuración principal del proyecto, carga desde las dependencias necesarias, declara los componentes que se utilizarán en la aplicación y es el punto de entrada de la app.


2. (0.25 puntos) Explica cada uno de los siguientes decoradores generados por Angular CLI, detallando cada una de las propiedades que se definen en:
    + app.module.ts- @NgModule (declarations, imports, providers, bootstrap):
      + NgModule: Typescript marca la definición de la clase como un modulo angular
      + declarations: Marca que componentes y directivas podemos utilizar dentro de la app.
      + imports: Importa otros modulos para proporcionar funcionalidad a la app.
      + providers:
      + bootstrap: El punto de entrada para iniciar la app.
    + app.component.ts - @Component (selector, templateUrl, styleUrls).
      + Selector: El seletor DOM que se traduce en una instancia de este componente `<app-root></app-root>`em el index.html.
      + TemplateUrl: La plantilla hmtl que respalda el componente.
      + StyleUrls: Estilo especifico del componente, puede tener mas de un archivo.
  
3. (0.25 puntos) ¿Es posible poder inyectar el template y los estilos en línea de un componente sin necesidad de especificarlos en templateUrl, styleUrls?
    Si que es posible, se hace escribiendo el código dentro de las propiedades `template` y `styles` dentro del decorador `@Component`.
    
    ¿Es recomendable hacer esto?
    Para mi no, porque me gusta separar los códigos por legibilidad, aunque si es un componente que tiene poco html/css se puede hacer.
