# 📊 Análisis de la Legislatura de Córdoba

Este proyecto analiza la composición y asistencia legislativa en la **Legislatura de la Provincia de Córdoba**, Argentina, utilizando herramientas de **Power BI** y técnicas de modelado de datos.

> ⚠️ Toda la información fue tomada con fines educativos y de práctica personal. La misma se encuentra disponible públicamente en la [página oficial de la Legislatura](https://legislaturacba.gob.ar/) y su [Portal de Datos Abiertos](https://legislaturacba.gob.ar/portal-de-datos-abiertos/).


## 📅 Período Analizado

**18 de diciembre de 2024** al **30 de abril de 2025**


## 🗂️ Fuentes de Datos

- **Composición de la Cámara (2025)**  
  Datos sobre la cantidad de legisladores, bloques políticos y distribución por género.

- **Histórico de Legisladores (1983 – 2025)**  
  Listado completo de legisladores que formaron parte del Poder Legislativo Provincial desde 1983.

- **Asistencia a Sesiones Legislativas**  
  Registro de asistencias individuales por bloque y legislador/a en cada sesión del año.


## 🛠️ Proceso de Trabajo

**Proceso ETL – Extracción, Transformación y Carga con Power Query**

Durante el proyecto, trabajé con fuentes reales y apliqué múltiples técnicas para estructurar y preparar los datos:

- Perfilado de datos y asignación de tipos correctos
- Tratamiento de filas y columnas: detección de vacíos, valores nulos, inconsistencias
- Reemplazo de valores erróneos y estandarización
- Combinación de consultas (merge y append) para unificar tablas
- Anulación de dinamización de columnas (unpivot) para transformar estructuras
- Carga de datos al modelo con enfoque dimensional
Se construyó un modelo de datos tipo estrella, relacionando las tablas `dim_Legisladores` y `fact_Asistencias` a través del campo **DNI**.

**Tabla de hechos:** `fact_Asistencias`  
**Tabla de dimensión:** `dim_Legisladores`

Además, se renombran campos para mejorar la comprensión semántica y mantener consistencia en el modelo.

- Ocultamiento de columnas innecesarias para simplificar la experiencia del usuario
- Uso de funciones iteradoras como SUMX, VARX y medidas DAX para construir indicadores

📊 **Visualización de Datos en Power BI**

- Segmentadores por bloque político, tipo de sesión, género y fechas
- Diseño de paneles claros e interactivos con enfoque en el usuario
- Breve Storytelling visual sobre la evolución de género y participación en la composición de la cámara. 
- Filtros dinámicos por tipo de sesión (Presente, Ausente, **NA → campo vacío en la base de datos original**) y por fecha

📘 **Glosario**

Bloque:
Grupo de tres (3) o más Legisladores organizados por afinidad política. En caso de partidos o alianzas con un solo representante, pueden igualmente actuar como bloque.

Sesión:
Reunión celebrada por el cuerpo de Legisladores dentro del período legislativo.
