# Práctica de Python: centros deportivos

**Autores:** Juan Carlos López Leal y Marina Martín Ronquillo

En esta práctica trabajamos con los datos de actividad de seis centros deportivos de Madrid, Barcelona y Valencia, entre el 1 y el 14 de septiembre de 2026. Combinamos estos datos con información meteorológica para calcular ocupaciones, agrupar las visitas y representar algunos resultados.

## Datos utilizados

- `datos/actividad.csv`: contiene 504 sesiones deportivas, con su fecha, centro, actividad, turno, duración, plazas y visitas.
- `datos/centros.xlsx`: contiene los datos de los seis centros, incluyendo su ciudad y coordenadas de referencia.
- [Open-Meteo](https://open-meteo.com/en/docs/historical-weather-api): utilizamos su API histórica para consultar las temperaturas máximas y mínimas y la precipitación diaria de las tres ciudades durante el periodo estudiado.

Los datos de actividad y centros son sintéticos y se utilizan con fines docentes.

## Cómo ejecutar el notebook

1. Abrir `practica_centros.ipynb` en Google Colab y conectar el entorno de ejecución.
2. Descargar `actividad.csv` y `centros.xlsx` de la carpeta `datos` del repositorio.
3. Ejecutar las celdas en orden. Cuando aparezca la opción de subir archivos, seleccionar los dos archivos descargados.
4. Continuar la ejecución para consultar Open-Meteo, unir los datos y obtener los resultados.
5. Al final, ejecutar la celda que genera y descarga `resultados_centros.zip`.

Si se reinicia el entorno de Colab, hay que volver a cargar los archivos de entrada.

## Resultados

En el notebook calculamos el porcentaje de ocupación de las sesiones y realizamos agrupaciones por centro, actividad, turno y fecha. También generamos dos gráficos. Tras unir las fuentes, seguimos teniendo 504 sesiones y un total de 8.085 visitas.

La carpeta `salidas`, que se incluye al generar `resultados_centros.zip`, contiene:

- `actividad_preparada.csv`: datos de las sesiones con la información añadida.
- `meteo_diaria.csv`: datos meteorológicos por ciudad y día.
- `resumen_centros.csv`: visitas totales por centro.
- `ocupacion_por_turno.csv`: ocupación media por actividad y turno.
- `visitas_diarias.csv`: visitas diarias por ciudad.
- `visitas_diarias.png`: gráfico de visitas diarias por ciudad.
- `ocupacion_actividad.png`: gráfico de ocupación por actividad y turno.
- `fuentes.json`: información sobre el origen de los datos utilizados.

## Uso responsable de la IA

Durante la práctica, hemos utilizado las herramientas de IA de forma responsable y crítica. En particular, la hemos utilizado para hacer revisiones de código, comprobando las sugerencias que nos da. Dos ejemplos de estas revisiones son los siguientes:

1. **Unión de datos (T5).** Revisamos si era suficiente unir la meteorología por ciudad. Mantuvimos la unión por `ciudad` y `fecha`, ya que hacerlo solo por ciudad duplicaría las sesiones. Así, comprobamos que el resultado conservaba las 504 filas originales.
2. **Agrupaciones (T7).** Revisamos cómo sumar visitas por centro y calcular la ocupación media por actividad y turno. Utilizamos `groupby` con `sum` y `mean`, respectivamente, y comprobamos que el total de visitas seguía siendo 8.085 y que se obtenían las ocho combinaciones de actividad y turno.

## Versiones

En GitHub hemos ido guardando varias versiones del notebook a entregar. Aunque en un inicio este se llamaba `Practica_centros_alumnado_v02.ipynb`, la versión final `practica_centros.ipynb` incluye las funciones y el código completo, las celdas ejecutadas, los gráficos generados junto a las explicaciones y las respuestas pedidas.
