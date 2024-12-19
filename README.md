#![Universitat Oberta de Catalunya](https://www.uoc.edu/portal/_resources/common/imatges/sala_de_premsa/noticies/2016/202-nova-marca-uoc.jpg)

**Máster en Ciencia de Datos**
**Área 2: Machine Learning in Cybersecurity**

# Desafíos y optimización en sistemas de detección de intrusiones (IDS) basados en comportamiento

**Autor**: Ivan Benajes Trenchs  
**Tutor/a de TF**: Blas Torregrosa García  
**Profesor/a responsable de la asignatura**: Josep Anton Mir Tutusaus  


## Introducción
Los sistemas de detección de intrusiones (IDS, por sus siglas en inglés) son una pieza fundamental en la ciberseguridad moderna, encargados de identificar actividades sospechosas y comportamientos maliciosos en redes y sistemas. No obstante, muchos IDS actuales enfrentan desafíos importantes debido a las tasas elevadas de falsos positivos y falsos positivos, así como dificultades para detectar ataques más sofisticados o modernos, que van evolucionando a lo largo del tiempo.

Este proyecto se centra en tratar de optimizar los sistemas IDS basados en comportamiento mediante el uso de técnicas de aprendizaje incremental basado en técnicas de knowledge distillation y memory buffer. La idea principal es mejorar la adaptabilidad de los modelos a lo largo del tiempo manteniendo la precisión en la detección de comportamientos anómalos, tratando de reducir así los falsos positivos que dificultan la gestión de incidentes de seguridad.

Para ello, se utiliza el dataset CIC-IDS2018, un conjunto de datos ampliamente reconocido en la investigación de ciberseguridad que incluye múltiples tipos de ataques y tráfico de red simulando un entorno realista. 

Este trabajo se enmarca dentro del Máster en Ciencia de Datos de la Universitat Oberta de Catalunya (UOC), con un enfoque en el área de Machine Learning aplicado a la ciberseguridad.

## Estructura y descripción
Este repositorio contiene el código fuente y los tres modelos resultantes de mismo que se han utilizado para llevar a cabo la comparativa entre estos dentro de un entorno que intenta simular la realidad de un entorno productivo y cambiante a lo largo del tiempo.

-   **`01. Código`**   
    -   Esta carpeta contiene todos los archivos en formato Jupyter Notebook, cada uno con el código fuente utilizado en el proyecto, así como comentarios específicos de los resultados obtenidos.
    -  **`TFM_DS_01_binary_dataset_analysis_ibenaiges.ipynb`**
	    -   **Descripción**: en este notebook se realiza un análisis exploratorio del conjunto de datos, de forma que se inspeccionan las características del conjunto de datos, las distribuciones, se realiza un preprocesamiento de valores ausentes y se evalúan correlaciones entre las variables del dataset.
	    -   **Objetivo**: entender y preparar los datos antes de aplicar técnicas y crear modelos de deep learning.
	-  **`TFM_DS_02_binary_static_model_ibenaiges.ipynb`**
	    -   **Descripción**: en este notebook se implementa, entrena y evalúa un modelo de detección de intrusiones estático, que no se actualiza con nuevas muestras de datos.
	    -   **Objetivo**: crear una línea base para comparar con otros enfoques.
	- **`TFM_DS_03_binary_static_window_model_ibenaiges.ipynb`**
	    -   **Descripción**: en este notebook se implementa, entrena y evalúa un modelo basado en ventanas deslizantes, donde los datos son procesados en bloques temporales dentro de unas ventanas de tiempo definidas.
	    -   **Objetivo**: evaluar cómo el modelo maneja datos dinámicos divididos en períodos o bloques y cómo es el modelo resultante frente a otros modelos.
	-  **`TFM_DS_04_binary_incremental_model_ibenaiges.ipynb`**
	    -   **Descripción**: en este notebook se implementa, entrena y evalúa un modelo incremental basado en las técnicas distillation knowledge y memory buffer, que se adapta a nuevos datos de forma continua.
	    -   **Objetivo**: comparar el rendimiento y adaptabilidad del modelo incremental frente a los modelos estáticos y de ventana deslizante, para comprobar si realmente es una solución viable y que puede mejorar los resultados actuales.

-   **`02. Modelos`**  
    -   Contiene los modelos desarrollados resultantes organizados en subcarpetas según el enfoque utilizado, para una mayor facilidad en determinar a cual corresponde cada uno.
    -   **Subcarpetas**:
        -   **`01. Static model`**: modelo entrenados con datos estáticos sin actualización periódica.
        -   **`02. Sliding window model`**: tres modelos entrenados utilizando diferentes ventanas deslizantes de datos.
        -   **`03. Incremental model`**: diferentes iteraciones del modelo que aprende de forma incremental a partir de nuevas muestras de datos, con un total de 10 debido a un total de 10 entrenamientos incrementales realizados.

-   **`LICENSE`**   
    -   Archivo que especifica la licencia del proyecto, en este caso, la **Reconocimiento-NoComercial-SinObrasDerivadas 3.0 España (BY-NC-ND 3.0)**.
    - 
-   **`README.md`**    
    -  El presente documento, que documenta el propósito y detalles del proyecto.

## Licencia
Este proyecto está licenciado bajo la Licencia Creative Commons Reconocimiento-NoComercial-SinObrasDerivadas 3.0 España. Consulta el archivo `LICENSE` para más detalles.