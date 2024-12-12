# Práctica 2 FSI 

**Redes Convolutivas**  
*Realizado por Juan Antonio Hernández Rodríguez y Acaymo Jesús Granado Sánchez*

## Introducción

En esta práctica de **Fundamentos de los Sistemas Inteligentes (FSI)**, se desarrollará e implementará varios modelos de redes neuronales convolutivas (CNN) para la clasificación de imágenes a partir de unos datasets escogidos en Kaggle. Las redes neuronales convolutivas son una de las técnicas más avanzadas en el campo del aprendizaje profundo, destacándose por su capacidad para extraer características relevantes de datos visuales de manera eficiente. 
Durante esta práctica, se trabajará con un conjunto de datos de imágenes predefinido y entrenando varios modelos que permitan clasificar dichas imágenes en sus respectivas categorías. Este ejercicio tiene como objetivo proporcionar una comprensión práctica del funcionamiento de las CNNs, así como de los procesos de aprendizaje por transferencia, entrenamiento mediante el descenso del gradiente, evaluación de los modelos y ajustes del modelo para que devuelva unos resultados optimos

## Datasets

Para esta práctica se han seleccionado dos conjuntos de datos disponibles en Kaggle, los cuales ofrecen desafíos interesantes en el contexto de la clasificación de imágenes. El primer conjunto es **Vehicles Image Dataset** ([enlace](https://www.kaggle.com/datasets/mmohaiminulislam/vehicles-image-dataset)), que contiene imágenes de diferentes tipos de vehículos, organizados en múltiples categorías de los cuales se cogerán las siguientes clases: "biclycle", "motorcycle", "bus" y "car". Este dataset es ideal para explorar la capacidad del modelo de identificar patrones visuales asociados a clases específicas de vehículos. 

El segundo conjunto es **Armenian Coins Dataset** ([enlace](https://www.kaggle.com/datasets/gorororororo23/armenian-coins-data)), que incluye imágenes de monedas armenias de varias denominaciones y estilos. Este dataset ofrece un enfoque en la clasificación basada en características más sutiles, como los detalles visuales y texturas presentes en las monedas. Ambos conjuntos permitirán probar la eficacia del modelo en dominios con características visuales distintas y evaluar su capacidad generalizadora.


## Resultados del Entrenamiento

Para el entrenamiento de ambos modelos se utilizó Data Augmentation, una técnica fundamental en el aprendizaje profundo para mejorar la generalización y la robustez de los modelos, especialmente cuando se trabaja con conjuntos de datos limitados. Esta técnica introduce variaciones en las imágenes de entrenamiento mediante transformaciones controladas, permitiendo que los modelos sean menos propensos al sobreajuste y más capaces de adaptarse a datos no vistos.

Entre las transformaciones aplicadas se incluyeron rotaciones aleatorias, que ayudan al modelo a reconocer patrones independientemente de la orientación; recortes redimensionados, que simulan diferentes perspectivas y escalas de los objetos; y alteraciones en el brillo, contraste, saturación y tonalidad de color, lo que imita variaciones en las condiciones de iluminación o calidad de las imágenes. Además, se añadieron reflejos horizontales aleatorios, que son particularmente útiles para mejorar la capacidad del modelo para identificar simetrías en los datos.

El primer modelo fue un modelo de **aprendizaje por transferencia** basado en ResNet50, modificado con capas completamente conectadas, dropout. Este modelo fue entrenado sobre el conjunto de datos **Vehicles Image Dataset** durante 10 épocas. En la siguiente gráfica se muestra la evolución de la pérdida de entrenamiento y validación, así como la precisión de validación a lo largo del proceso de entrenamiento.

![Training1](https://github.com/user-attachments/assets/75a87eb6-de2a-4975-8134-b8abee8d0cfb)

![Gráfica del entrenamiento ResNet50](https://github.com/user-attachments/assets/cb2998db-2fef-45f5-9d40-2f1bf74c76cd)

El segundo modelo fue una **red neuronal convolutiva personalizada (ConvNet)** diseñada para trabajar con el conjunto de datos **Armenian Coins Dataset**. Esta arquitectura incluyó múltiples capas convolucionales con normalización por lotes, max pooling y capas completamente conectadas. Fue entrenada durante 30 épocas, logrando un excelente desempeño. A continuación, se presenta la figura correspondiente al entrenamiento de este modelo y la gráfica de pérdida y precisión del testeo del modeo.

![Training2](https://github.com/user-attachments/assets/9724b9dc-d2ed-4366-9e14-b700f1c61ddc)

![Gráfica del entrenamiento ConvNet](https://github.com/user-attachments/assets/c9150473-b470-46f4-9a62-4f3b0fb8ad3c)


### Matrices de Confusión

Finalmente, se generaron las matrices de confusión para ambos modelos, las cuales proporcionan un análisis detallado del desempeño en la clasificación. Estas matrices permiten observar en qué categorías el modelo tuvo más dificultades con respecto a las predichas, así como identificar posibles fuentes de error.

1. **Matriz de confusión para Vehicles Image Dataset (ResNet50):**

![Matriz de confusión ResNet50](https://github.com/user-attachments/assets/695675d0-154e-4a5d-a5c5-9bf065927e97)

2. **Matriz de confusión para Armenian Coins Dataset (ConvNet):**

![Matriz de confusión ConvNet](https://github.com/user-attachments/assets/a08733cc-5dee-4cc2-9f46-7440305de44d)
