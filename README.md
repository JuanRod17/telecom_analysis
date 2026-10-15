Objetivo del proyecto
Analizar el comportamiento de los clientes de ConnectaTel (empresa con operaciones en México y Colombia) utilizando datos reales de uso de servicios móviles (llamadas y mensajes) hasta el año 2024. El propósito principal es identificar patrones de consumo, detectar comportamientos atípicos (outliers), y comprender qué segmentos de usuarios muestran necesidades diferenciadas para optimizar la oferta comercial, mejorar la retención y diseñar estrategias de migración de planes.


Datasets utilizados
El proyecto integra y procesa información proveniente de tres fuentes principales:

plans.csv: Catálogo de planes actuales que incluye detalles de precios, minutos, mensajes y gigabytes incluidos, así como costos por excedentes.

users_latam.csv: Información demográfica y de registro de los clientes (edad, ciudad, fecha de registro, plan contratado y fecha de baja o churn).

usage.csv: Detalle transaccional del uso real de los servicios móviles (tipo de interacción, fecha, duración de llamadas y longitud de mensajes).


Etapas del análisis realizadas
El desarrollo del proyecto se estructuró en un flujo de pensamiento programático dividido en 8 pasos principales:

Carga y exploración inicial: Importación de librerías (pandas, numpy, seaborn, matplotlib) y revisión estructural de los tres datasets (.shape, .info()).

Identificación de problemas de calidad: Conteo de valores nulos, localización de valores centinelas (ej. -999 en edad y ? en ciudad), y detección de anomalías temporales (fechas futuras en 2026).

Limpieza básica de datos: Reemplazo de centinelas por valores estadísticos (mediana), estandarización de nulos, tratamiento de fechas fuera de rango y validación de un patrón de datos faltantes MAR (Missing At Random) dependiente del tipo de servicio.

Resumen estadístico por usuario: Agregación de la tabla de uso por user_id para calcular métricas clave de comportamiento histórico (mensajes totales, llamadas totales y minutos acumulados).

Visualización y detección de outliers: Generación de histogramas segmentados por tipo de plan y boxplots analizados mediante el método IQR (Rango Intercuartílico) para evaluar valores extremos.

Segmentación de clientes: Creación de categorías accionables basadas en rangos de edad (Joven, Adulto, Adulto Mayor) y niveles de consumo (Bajo uso, Uso medio, Alto uso).

Insight ejecutivo: Estructuración de conclusiones de negocio y recomendaciones orientadas a marketing y prevención de riesgos.

Publicación y versionado: Documentación y estructuración del repositorio en GitHub.


Cómo ejecutar el notebook en Google Colab
Sube tu archivo .ipynb a tu unidad de Google Drive o ábrelo directamente desde tu repositorio de GitHub usando Google Colab.

Asegúrate de contar con la estructura de carpetas correcta o ajusta las rutas de lectura de los archivos CSV según corresponda (/datasets/plans.csv, etc.).

Ejecuta las celdas secuencialmente de arriba hacia abajo (Runtime > Run All).


Guía de reproducción
Verifica que los archivos fuente (plans.csv, users_latam.csv, usage.csv) estén ubicados en la ruta especificada en el código o cárgalos en tu entorno de trabajo.

Sigue el orden de los bloques de código descritos en el Jupyter Notebook. Cada bloque cuenta con comentarios explicativos sobre los filtros, limpiezas y transformaciones aplicadas.

Las visualizaciones y gráficos estadísticos se generarán de manera automática tras ejecutar las celdas correspondientes al Paso 5 y Paso 6.
