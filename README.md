# Bootcamp-DA-P2-proyecto2-analysis-python

Todo el proceso esta documentado en formato de comentarios para saber la utilidad de cada parte del codigo

Análisis de Microcréditos de Kiva - Proyecto de Limpieza y ETL
1. Pasos Ejecutados
El proyecto sigue un flujo de trabajo de ingeniería de datos dividido en cuatro fases principales:

Fase 1: Carga y Auditoría: Importación del dataset masivo (+670k registros) y detección de columnas con alta tasa de nulos (tags).

Fase 2: Limpieza y Normalización:

Eliminación de duplicados y gestión de valores faltantes.

Estandarización de variables categóricas (minúsculas y eliminación de espacios).

Corrección de tipos de datos (Conversión de fechas y montos a formatos numéricos).

Fase 3: Gestión de Outliers: Aplicación del método de percentiles para estabilizar la media de los préstamos.

Fase 4: Ingeniería de Variables y Codificación: Creación de métricas de eficiencia y transformación de variables de género a formato binario (One-Hot Encoding).

2. Resumen de Decisiones de Limpieza (Justificación)
Durante el proceso se tomaron decisiones estratégicas para asegurar la calidad de los datos:

Eliminación de la columna tags: Se descartó debido a que presentaba un alto porcentaje de valores nulos y no aportaba valor estadístico directo para el análisis cuantitativo.

Mantenimiento de Nulos en funded_time: No se eliminaron ni imputaron estos nulos para evitar el sesgo de supervivencia. Los nulos representan préstamos no completados, una información crítica para entender el riesgo en la plataforma.

Filtro de Outliers (Percentil 99): Se estableció un límite de $5,300 USD para los préstamos. Esto eliminó el 1% de casos extremos (préstamos de hasta $50,000) que distorsionaban el promedio y dificultaban la visualización.

Normalización de Consistencia: Se ajustaron los registros donde el monto recaudado superaba ligeramente al solicitado para garantizar un ratio_fondeo máximo de 1.0.

3. Cómo Ejecutar el Notebook
Para reproducir este análisis, siga estas instrucciones:

Entorno: Abra el archivo .ipynb en Google Colab.

Carga de Datos: Asegúrese de subir el archivo original kiva_loans.csv a la sección de archivos de la sesión (icono de carpeta a la izquierda).

Dependencias: El notebook utiliza pandas, seaborn, matplotlib y numpy. No es necesaria la instalación manual ya que vienen preinstaladas en Colab.

Ejecución:

Vaya a la pestaña Entorno de ejecución.

Seleccione Ejecutar todas.
