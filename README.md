# Multi-Database RAG System & Intent Router

> Trabajo práctico final - Procesamiento del Lenguaje Natural  
> Tecnicatura Universitaria en Inteligencia Artificial (UNR)  
> Máximo Alva  
> 2026  

---

## 💡 Acerca del proyecto
Este proyecto implementa un asistente inteligente de preguntas y respuestas (QA) bajo una arquitectura **RAG (Retrieval-Augmented Generation)** avanzada y modular. 

A diferencia de los sistemas RAG tradicionales que consultan una única fuente, este asistente cuenta con un **enrutador de intenciones basado en Machine Learning** (Regresión Logística sobre embeddings) que analiza la consulta del usuario en lenguaje natural y la deriva dinámicamente hacia la base de datos óptima:

1. **Base de Datos Vectorial (Milvus Lite):** Resuelve consultas conceptuales, manuales técnicos y reseñas de usuarios mediante búsqueda semántica (`SentenceTransformers`).
2. **Base de Datos Relacional (SQLite):** Resuelve consultas de negocio, stock, precios y métricas mediante traducción automática de lenguaje natural a **SQL**.
3. **Base de Datos de Grafos (GrafitoDB):** Resuelve consultas sobre relaciones complejas, categorías y preguntas frecuentes (FAQs) mediante traducción a **Cypher**.

Las respuestas finales y las traducciones de código son generadas integrando **Ollama** con el modelo `qwen2.5` en un entorno local/Colab.

---

## 🛠️ Tecnologías y librerías
* **Python**
* **NLP & Embeddings:** `SentenceTransformers` (`paraphrase-multilingual-MiniLM-L12-v2`), `NLTK`, `LangChain Text Splitters`.
* **Bases de Datos:** `Milvus Lite` (Vectorial), `SQLite` (Relacional), `GrafitoDB` (Grafos).
* **Machine Learning:** `scikit-learn` (Clasificador de intenciones).
* **LLM & Local Inference:** `Ollama` (`qwen2.5`).

---

## 🚀 Cómo usarlo

El proyecto está diseñado para ejecutarse de forma interactiva en **Google Colab** con soporte de GPU.

1. Abrí el notebook principal `TP_NLP_MaximoAlva.ipynb` haciendo clic en el botón superior de *Open in Colab*.
2. Ejecutá la celda de **Preparación del entorno**:
   * Se instalarán automáticamente todas las dependencias necesarias.
   * Se descargará e iniciará el servidor de **Ollama** en segundo plano bajando el modelo `qwen2.5`.
   * Se clonará la carpeta de fuentes de información directamente desde este repositorio.
3. Recorré las celdas secuencialmente para probar los distintos módulos.
