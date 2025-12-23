# 📊 Análisis de Datos Públicos del Canal de Streaming LUZU TV

### ETL con Python y YouTube Data API

## 🧠 Descripción general

Este proyecto forma parte de un trabajo integral de **Data Analytics** cuyo objetivo es analizar datos públicos del canal de streaming **LUZU TV** utilizando la **YouTube Data API**.

El proyecto está estructurado en **tres etapas clásicas del análisis de datos**:

1. **ETL (Extract, Transform, Load)** ← *etapa desarrollada en este repositorio*
2. **EDA (Exploratory Data Analysis)**
3. **Visualización y generación de insights**

En esta primera parte se implementa un proceso completo de **extracción, limpieza, transformación y enriquecimiento de datos**, dejando un dataset final listo para análisis exploratorio y visualización.

---

## 🎯 Objetivos del proyecto

### Objetivo general

Construir un pipeline de ETL en Python que permita transformar datos crudos de YouTube en un dataset estructurado y analíticamente robusto para la toma de decisiones de negocio.

### Objetivos específicos

* Conectarse a la **YouTube Data API v3**
* Extraer datos públicos del canal (videos, métricas y metadata)
* Limpiar valores nulos y registros inconsistentes
* Normalizar y enriquecer variables textuales y temporales
* Clasificar videos por **programa**, **formato** y **duración**
* Crear métricas derivadas (engagement, viralidad, ratios)
* Detectar outliers de forma estadística
* Generar un DataFrame final listo para EDA y visualización

---

## 🛠️ Tecnologías utilizadas

* **Python**
* **Google YouTube Data API v3**
* **Pandas**
* **NumPy**
* **Scikit-learn** (TF-IDF + KMeans para clustering exploratorio)
* **Google Colab**

---

## 📥 Extracción de datos (Extract)

Los datos se obtienen mediante la **YouTube Data API**, consultando:

* Información del canal
* Lista completa de videos
* Metadata de cada video:

  * título
  * fecha de publicación
  * duración
  * vistas
  * likes
  * comentarios

Se respetan las limitaciones de la API (máx. 50 videos por request).

---

## 🧹 Transformación y limpieza (Transform)

Durante el proceso ETL se realizaron, entre otras, las siguientes transformaciones:

### 🔹 Limpieza de datos

* Eliminación de registros con métricas inconsistentes (duración = 0, métricas imposibles)
* Tratamiento de valores nulos
* Conversión de tipos de datos (fechas, métricas numéricas)

### 🔹 Normalización

* Normalización de títulos (minúsculas, eliminación de tildes)
* Conversión de duraciones ISO 8601 a minutos
* Normalización temporal (días desde publicación)

### 🔹 Clasificación de contenido

* Clasificación automática por **programa**, usando un enfoque híbrido:

  * hashtags
  * texto del título
* Clasificación por **formato** según duración:

  * Short
  * Clip
  * Segmento
  * Full Program
  * Complete Programming


### 🔹 Métricas derivadas

Se agregaron métricas clave para análisis de negocio:

* Views por día
* Views por minuto (normalizado)
* Engagement rate
* Like ratio
* Comment ratio
* Growth factor
* Detección de outliers (vistas, likes, engagement)

### 🔹 Mejora iterativa de clasificación

* Reducción progresiva de la categoría genérica **“Contenido no programático”**
* Auditoría manual + reglas incrementales
* Clustering exploratorio sobre títulos no clasificados

---

## 📦 Carga (Load)

El resultado del ETL es un **DataFrame final limpio y enriquecido**, listo para:

* Análisis exploratorio (EDA)
* Visualizaciones
* Insights de negocio

Este dataset será utilizado en la **segunda etapa del proyecto**.

---

## 📈 Próximos pasos (fase 2)

* Análisis exploratorio de datos (EDA)
* Comparación de métricas por programa y formato
* Identificación de patrones de engagement y viralidad
* Visualizaciones orientadas a decisiones de contenido

---

## ▶️ Cómo ejecutar el proyecto

1. Clonar el repositorio
2. Abrir el notebook en **Google Colab**
3. Crear una API Key de YouTube Data API v3
4. Guardar la API Key como variable de entorno
5. Ejecutar las celdas en orden

---

## 👤 Autor

**Ulises Alberto Gonzalez**
* Analista de Datos Jr. 
* Licenciado en Biotecnología

---

## 🧭 Contexto profesional

Este proyecto forma parte de una **transición profesional hacia el análisis y la ciencia de datos**, integrando formación científica, pensamiento analítico y herramientas de programación para resolver problemas reales basados en datos.
