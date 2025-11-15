💻 Análisis de Gobernanza de TI y Rendimiento de SLAs

Este proyecto demuestra un pipeline completo de análisis de datos, desde la limpieza ETL con Python hasta la ejecución de consultas SQL de nivel intermedio para extraer insights 
de la gestión de tickets y la gobernanza de usuarios. El objetivo analítico es transformar la experiencia previa en Soporte/TI en métricas claras para la optimización operacional 
y la reducción de riesgos.

🛠️ Stack Tecnológico

La metodología empleada sigue un proceso ETL (Extracción, Transformación y Carga) bien definido. 
La fase de ETL & Limpieza se ejecuta con Python (Pandas), donde se maneja la codificación de archivos (encoding='latin-1'), 
se estandarizan los formatos de fecha y se cargan los datos en una base de datos local SQLite. El Análisis Lógico utiliza el 
entorno SQLite para aplicar la lógica de negocio mediante SQL Intermedio, extrayendo los hallazgos. Finalmente, la Visualización/BI se realiza en Power BI,
consumiendo el resultado limpio del análisis SQL para generar un dashboard de toma de decisiones.

✨ Logros y Hallazgos Analíticos Clave
El corazón del proyecto se centra en la aplicación de lógica SQL avanzada para responder preguntas de negocio cruciales sobre la eficiencia de TI y el riesgo de seguridad.

Auditoría de Incumplimiento de SLA: Para medir la eficiencia, se implementó un CASE STATEMENT en SQL que compara el tiempo real de resolución contra el tiempo definido en el SLA,
lo que permitió calcular el PorcentajeFueraSLA agrupado por Categoría de Ticket y Departamento.
El hallazgo crítico reveló que la categoría 'Acceso' en el departamento de Finanzas presenta una alarmante tasa de incumplimiento del 50%. 
Este insight señala un cuello de botella específico que debe resolverse mediante la automatización de los procesos de gestión de acceso.

Gobernanza y Riesgo de Cuentas: En un logro directamente relacionado con la experiencia en Soporte/TI, se aplicó un LEFT JOIN para
realizar una auditoría de seguridad: se identificaron cuentas de usuario activas que no han solicitado soporte o generado actividad en el último año. 
La conclusión analítica recomienda iniciar un proceso de desactivación de estas cuentas para reducir el riesgo de accesos no autorizados y optimizar los costos de licencias.

📊 Dashboard de Power BI (Entregable Final)
El resultado del análisis SQL fue exportado a analisis_ti_processed.csv, el cual sirve como fuente única y confiable para el Dashboard.
El panel final, denominado Dashboard Ejecutivo de SLA y TI, se centra en la visualización del Porcentaje de Incumplimiento de SLA segmentado por Departamento, 
lo que permite a la gerencia priorizar las inversiones y los esfuerzos de optimización de procesos internos.

📁 Estructura del Repositorio
Para replicar el análisis, el repositorio está estructurado en las siguientes carpetas: la carpeta notebook/ contiene el código fuente en Python (ETL_Analisis_SLA_Ti.ipynb) 
con todo el proceso de ETL y las consultas SQL. La carpeta data/raw/ almacena los datos originales (usuarios.csv, tickets.csv). La carpeta data/processed/ es el resultado del
pipeline y contiene el archivo limpio (analisis_ti_processed.csv), listo para ser consumido por Power BI. Finalmente, la carpeta reports/ contiene el archivo
de Power BI (Dashboard_Ejecutivo_SLA_TI.pbix) y las capturas de pantalla del análisis.
