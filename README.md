# proyectofinal

*Indroduccion al proyecto*

El proyecto consiste en el desarrollo de un asesor inteligente para la reventa de artículos de moda. Hoy en dia existen múltiples plataformas dedicadas a la segunda mano, destacando entre ellas Vestiaire Collective, especializada en moda de lujo, y Vinted, más enfocada en ropa vintage o simplemente en dar salida a prendas que ya no se usan, sin importar tanto la marca. Esta diferencia de enfoque hace que el precio medio de los productos en Vinted —incluso tratándose de artículos de lujo— sea considerablemente más bajo que en Vestiaire, lo que representa una oportunidad clara de negocio si se tiene buen ojo para identificar qué prendas pueden tener salida.

Este análisis y toma de decisiones siempre han sido un proceso mental que he desarrollado durante años dedicándome a la reventa. Sin embargo, al iniciar este curso, comprendí que con el uso de herramientas de inteligencia artificial se puede sistematizar y acelerar este proceso de forma significativa.

Para ello, trabajamos con dos bases de datos: una extraída de Vestiaire, que contiene alrededor de 900.000 artículos junto a 36 características por entrada (relacionadas tanto con el producto como con el usuario), y otra obtenida de Vinted, más limitada en tamaño debido a las restricciones de scrapeo, pero igualmente valiosa para el análisis comparativo y la construcción del modelo predictivo.

Para acotar el estudio y agilizar la ejecución del código, hemos reducido el tamaño de los datasets, centrándonos únicamente en una selección de marcas. Estas marcas han sido elegidas en base a mi experiencia en la reventa, ya que son algunas de las que he trabajado durante estos años y sé que tienen potencial de venta. No obstante, uno de los objetivos del proyecto es precisamente descubrir qué otras marcas podrían tener salida en este tipo de mercado.

En el caso del dataset de Vestiaire, hemos filtrado únicamente los productos que ya han sido vendidos, lo cual es clave para poder entrenar posteriormente los modelos de regresión orientados a la predicción de precios reales de venta.

Para el dataset de Vinted, durante el proceso de scrapeo se estableció un límite máximo de precio de 150 €, ya que a partir de ese umbral los precios en ambas plataformas tienden a igualarse y, desde el punto de vista de inversión, los artículos por encima de ese rango suelen tener una rotación mucho más lenta y quedar "apalancados".

Con el objetivo de visualizar de forma clara la diferencia de precios entre ambas plataformas, también hemos limitado el dataset de Vestiaire a productos de hasta 150 €. A partir de ahí, generamos gráficos de violín y boxplots que nos permiten comparar la distribución de precios en ambos casos.

![image](https://github.com/user-attachments/assets/62d87718-0a48-4520-81a5-8df1bd88f455)
![image](https://github.com/user-attachments/assets/e2acf6a9-1daf-45cb-adab-5015d85df683)

