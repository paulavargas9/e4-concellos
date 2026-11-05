# E4 - Concellos da provincia da Coruña

## Objetivo

El objetivo de este ejercicio es extraer los datos de población de los 93 municipios de la provincia de A Coruña desde Wikipedia mediante web scraping.

Después voy a limpiar y validar los datos para poder analizarlos y responder a las preguntas del ejercicio.

## 4.1. Antes de descargar

Primero compruebo si Wikipedia permite acceder a la página utilizando un programa de Python. Para ello consulto el archivo `robots.txt` con `RobotFileParser`.

También reviso la licencia de Wikipedia y compruebo si los datos contienen información personal.

## 4.2. Descarga

Descargo la página de Wikipedia con la librería `requests` y guardo el HTML original en la carpeta `datos/raw/`.

Antes de descargar, compruebo si el archivo ya existe para evitar repetir la descarga cada vez que ejecuto el notebook.

## 4.3. Extracción de datos

Leo el HTML guardado y utilizo BeautifulSoup para buscar la tabla que contiene los municipios y su población.

Localizo la tabla por sus encabezados y extraigo los datos para crear un DataFrame con pandas.

En total obtengo 93 municipios y dos columnas: municipio y población.

## 4.4. Limpieza de datos

Reviso cómo están guardadas las poblaciones y compruebo que todas tienen el formato correcto.

Como están guardadas como texto y utilizan comas para separar los millares, elimino las comas y convierto los valores en números enteros.

No encuentro valores extraños, así que no necesito corregir ninguno manualmente.

## 4.5. Validación de los datos

Compruebo que tengo los 93 municipios de la provincia y que no hay nombres repetidos.

Al sumar las poblaciones obtengo 1.128.320 habitantes, que coincide con el total indicado en Wikipedia.

También comparo los datos extraídos con BeautifulSoup con los obtenidos mediante `pd.read_html()` y compruebo que coinciden.

## 4.6. Preguntas sobre los datos

Utilizo pandas para responder a las cuatro preguntas del ejercicio.

Los cinco municipios más poblados son A Coruña, Santiago de Compostela, Ferrol, Narón y Oleiros.

He comprobado que 43 municipios tienen menos de 5.000 habitantes, lo que representa el 46,24 % del total.

Los tres municipios más poblados reúnen 413.015 habitantes, que representan el 36,6 % de la población provincial.

Por último, calculo que hacen falta los 8 municipios más poblados para alcanzar al menos la mitad de la población de la provincia.

## 4.7. Guardar los datos

Guardo los datos limpios en el archivo `datos/clean/municipios_coruna.csv`, utilizando la codificación UTF-8.

Después vuelvo a leer el archivo con pandas y compruebo que contiene los 93 municipios y que los datos coinciden con los del DataFrame original.

## Uso de inteligencia artificial

Para realizar este ejercicio he utilizado herramientas de inteligencia artificial como apoyo.

Las he utilizado para ayudarme a escribir y desarrollar el código Python, entender el funcionamiento de las librerías utilizadas y resolver los errores que me han ido apareciendo.

También me han ayudado a organizar el ejercicio y revisar la redacción de las explicaciones del notebook y del README.

He ejecutado el código en VS Code y he comprobado los resultados obtenidos en cada apartado.
