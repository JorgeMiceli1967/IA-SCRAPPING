# IA-SCRAPPING
Relevamiento web automatizado para análisis de ecosistemas de IA y derecho

## Descripción
Este repositorio contiene un script en Python diseñado para realizar **relevamientos web temáticos automatizados** orientados a la construcción de **estados del arte** en campos vinculados con la inteligencia artificial aplicada al derecho y a los sistemas de justicia.
El script ejecuta búsquedas estructuradas en Google mediante **SerpAPI**, recupera resultados orgánicos, visita las páginas encontradas, extrae texto visible básico y calcula un **puntaje de relevancia temática** basado en reglas explícitas.
Los resultados se organizan en una base estructurada que permite identificar actores institucionales, herramientas tecnológicas, publicaciones académicas y recursos relevantes dentro del ecosistema analizado.
El objetivo es facilitar una **exploración sistemática y reproducible** de fuentes web vinculadas con inteligencia artificial, justicia penal y tecnologías jurídicas.

## Funcionalidades principales
El script realiza automáticamente las siguientes operaciones:
- ejecución de búsquedas temáticas en Google mediante SerpAPI
- recuperación de resultados orgánicos
- visita a cada URL encontrada
- extracción de texto visible de la página
- cálculo de un **puntaje de relevancia temática**
- clasificación heurística del **tipo de actor institucional**
- eliminación de resultados duplicados
- generación de tablas de síntesis
- exportación de resultados a **CSV y Excel**

Esto permite identificar rápidamente:

- instituciones relevantes
- herramientas de legal tech
- programas académicos y grupos de investigación
- publicaciones científicas
- plataformas tecnológicas

## Campos temáticos analizados
El relevamiento se organiza en cuatro áreas principales:

1. **Inteligencia artificial y analítica de datos en sistemas judiciales y fiscalías**
2. **Legal tech y oferta académica en inteligencia artificial y derecho**
3. **Herramientas de inteligencia artificial aplicadas al ámbito jurídico**
4. **Bibliografía académica y jurisprudencia sobre inteligencia artificial y justicia penal**

Cada campo incluye consultas de búsqueda específicas y vocabulario relevante para evaluar la pertinencia de los resultados.

## Cálculo de relevancia temática
Cada resultado se evalúa mediante un puntaje de relevancia basado en coincidencias entre el contenido recuperado y un conjunto de términos relevantes definidos para cada campo.

La fórmula utilizada es:

Relevancia =  
(3 × coincidencias en título)  
+ (2 × coincidencias en snippet)  
+ (1 × coincidencias en texto de la página)  
+ coincidencias institucionales

Este esquema prioriza coincidencias en el título y el snippet del buscador, que suelen reflejar con mayor precisión el contenido central del recurso.

## Clasificación de actores
Los resultados se clasifican heurísticamente según el tipo de actor institucional:

- gobierno / sistema judicial
- academia
- organizaciones o fundaciones
- empresas o proveedores tecnológicos
- otros

La clasificación se basa en el dominio web y en el contenido textual recuperado.

## Requisitos
El script utiliza las siguientes librerías de Python:

requests  
pandas  
openpyxl  
beautifulsoup4  
lxml

Instalación:
pip install requests pandas openpyxl beautifulsoup4 lxml

## Configuración de la API
El script requiere una clave de **SerpAPI** para acceder a los resultados del buscador.
https://serpapi.com/

En Google Colab la clave se guarda como **Secret** con el nombre:
SERPAPI_KEY
El script la recupera mediante:
from google.colab import userdata  
API_KEY = userdata.get("SERPAPI_KEY")

Esto permite mantener las credenciales fuera del código.

## Archivos generados
La ejecución del script produce tres archivos principales:
relevamiento_estado_del_arte.csv  
relevamiento_estado_del_arte.xlsx  
relevamiento_resumen.xlsx

Estos contienen:
- la base completa de resultados recuperados
- resúmenes por campo temático
- distribución por tipo de actor institucional
- ranking de dominios más frecuentes

## Uso recomendado
Esta herramienta está pensada como instrumento de **exploración inicial de estados del arte**, particularmente útil en investigaciones sobre:
- inteligencia artificial aplicada al derecho
- transformación digital de sistemas judiciales
- ecosistemas de legal tech
- análisis institucional de tecnologías emergentes

No reemplaza la evaluación cualitativa de las fuentes recuperadas, pero permite **acelerar y sistematizar la fase exploratoria del relevamiento**.

## Autor
Jorge Miceli
