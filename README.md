# 📊 Análisis de la Legislatura de Córdoba

Este proyecto analiza la composición y asistencia legislativa en la **Legislatura de la Provincia de Córdoba**, Argentina, utilizando herramientas de **Power BI** y técnicas de modelado de datos.

> ⚠️ Toda la información fue tomada con fines educativos y de práctica personal. La misma se encuentra disponible públicamente en la [página oficial de la Legislatura](https://legislaturacba.gob.ar/) y su [Portal de Datos Abiertos](https://legislaturacba.gob.ar/portal-de-datos-abiertos/).

---

## 📅 Período Analizado

**18 de diciembre de 2024** al **30 de abril de 2025**

---

## 🗂️ Fuentes de Datos

- **Composición de la Cámara (2025)**  
  Datos sobre la cantidad de legisladores, bloques políticos y distribución por género.

- **Histórico de Legisladores (1983 – 2025)**  
  Listado completo de legisladores que formaron parte del Poder Legislativo Provincial desde 1983.

- **Asistencia a Sesiones Legislativas**  
  Registro de asistencias individuales por bloque y legislador/a en cada sesión del año.

---

# ⚙️ Proceso ETL (Extracción, Transformación y Carga):
Este proyecto me permitió aplicar todo el flujo completo de trabajo de datos:

## 1. **Limpieza de Datos con Power Query**
- Se detectaron y reemplazan valores inconsistentes/erróneos.
- Se crea una columna personalizada para fechas, manejando valores `null` si no hay información registrada.
- Perfilado de valores.
- Limpieza de columnas inconsistentes

## 2. **Relación entre Tablas**
Se relacionan las tablas dim_Legisladores y fact_Asistencias a través del campo DNI.

## 3. **Modelo Dimensional Básico**
Se construye un modelo de datos tipo estrella:
Tabla de hechos: fact_Asistencias
Tabla de dimensión: dim_Legisladores

Se renombran campos para mejorar la comprensión y consistencia del modelo.

## 4. **Transformación de Datos**
En la tabla fact_asistencias2025, se aplica la función desagrupar columnas para transformar sesiones (columnas) en filas, permitiendo análisis por fecha y tipo de sesión.

## 5. **Principales Visualizaciones en Power BI**
-Composición por bloque político
-Distribución por género
-Evolución histórica de la representación femenina y masculina
-Asistencia por bloque y legislador/a
-Filtros por tipo de sesión (Presente, Ausente, **NA > Campo Vacio en BD Original** y fecha)

📘 Glosario:
Bloque:
Grupo de tres (3) o más Legisladores organizados por afinidad política. En caso de partidos o alianzas con un solo representante, pueden igualmente actuar como bloque.

Sesión:
Reunión celebrada por el cuerpo de Legisladores dentro del período legislativo.
