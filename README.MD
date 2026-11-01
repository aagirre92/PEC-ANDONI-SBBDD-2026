# Introducción a Big Data con Hadoop y Herramientas Inspiradas en SQL

Repositorio con el desarrollo de la práctica de evaluación (curso 2026-2027) de la asignatura **Sistemas de Bases de Datos** del Grado en Ingeniería Informática (UNED).

## 🛠️ Stack y Entorno de Trabajo
* **Entorno:** Máquina Virtual de Cloudera (Hadoop / HDFS / YARN).
* **Consultas tipo SQL:** Apache Hive (`HiveQL` vía `Beeline`).
* **Procesamiento Distribuido:** `Hadoop Streaming` con scripts MapReduce en Python.
* **Desarrollo y Memoria:** Jupyter Notebook.

---

## 📂 Contenido de la Práctica

### 1. Datos del Banco Mundial: Electricidad y Energía Nuclear (Apartados 1 - 5)
Análisis de indicadores históricos (1960–2024) del Banco Mundial por país:
* `API_EG.ELC.ACCS.ZS_DS2_en_csv_v2_33377.csv`: Acceso a la electricidad (% de la población).
* `API_EG.ELC.NUCL.ZS_DS2_en_csv_v2_39492.csv`: Producción de electricidad de fuentes nucleares (% del total).

**Tareas realizadas:**
1. **Creación de tablas (HiveQL):** Definición y justificación del tipo de tablas (internas/externas).
2. **Carga y validación:** Ingesta de datos en HDFS/Hive y consultas de verificación acotadas (sin usar `SELECT *`).
3. **Vistas:** Creación de una vista con el valor medio de producción nuclear por país en la década 1990–1999.
4. **Consultas analíticas (HiveQL):**
   * Valor de energía nuclear en Argentina en 2023.
   * Acceso a la electricidad en 2018 para el país con mayor producción nuclear en dicho año.
   * Top 5 países con mayor media de producción nuclear en la década 1990–1999.
5. **MapReduce en Python:** Implementación de funciones `mapper.py` y `reducer.py` (patrón de filtrado) para resolver la consulta 4.1 directamente sobre Hadoop.

### 2. Caso Práctico Propio: Steam Game Recommendations (Apartado 6)
Explotación de un conjunto de datos relacional propio registrado en el foro de la asignatura:
* **Dataset:** [Game Recommendations on Steam (Kaggle)](https://www.kaggle.com/datasets/antonkozyriev/game-recommendations-on-steam)
* **Tablas importadas en Hive (mínimo 3):**
  * `games`: Metadatos del catálogo de juegos (`app_id`, título, fecha, valoración, precio).
  * `users`: Estadísticas de usuarios (`user_id`, productos adquiridos, reseñas publicadas).
  * `recommendations`: Interacciones y horas de juego registradas (`review_id`, `app_id`, `user_id`, horas, recomendación).
* **Consultas:** Desarrollo de 4 consultas en HiveQL sobre las tres tablas, incluyendo operaciones de agregación y reunión (`JOIN`).

> **Nota sobre archivos pesados en el repositorio:** Los ficheros originales sin comprimir/filtrar (`archive.zip` y `recommendations.csv` completo de >1,8 GB) están excluidos en `.gitignore` por superar el límite de 100 MB de GitHub. Para la ejecución en la VM de Cloudera se utiliza una versión filtrada de `recommendations.csv` acotada a *Elden Ring* y *Grand Theft Auto V (GTA V)*.

---

## 📑 Aspectos Adicionales del Entregable
* **Uso de IA Generativa:** Documentación de la herramienta empleada y registro íntegro de los *prompts* utilizados durante el desarrollo.
* **Valoración personal:** Conclusiones, puntos fuertes y débiles encontrados al realizar la práctica.