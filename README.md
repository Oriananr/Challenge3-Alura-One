**Challenge Telecom X: Análisis de evasión de clientes. Parte II**

Programa de formación Oracle ONE / 8 (Oracle Next Education) - Especialización en Data Science, patrocinado por Oracle y Alura Latam.

Fecha:13-08-2025
Nombre alumna: Oriana Ortiz.


**1. Introducción**

Dentro del programa Oracle ONE (Oracle Next Education) - Alura Latam, la realización de una serie de Challenges se contempla como una parte fundamental de la formación de los becarios. Esta metodología de aprendizaje, desarrollada por Apple, se basa en exponer a los alumnos a situaciones reales y complejas.

El presente Challenge corresponde al tercero y último de la serie. El objetivo principal de este proyecto fue construir un modelo predictivo capaz de identificar a los clientes en riesgo de abandono (churn), una tarea crítica para la retención de clientes. Debido al desbalance de clases inherente en los datos, donde la clase de abandono (1) es minoritaria, la métrica clave fue el "recall", que mide la capacidad del modelo para identificar correctamente a los clientes que realmente abandonan el servicio.

El modelo final, un Random Forest, no solo demostró un rendimiento superior, sino que también validó la importancia de una metodología rigurosa para superar los desafíos de los datos.

**2. Metodología**

La metodología se centró en un enfoque iterativo para superar las limitaciones de los datos:

Se utilizó una división simple de "train_test_split" para obtener un primer modelo de referencia. El resultado fue un "recall" porfiadamente bajo (0.49), lo que inicialmente sugirió que el modelo era ineficaz.

Hipótesis de Ponderación de Clases: Para abordar el desbalance, se probó la ponderación de clases ("class_weight"), esperando una mejora. Sin embargo, un "screening" de diferentes pesos de clase demostró que esta técnica no mejoró significativamente el rendimiento, lo que llevó a la conclusión de que la causa raíz del bajo "recall" era más profunda.

El análisis demostró que el bajo "recall" no era un problema del modelo, sino un problema de los datos y su evaluación. La frontera de decisión borrosa entre los clientes que abandonan y los que no, hacía que el modelo no pudiera aprender a diferenciarlos adecuadamente con los datos desbalanceados.

Para resolver este problema, se implementó NearMiss, una técnica de submuestreo que equilibra los datos de entrenamiento al enfocarse en los casos más difíciles y relevantes. Esta intervención estratégica permitió al modelo aprender la verdadera naturaleza de la clase minoritaria.

Validación Robusta: Para obtener una evaluación fiable y final, se utilizó la validación cruzada (cross_validate) en el modelo optimizado. Este método proporcionó un "recall" promedio de 0.69, demostrando que el modelo era consistentemente efectivo en diferentes subconjuntos de datos.

**Resultados y Conclusiones**

El modelo final de Random Forest, optimizado con NearMiss y validado con cross_validate, superó con "creces" el rendimiento del modelo inicial. 

El "recall" de 0.69 es un resultado sólido que demuestra que el modelo es una herramienta valiosa para identificar a los clientes en riesgo, con la capacidad de capturar a la mayoría de ellos.

Este proyecto ha demostrado que el éxito en el modelado predictivo no solo depende de la elección del algoritmo, sino de una metodología rigurosa que incluye la correcta identificación del problema de los datos y una evaluación robusta. 

La inversión de tiempo en esta metodología, en lugar de una optimización ciega, fue crucial para lograr un modelo confiable. Aunque la optimización del "recall" podría continuar, el modelo actual es más que suficiente para cumplir con los objetivos del negocio.


