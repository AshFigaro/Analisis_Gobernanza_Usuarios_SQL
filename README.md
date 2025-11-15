# 💻 Análisis de Gobernanza de TI y Rendimiento de SLAs

## 🎯 Objetivo del Proyecto

Este proyecto demuestra un pipeline completo de análisis de datos, desde la limpieza ETL con Python hasta la ejecución de consultas SQL de nivel intermedio para extraer insights 
de la gestión de tickets y la gobernanza de usuarios. El objetivo analítico es transformar la experiencia previa en Soporte/TI en métricas claras para la optimización operacional 
y la reducción de riesgos.

---

## 🛠️ Stack Tecnológico

| Etapa | Herramientas | Propósito y Técnicas Destacadas |
| :--- | :--- | :--- |
| **ETL & Limpieza** | **Python (Pandas)** | Manejo de codificación de archivos (`encoding='latin-1'`), estandarización de formatos de fecha y carga a base de datos SQLite. |
| **Análisis Lógico/SQL** | **SQL (Intermedio)** | Aplicación de lógica de negocio (SLA y Gobernanza) usando `CASE STATEMENT` y `LEFT JOIN` para extraer *insights* críticos. |
| **Visualización/BI** | **Power BI, DAX** | Creación de métricas de desempeño (`% Incumplimiento SLA`) y diseño de Dashboard Ejecutivo con Gráfico de Cascada (*Waterfall*). |

---

## ✨ Logros y Hallazgos Analíticos Clave

El corazón del proyecto se centra en la aplicación de lógica SQL avanzada para responder preguntas de negocio cruciales sobre la eficiencia de TI y el riesgo de seguridad.

* **Auditoría de Incumplimiento de SLA:** Para medir la eficiencia, se implementó un CASE STATEMENT en SQL que compara el tiempo real de resolución contra el tiempo definido en el SLA,
lo que permitió calcular el PorcentajeFueraSLA agrupado por Categoría de Ticket y Departamento.
El CASE STATEMENT permitió identificar el Incumplimiento Crítico por área: el departamento de Operaciones presenta la Tasa de Falla más alta, con un 1.67% de sus tickets fuera de SLA. Este hallazgo señala un cuello de botella severo que requiere una revisión inmediata de los procesos de soporte críticos para la continuidad operacional.

* **Gobernanza y Riesgo de Cuentas:** En un logro directamente relacionado con la experiencia en Soporte/TI, se aplicó un LEFT JOIN para
realizar una auditoría de seguridad: se identificaron cuentas de usuario activas que no han solicitado soporte o generado actividad en el último año. 
La conclusión analítica recomienda iniciar un proceso de desactivación de estas cuentas para reducir el riesgo de accesos no autorizados y optimizar los costos de licencias.

## 📊 Dashboard de Power BI (Entregable Final)
El resultado del análisis SQL fue exportado a analisis_ti_processed.csv, el cual sirve como fuente única y confiable para el Dashboard.
El resultado es un Dashboard Ejecutivo que presenta la Tasa de Falla Global del SLA (0.66%) y un Gráfico de Cascada (Waterfall) para desglosar la contribución de cada Categoría de Ticket al incumplimiento, facilitando la identificación de la causa raíz de las fallas.

---

## 📁 Estructura del Repositorio

Para replicar el análisis:

| Carpeta | Contenido |
| :--- | :--- |
| `notebooks/` | Código fuente en Python (`ETL_Analisis_SLA_Ti.ipynb`) con todo el proceso de ETL y las consultas SQL. |
| `data/raw/` | Datos originales sin procesar (`usuarios.csv`, `tickets.csv`). |
| `data/processed/` | Archivo limpio y resultado del *pipeline* (`analisis_ti_processed.csv`), listo para ser consumido por Power BI. |
| `reports/` | Archivo de Power BI (`Dashboard_Ejecutivo_SLA_TI.pbix`). |
