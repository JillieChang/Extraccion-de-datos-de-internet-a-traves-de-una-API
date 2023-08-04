# <p align="center"> EXTRACCIÓN DE DATOS DE LA WEB DEL BCRP<br/> utilizando su API y la librería Requests (Python) </p>
<br/>

<p style='text-align: justify;'> 

Una forma de descargar los datos de la página web del Banco Central de Reserva del Perú (BCRP) <a href="https://estadisticas.bcrp.gob.pe/estadisticas/series/" style="color: navy; text-decoration: underline;text-decoration-style: dotted;">(BCRPData)</a> es a través de su API (interfaz de programación de aplicaciones), la cual permite consultar series estadísticas actualizadas desde otras aplicaciones web de forma directa.

En este ejercicio, se utiliza la librería REQUESTS y el método GET(URL) para realizar las peticiones al API del BCRP y poder consultar los datos. La estructura de la URL es la siguiente:
    
`"https://estadisticas.bcrp.gob.pe/estadisticas/series/api/[códigos_de_series]/[formato_de_salida]/[periodo_inicial]/[periodo_final]/[idioma]"`
</p>

<p align="center";font-size:20pt>
  <img  src="https://user-images.githubusercontent.com/57914884/178173931-e2ab9892-aa06-472c-ba4d-ff8df27f0c99.png">
</p>

<p style='text-align: justify;'> 
    
Con relación a los parámetros utilizados para la descarga, se precisa lo siguiente:

- `[códigos_de_series]`: El código de la serie es el único parámetro obligatorio (se pueden descargar entre 1 y 10 series de la misma frecuencia y deben estar separados por un guión). En este ejercicio, se optó por descargar cada serie de forma independiente y no 10 a la vez. 
- `[formato_de_salida]`: Los datos pueden ser extraídos en diferente formatos de salida como HTML, XLS, XML, JSON, CSV, entre otros.
- `[periodo_inicial]/[periodo_final]`:Si no se colocan los periodos, por defecto se mostrarán los datos más actuales de las series. En el caso que se coloque un solo periodo, se asumirá como una consulta de una fecha.
- `[idioma]`: Los resultados se pueden generar en idioma español (esp) o inglés (ing). Se debe señalar que en el ejercicio no se logró descargar los datos en inglés cambiando el parámetro de "esp" a "ing"

Revisar la <a href="https://estadisticas.bcrp.gob.pe/estadisticas/series/ayuda/api" style="color: navy; text-decoration: underline;text-decoration-style: dotted;">Guía de uso de API para desarrolladores del BCRP</a> para mayor detalle.
   
</p>

## Tabla de contenido

A continuación, se muestran los pasos que se siguieron para poder descargar los datos:

<ol>
  <li>Construir estructura de consultas (URL)</li>
  <li>Enviar solicitudes con el método GET a las URL especificadas </li>
  <li>Revisar estructura de respuestas (http consultadas)</li>
  <li>Seleccionar variables y agregarlas en un dataframe</li>
  <li>Revisar series de dataframe </li>
  <li>Guardar dataframe en un archivo csv.</li>
</ol>
