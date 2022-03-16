# INSTITUTO TECNOLÓGICO Y DE ESTUDIOS SUPERIORES DE MONTERREY - CAMPUS ESTADO DE MÉXICO
## TC2005B: CONSTRUCCIÓN DE SOFTWARE Y TOMA DE DECISIONES
## MÓDULO 3: DESARROLLO TECNOLÓGICO Y DESARROLLO WEB
## PRIMERA EVALUACIÓN PARCIAL
## PROF. MARCIANO ALBERTO MORENO DÍAZ COVARRUBIAS


## Introducción
Esta primera evaluación parcial abarca los siguientes conceptos:
* Node.js
* HTML
* CSS
* TypeScript
* Git y GitHub

## Requisitos
* Computadora personal con conectividad a Internet.
* Cuenta de GitHub dada de alta en el classroom de GitHub for Education del grupo.
* Enlace de la asignación en el classroom de GitHub for Education correspondiente al examen.

## Procedimiento
* Abre un navegador de Internet y autentícate en GitHub con la cuenta que tienes dada de alta para las asignaciones de la clase.
* Navega al enlace del examen (asignación en el classroom de GitHub for Education) y acepta la asignación.
* Navega al repositorio del examen (provisto al final del paso anterior).
* Crea e inicia un Codespace del repositorio del examen (Machine type: 2 cores). 
  * Opcionalmente podrás responder al examen clonando el repositorio a tu ambiente de desarrollo local el cual deberá contar con ambiente integrado de desarrollo, instalación de Node.js con las herramientas node y npm, capacidad de instalar paquetes externos de Node.js por medio de Node Package Manager (npm).
* Lleva a cabo las actividades descritas en el archivo README.md.
* Verifica que el código implementado cumpla con los requerimientos. Asegúrate que los archivos estén guardados.
* Por cada actividad completada del examen, registra los cambios de los archivos en el sistema de control de versiones local (commit) y publícalos al respositorio remoto (push).
* Envía un correo con título: "\<NUM_GRUPO\>-\<MATRICULA\>:Primer examen parcial", en el cuerpo del correo incluye el enlace al repositorio de tu examen al correo del Tec de tu profesor. 
  * Título de ejemplo: 400-AL123456: Enlace a primer examen parcial.
  * Correo: marciano.moreno [arroba] tec.mx.

## Duración del examen
100 minutos

## Horario del examen
El examen iniciará al minuto 10 de la hora calendarizada de inicio la clase (p.e. para la hora de inicio de las 8:00 el examen iniciará a las 8:10).

El examen concluirá 10 minutos antes de la hora calendarizada de fin de la clase (p.e. para la hora de fin de las 10:00 el examen concluirá a las 9:50).

NOTA: Solo se evaluarán exámenes recibidos hasta la hora señalada de conclusión.

# Inicio de examen
"Apegándome al Código de Ética de los Estudiantes del Tecnológico de Monterrey, me comprometo a que mi actuación en este examen esté regida por la honestidad académica".

Realiza las actividades descritas a continuación.

# Node.js
Inicializa un proyecto de node considerando los siguientes requerimientos
* Instala por medio de `npm install --save-dev` los siguientes paquetes almacenados como dependencia de desarrollo:
  * typescript
  * webpack
  * webpack-cli
  * @webpack-cli/generators

* Inicializa la configuración de TypeScript por medio de `tsc --init`

* Añade la siguiente configuración a tsconfig.json:
  * "outDir": "./dist" 

* Inicializa la configuración de webpack por medio de `npx webpack-cli init` considerando los siguientes aspectos:
* ? Which of the following JS solutions do you want to use? Typescript
* ? Do you want to use webpack-dev-server? Yes
* ? Do you want to simplify the creation of HTML files for your bundle? Yes
* ? Do you want to add PWA support? No
* ? Which of the following CSS solutions do you want to use? CSS only
* ? Will you be using PostCSS in your project? No
* ? Do you want to extract CSS for every file? Only for Production
* ? Do you like to install prettier to format generated configuration? Yes
* ? Pick a package manager: npm
* overwrite package.json : yes
* overwrite README.md: no
* overwrite tsconfig.json: no (en caso de aplicar)

Añade los siguientes scripts a `package.json` en la sección `scripts`, recuerda que deben ir separados por coma:
* `"tsc": "tsc"`
* `"tsc:w: "tsc --watch"`

# HTML
Implementa los siguientes requerimientos en la página `src/index.html`:
## Declarativas html

* Declarativa DOCTYPE html

## Elemento raíz html
* Elemento raíz `<html>` con los elementos descritos abajo y su tag de cierre al final

## Elemento head
* Elemento `<head>` vacío

## Elemento body
* Elemento `<body>` con los elementos descritos abajo y su tag de cierre al final
* Encabezado de primer nivel `<h1>` con texto "Verificador de palabras"
* Párrafo `<p>` con texto: `Ingresa una palabra`
* Caja de entrada de texto `<input>` con atributo `id` igual a `inputText`
* Botón `<button>` con atributo `id` igual a `buttonSubmit` y texto Enviar.
* `<div>` con atributo `id` igual a `divResult`

# CSS
Implementa los siguientes requerimientos en la hoja de estilo `style.css`
* estilo `palindrome` con los siguientes atributos:
  * tamaño de la fuente `large`
  * color `white`
  * color de fondo `blue`
* estilo `notPalindrome` con los siguientes atributos:
  * tamaño de la fuente `large`
  * color `white`
  * color de fondo `purple`

# TypeScript
Implementa los siguientes requerimientos en `src/checker.ts`:
* Implementa la función `isPalindrome` considerando:
  * Parámetro: `text` de tipo `string`
  * Tipo de retorno: `boolean`
  * Escribir en consola el texto provisto como argumento
  * isPalindrome es `true` si cada uno de sus caracteres de izquierda a derecha (índice 0 a indíce length -1) corresponde al caracter del texto en el orden inverso, de derecha a izquiera (índice length - 1 a índice 0). Ignorar la diferencia entre mayúsculas y minúsculas en la comparación.

Ejemplos:
```ts
isPalindrome('Anna') == true
isPalindrome('México') == false
```
  
* Exporta la función `isPalindrome` como `default` del archivo `checker.ts`.

Implementa los siguientes requerimientos en `src/index.ts`:
* Importa la hoja de estilo `style.css`
* Importa la función `isPalindrome` de `./checker`
* Implementa la función buttonSubmitClick considerando:
  * No recibe argumentos.
  * Obten una referencia denominada `inputText` de tipo `<HTMLInputElement>` al elemento HTML con id `inputText`
  * Invoca a la función `isPalindrome()` empleando como parámetro el valor de la caja de texto `inputText`
  * Obten una referencia de tipo `<HTMLDivElement>` al elemento `div` con id `result`
  * Si el resultado de `isPalindrome()` es `true`:
    * Asigna al `div` el texto interno `The word is palindrome`
    * Asigna al div la clase CSS `palindrome`
  * Si el resultado de `isPalindrome()` es `false`:
    * * Asigna al `div` el texto interno `The word is not palindrome`
    * Asigna al div la clase CSS `notPalindrome`
  * Añade un bloque de código donde se añada un EventListener al botón con id `button` con callback a la función `buttonSubmitClick`

# Fin de examen

Asegúrate que todos los cambios al código asociados con tu respuesta al examen se encuentren registrados en control de versiones local (commit) y publicados en el repositorio remoto (push).

Envía a tu profesor un correo con el enlace al repositorio remoto del examen.

Gracias por tu participación y compromiso.