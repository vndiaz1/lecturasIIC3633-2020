# Crítica de *Collaborative Filtering for Implicit Feedback Datasets*

Este *paper*, como lo dice su título, presenta un sistema recomendador que utiliza un modelo de factores con preferencias que tienen distintos niveles de confianza para un set de datos con información implícita. 

### Resumen

Al comienzo, se presenta una introducción del tema en donde explican el por qué utilizar datos implícitos es un problema más desafiante que con datos explícitos. También, explican de forma breve tanto el modelo de FC de vecinos cercanos, como el de factores latentes, el que de este último se basa el modelo propuesto. 

Después, presentan su modelo desarrollado que utiliza dos variables principales, una binaria que representa si un usuario ha visto o no un cierto ítem y el nivel de confianza que tiene la variable anterior. Con estas, generan un problema de optimización con la función objetivo típica de factores latentes con regularización, pero agregando el nivel de confianza multiplicando al error. También, en vez de utilizar el descenso de gradiente estocástico para resolver el problema, utilizan el proceso de optimización de **mínimos cuadrados alternados** para hacer más eficiente el cálculo. Esta técnica, además de utilizar menos recursos, permite generar una explicación para los resultados de la recomendación. 

Luego, realizan experimentos para mostrar el funcionamiento de este modelo en comparación a los existentes, utilizando un *dataset* de programas de televisión, Estos son evaluados mediante un rango de percentiles  en donde se ordenan por orden de preferencia los programas que más ven los usuarios. 

Por último, analizan los resultados obtenidos y concluyen las ventajas que tiene este modelo con respecto a los otros, pero también indicando que todavía se puede mejorar el rendimiento si se aumenta el costo computacional.

### Comentarios

A pesar de que no utilizaron figuras para explicar su modelo, se pudo entender de buena manera gracias a las ecuaciones utilizadas y a lo ordenado del artículo.

Encontré interesante el cambio de técnica para entrenar el modelo, ya que con tantos datos no se puede utilizar de buena manera el descenso de gradiente. Por esto, el hecho de utilizar mínimos cuadrados alternados fue una muy buena solución. Además, con esta técnica pudieron generar un algoritmo que explica las recomendaciones que entrega su modelo, lo que lo hace más confiable y fácil de comprobar su desempeño.

Me gustó el preprocesamiento de la base de datos que realizaron para poder hacer los experimentos de la forma más objetiva posible y comparar bien los desempeños de los modelos. Esto lo digo cuando hablan sobre de quitar los programas de televisión en el set de test que ya estaban en el entrenamiento, para que así no se obtengan desempeños poco reales y robustos. Sin embargo, me hubiera gustado si hubiesen agregado otra base de datos distinta para comprobar la robustez de su modelo.

A modo general, encontré bueno el artículo gracias a su capacidad de explicar las cosas de forma sencilla pero abarcando todo lo necesario para comprender de buena manera el modelo que estaban proponiendo. También, encuentro más difícil el tema de hacer sistemas recomendadores con datos implícitos, por lo le doy bastante mérito a la forma de cómo enfrentaron este problema.