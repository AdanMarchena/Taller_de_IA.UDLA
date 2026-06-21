# Asistente de Ritmo Emocional para Escritores (NLP)

Este proyecto consiste en un cuaderno interactivo desarrollado en Python para el Procesamiento del Lenguaje Natural (NLP). Está diseñado como una herramienta de apoyo para escritores, permitiéndoles analizar el flujo y la evolución de las emociones dentro de sus textos línea por línea.

## 🚀 Características del Proyecto
- **Limpieza de Texto:** Filtrado de signos de puntuación, conversión a minúsculas y eliminación de *stopwords* en español.
- **Análisis Exploratorio (EDA):** Estadísticas del conteo de palabras e identificación de las más frecuentes mediante una **Nube de Palabras (Word Cloud)**.
- **Análisis de Sentimiento Global:** Clasificación general del tono de la obra empleando modelos basados en la librería `pysentimiento`.
- **Curva de Ritmo Emocional:** Mapeo secuencial del estado de ánimo del texto, ideal para identificar clímax o monotonía narrativa.
- **Interfaz Gráfica Interactiva:** Panel dinámico construido con `ipywidgets` que permite al usuario ingresar cualquier título y texto para analizarlo en tiempo real.

## 🛠️ Requisitos e Instalación

Para ejecutar este cuaderno en tu entorno local, asegúrate de tener Python instalado y sigue estos pasos:

1. Clona o descarga este repositorio en tu computadora.
2. Instala las dependencias necesarias utilizando el archivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

## 💻 Instrucciones de Uso
1. Abre el archivo trabajo_nlp.ipynb en tu entorno de Jupyter (Jupyter Notebook, JupyterLab o VS Code).
2. Ejecuta las celdas en orden secuencial (Kernel -> Restart & Run All).
3. Al final del cuaderno, interactúa con la interfaz gráfica: escribe el título de tu obra, pega el texto completo en el recuadro y presiona el botón Analizar Escrito 🚀 para ver tu curva emocional personalizada.