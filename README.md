# Clasificador borroso interpretable para la determinación del perfil inversor mediante aprendizaje automático y lógica difusa

En este repositorio se aloja el código desarrollado para el Trabajo Fin de Máster del Máster en Tratamiento Estadístico-Computacional de la Información (TECI), impartido conjuntamente por la Universidad Complutense de Madrid y la Universidad Politécnica de Madrid.

## Resumen
Los gestores automatizados que tratan de establecer perfiles de inversión, lo hacen mediante cuestionarios estáticos que, según evidencia empírica reciente, no reflejan el comportamiento real de los clientes en el mercado. Ademas, la normativa MiFID II exige que dicha clasificación sea explicable lo que choca con el carácter de "caja negra" de los algoritmos de machine learning capaces de modelar ese comportamiento real. Este trabajo adapta al contexto financiero la metodología propuesta por Noroozi et al. (2024) en el ambito aeronautico, con el objetivo de diseñar un clasificador borroso para la determinación del perfil inversor que integre modelos ensemble y análisis SHAP, proporcionando una herramienta transparente y explicable. A partir del conjunto de datos FAR-Trans, se construyeron variables transaccionales para 12.613 clientes activos. Mediante reducción de dimensionalidad con UMAP y clustering con HDBSCAN se identificaron cinco perfiles de comportamiento, posteriormente reproducidos por un modelo subrogante (CatBoost) con un desempeño cercano al 0.99 de F1-score. El análisis SHAP permitió extraer las variables más relevantes para cada perfil, y árboles de decisión de profundidad reducida se emplearon para definir umbrales naturales que dieron forma a funciones de pertenencia sigmoidales. Sobre esta base se construyó un clasificador difuso tipo Wang-Mendel de 67 reglas SI-ENTONCES.El sistema alcanzó un accuracy de 0.96 (macro avg 0.88), clasificando todas las instancias en cinco perfiles interpretables: Inversor de cartera dinámica, de cartera en crecimiento, de ciclo único, de compra única y de huella latente. Las reglas generadas permiten describir en lenguaje natural el comportamiento de cada segmento, ofreciendo una herramienta auditable y comprensible para analistas financieros y reguladores, con interpretabilidad tanto global como local.

El código está dividido en cuatro Notebooks: 

En el primero (TFM_RMAT_DATOS.ipynb) se puede encontrar los comando para obtener la base consolidada

El segundo (TFM-RMAT-INGENIERA_DE_VARIABLES.ipynb) contiene las variables generadas y la base reducida donde la unidad de analisis es el cliente. 

El tercer (TFM-RMAT-EDA.ipynb) contiene el analisis exploratorio de datos sobre la base de clientes. 

Y el último (TFM-RMAT-RESULTADOS.ipynb) incluye los algoritmos UMAP, HDBSCAN hasta llegar al clasificador difuso. 

Las bases usadas en TFM_RMAT_DATOS.ipynb son las presentadas por https://arxiv.org/abs/2407.08692 
