# StudyBot 2.0: Asistente Avanzado para la Organización del Estudio

## 1. Introducción

StudyBot 2.0 es un chatbot híbrido desarrollado en Python diseñado para interactuar con el usuario mediante una interfaz gráfica integrada. Su objetivo es actuar como un **Asistente de Diagnóstico Académico**, guiando al estudiante a través de un flujo estructurado de 10 interacciones consecutivas. Al finalizar, el sistema procesa los datos recolectados para generar un informe personalizado con conclusiones y estrategias de mejora técnica.

El proyecto combina el poder de las máquinas de estado secuenciales para garantizar la coherencia del diálogo y técnicas de **Procesamiento de Lenguaje Natural (NLP)** mediante la biblioteca **spaCy** para la extracción inteligente de entidades (como nombres propios), evitando almacenar texto basura o saludos dentro de las variables del usuario.

**Nota:** Este proyecto corresponde al curso *Taller de Inteligencia Artificial* del Magíster en Data Science impartido por la Universidad de Las Américas (UDLA), Chile.

---

## 2. Requisitos e Instalación de Librerías

Para la ejecución correcta de este chatbot dentro de un entorno Jupyter Notebook (.ipynb), se requieren las siguientes dependencias:

### 2.1 spaCy y Modelo de Lenguaje
Utilizada para el análisis lingüístico y el etiquetado gramatical (POS Tagging):
pip install spacy
python -m spacy download es_core_news_sm

### 2.2 Gradio
Biblioteca encargada de desplegar la interfaz gráfica web directamente sobre las celdas del notebook, eliminando la necesidad de interactuar por la consola nativa:
pip install gradio

---

## 3. Arquitectura del Sistema y Flujo de Datos

El sistema se compone de cuatro capas principales que operan en cascada de la siguiente manera:

```text
       [ Usuario Interactúa en Interfaz Web ]
                         │
                         ▼
            [ Capa de Entrada (Gradio) ]
                         │
                         ▼
          [ Capa NLP (Análisis con spaCy) ]
     (Aísla el nombre real de saludos iniciales)
                         │
                         ▼
       [ Máquina de Estados (Matriz de 10 Pasos) ]
  (Registra: Asignatura -> Horas -> Distracciones...)
                         │
                         ▼
       [ Generador de Conclusiones Dinámicas ]
  (Genera plan personalizado usando reglas lógicas)
```

## 4. Componentes Clave del Desarrollo

### 4.1 Extracción Inteligente con NLP
A diferencia de los enfoques rígidos, StudyBot 2.0 procesa gramaticalmente la introducción del usuario. Si el alumno responde "Me llamo Adán", spaCy detecta el token catalogado como PROPN (Nombre Propio) y extrae únicamente la entidad de valor (Adán). Además, cuenta con un filtro de contención que detecta saludos iniciales preventivos.

### 4.2 Gestión del Diálogo (Garantía de 10 Respuestas)
Para cumplir rigurosamente con los requisitos de evaluación de coherencia continua, el chatbot implementa una lista indexada de estados (ESTADOS). Esto asegura que el bot mantenga el hilo conductor a través de 10 preguntas lógicas sin desviarse del objetivo:

1. PEDIR_NOMBRE
2. PEDIR_ASIGNATURA
3. PEDIR_HORAS
4. PEDIR_DIFICULTAD
5. PEDIR_APUNTES
6. PEDIR_DISTRACCIONES
7. PEDIR_HORARIO
8. PEDIR_EVALUACION
9. PEDIR_ESTRES
10. PEDIR_META

### 4.3 Módulo de Conclusión Dinámica
En el último estado, el bot invoca la función generar_plan_estudio(). Esta función no arroja una respuesta estática, sino que analiza las variables guardadas en el perfil:
* Si el número de horas es bajo, prescribe un aumento controlado del tiempo.
* Si detecta palabras clave como "celular" o "redes" en las distracciones, genera una recomendación específica para bloquear pantallas (ej. método Pomodoro o app Forest).

---

## 5. Diseño de la Interfaz Gráfica

La vista del usuario fue migrada a gr.ChatInterface. Se eliminaron los botones y ejemplos flotantes que causaban interrupciones del flujo secuencial en versiones anteriores de Gradio, logrando una barra de texto limpia y un entorno visual interactivo directamente montado sobre el Notebook, mejorando drásticamente la experiencia de usuario en comparación con la lectura clásica por consola de comandos.

---

## 6. Conclusiones

StudyBot 2.0 demuestra de forma práctica cómo los conceptos fundamentales de la Inteligencia Artificial y el Procesamiento de Lenguaje Natural (NLP) pueden integrarse con lógica algorítmica tradicional para resolver problemas reales de productividad y educación. La inclusión de spaCy eleva la robustez del software, transformándolo de una simple captura de datos a un analizador textual básico pero eficiente para la comunidad académica.
