PRESENTACION: https://prezi.com/view/ZjlOylcF7DaylDDERls4/
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

# EDA

Vamos a proceder con el EDA para entender mejor los datos de Vestiaire:

![image](https://github.com/user-attachments/assets/ba40d083-38a2-436b-ae9c-38812aac6c7f)
![image](https://github.com/user-attachments/assets/ba846a72-c0ed-4783-98b7-5c1ca7ad1d2a)
![image](https://github.com/user-attachments/assets/f67897a2-a957-4227-89a0-62aabb794887)
![image](https://github.com/user-attachments/assets/4692a887-6815-4dd0-96e5-e50037944f49)
![image](https://github.com/user-attachments/assets/32dea084-b04b-4738-b472-1cecaa23514d)
![image](https://github.com/user-attachments/assets/6e24a2fc-2511-4039-bb53-ec405542eebb)
![image](https://github.com/user-attachments/assets/96e9a3ca-e8c3-49ae-a175-cdcb17ee9e56)
![image](https://github.com/user-attachments/assets/10f1e88c-a56d-449c-be88-2faf6db5b7b3)
![image](https://github.com/user-attachments/assets/9736e10b-ec1d-4525-91c0-3414a9a7f0df)
![image](https://github.com/user-attachments/assets/41f9128b-409b-4d80-8dc3-eb1b1f41577e)
![image](https://github.com/user-attachments/assets/9d8c8a3d-c1a0-47fe-8d8e-5eff2a3936ad)
![image](https://github.com/user-attachments/assets/afef027f-d9dd-4d7e-b1f4-f71c5fcb2269)
![image](https://github.com/user-attachments/assets/406a55f2-070e-4470-bf0a-8ab67f42b2f5)
![image](https://github.com/user-attachments/assets/d7a9f08a-5f4c-4477-a083-11feb3ed82ad)
![image](https://github.com/user-attachments/assets/3c5a0853-52e2-498a-a7bf-aa3e3548ff3d)
![image](https://github.com/user-attachments/assets/17db4335-3798-46ab-bac8-46c317c013e7)
Resumen General
Total de productos analizados: 12,719

Cantidad de marcas distintas: 19

Marca más frecuente: Gucci

Categoría más común: Women Shoes

Condición más común: Very good condition

Precio promedio (USD): 283.93 $

Ganancia media del vendedor: 208.06 $

Promedio de "likes" por producto: 19.84

Productos vendidos:

![image](https://github.com/user-attachments/assets/b4b6da41-aadb-4f5b-b83a-4e87e801fe49)
![image](https://github.com/user-attachments/assets/ac923729-2d53-4480-98ae-fce40265541e)
![image](https://github.com/user-attachments/assets/62095838-1d5c-4633-9e95-520b10a51a10)

*(añadir capturas de orange y powerbi)*


* TABLA DE LOS USUARIOS CON MAYORES INGRESOS DE LA APLICACION.
* potencial para incluir una Categoria de Vendedor Pro y asi incentivar las ventas a la vez que ganas dinero con la cuota de la suscripcion
![image](https://github.com/user-attachments/assets/1f086460-6506-4f89-bce3-044ce022215a)



