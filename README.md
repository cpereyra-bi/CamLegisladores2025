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

### 1. **Limpieza de Datos con Power Query**
- Se detectaron y reemplazaron valores inconsistentes o erróneos.
- Se creó una columna personalizada para fechas, contemplando valores `null` en los casos sin información registrada.
- Se realizó un perfilado de valores para identificar patrones y outliers.
- Se limpiaron columnas con formatos o registros inconsistentes.

### 2. **Modelo Dimensional Básico**
Se construyó un modelo de datos tipo estrella, relacionando las tablas `dim_Legisladores` y `fact_Asistencias` a través del campo **DNI**.

- **Tabla de hechos:** `fact_Asistencias`  
- **Tabla de dimensión:** `dim_Legisladores`

Además, se renombran campos para mejorar la comprensión semántica y mantener consistencia en el modelo.

### 3. **Transformación de Datos**
En la tabla `fact_asistencias2025`, se aplicó la función **desagrupar columnas (unpivot)** para transformar los registros de sesiones (originalmente columnas) en filas. Esto permite un análisis más flexible por **fecha** y **tipo de sesión**.

### 4. **Principales Visualizaciones en Power BI**
- Composición de la Cámara por bloque político
- Distribución de legisladores/as por género
- Evolución histórica de la representación femenina y masculina
- Asistencia a sesiones, segmentada por bloque y por legislador/a
- Filtros dinámicos por tipo de sesión (Presente, Ausente, **NA → campo vacío en la base de datos original**) y por fecha


📘 Glosario:

Bloque:
Grupo de tres (3) o más Legisladores organizados por afinidad política. En caso de partidos o alianzas con un solo representante, pueden igualmente actuar como bloque.

Sesión:
Reunión celebrada por el cuerpo de Legisladores dentro del período legislativo.
