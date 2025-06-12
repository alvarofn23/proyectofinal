# 👕MACHINE LEARNING APLICADO A LA PREDICCIÓN DE PRECIOS DE ARTÍCULOS DE LUJO
***

Este repositorio contiene un análisis de los articulos que se venden en plataformas de reventa (Vinted y Vestiaire) y la prediccion de sus precios, constando de las siguientes fases:

- Adquisición de datos: Scrapeados dede APIs
- Preprocesamiento de datos: Limpieza, transformación y preparación de los datos para el modelado.
- Modelado predictivo: Construcción y evaluación de modelos de machine learning para predecir los precios de los articulos.
- Modelado categorico: Clasificacion del tipo e inversion segun los precios predichos por los modelos.
- Visualización de resultados: Creación de visualizaciones para complementar la informacion de los moelos.
- Se utilizan diversas herramientas y tecnologías, destacando el uso extensivo de Jupyter Notebooks para la manipulación, análisis y modelado de datos.



# 📂Estructura del repositorio
---
```
├── Aplicativos/
│   ├── PROYECTO.pbix
│   ├── proyecto final.ows
├── Datos/
│   ├── Filtered_Vestiaire_.csv
│   ├── Vinted Scraper b.csv
│   ├── Vinted_Investment_Categorization (2).csv
│   ├── Vinted_Price_Estimates_with_MLP.csv
│   ├── Vinted_Scraper_adapted (2).csv
├── Scripts/
│   ├── comparacion-de-modelos y categorizacion.ipynb
│   ├── extraer-precios-vinted.ipynb
│   ├── proyecto-final-eda.ipynb
│   └── proyecto-final-modelo.ipynb
├── Proyectofinal_memoria.pdf
└── README.md
```

# 📂Detalles del repositorio
---
1. Aplicativos
   - PROYECTO.pbix: Visualizaciones de PowerBI
   - proyecto final.ows: Visualizaciones de Orange

2. Datos
   - Filtered_Vestiaire_.csv: Dataset de Vestiaire despues del filtrado con SQL
     ![image](https://github.com/user-attachments/assets/e1a0a2b8-24dc-46cf-b59e-bfd3259aa928)

   - Vinted Scraper b.csv: Dataset scrapeado de Vinted
     ![image](https://github.com/user-attachments/assets/c52abb9c-659c-497c-8f2c-9e3cdb83ad61)

   - Vinted_Scraper_adapted (2).csv: Dataset de Vinted adaptado a la estructura del de Vestiaire
     ![image](https://github.com/user-attachments/assets/a8984de4-ed0b-430d-aefb-fb9ae0a237a5)

   - Vinted_Price_Estimates_with_MLP.csv: Dataset de Vinted con la prediccion de los precios en Vestiaire
     ![image](https://github.com/user-attachments/assets/52b0ca3d-02f6-467a-883b-e1d3c9259456)

   - Vinted_Investment_Categorization (2).csv: Dataset de Vinted con la clasificacion de inversion
     ![image](https://github.com/user-attachments/assets/0f37df02-6d7c-4f75-9516-269445db9d86)

3. Scripts
   - proyecto-final-eda.ipynb: script con el EDA y algunas visualizaciones de python
     
   - proyecto-final-modelo.ipynb: script con el modelo de regresion para los articulos de Vestiaire
     
     1. Filtrado y preparacion de datos
        
        ![image](https://github.com/user-attachments/assets/ce5f37f3-a521-49b2-8c17-7d0d1e99f816)
        ![image](https://github.com/user-attachments/assets/7c695c7e-6ca3-4ea1-8c7b-a8f540576e2c)
  
        ---
        
     2. Separacion en entrenamiento y prueba
        
        ![image](https://github.com/user-attachments/assets/d93d9a6d-dd0e-44ae-aaec-d262dcd47357)
        ![image](https://github.com/user-attachments/assets/bbb0ed42-d969-4063-b5f3-d8d0d4b73bc6)
        ![image](https://github.com/user-attachments/assets/0a8e0bc7-7c39-482b-bfad-2fc14fc7630e)
        ![image](https://github.com/user-attachments/assets/cd1a2a00-3fe8-4a13-9e7d-73fca2dcce96)
  
        ---
     3. Modelo Lightgbm
        
        ![image](https://github.com/user-attachments/assets/9b533710-fe3f-4bdc-80dd-a965a652d9bd)
        ![image](https://github.com/user-attachments/assets/85f683da-ab91-4a84-ac06-2e5f5072981c)
        ![image](https://github.com/user-attachments/assets/64df2981-d5a7-4834-8423-7305a0ba1ccd)
  
        ---
     4. Comprobacion y visualizacion
        
        ![image](https://github.com/user-attachments/assets/93b7a120-5f55-4504-86a4-91159da02a7a)
        ![image](https://github.com/user-attachments/assets/e8ee334b-8edd-4f5a-88a1-5594fbf6596f)
        ![image](https://github.com/user-attachments/assets/7df28d9c-89e6-4db4-beef-8d215bf950e0)

   - extraer-precios-vinted.ipynb: script que extrae los precios de la columna product_name filtra, traduce y adapta la estructura a la del dataset de Vestiaire

     1. Extraccion del precio
        
        ![image](https://github.com/user-attachments/assets/fe8d200a-2abf-4d95-a556-5424c7a6a71a)
  
        ---

     2. Filtrado, traduccion y adaptacion del dataset
    
        ![image](https://github.com/user-attachments/assets/78cf91a8-86ab-4097-a073-615a87cf8bf8)
        ![image](https://github.com/user-attachments/assets/c05fdd95-5434-45d8-8624-1c925480730f)

        ---

     - comparacion-de-modelos y categorizacion.ipynb: el script mas importante, evalua y compara los demas modelos, da con el mejor, predice los precios de Vinted y categoriza la inversion

       1. Evaluacion de modelos y prediccion
          
          ![image](https://github.com/user-attachments/assets/4a94390f-e680-41dc-986f-3745968353ec)
          ![image](https://github.com/user-attachments/assets/47e0cda0-b0d1-4abf-a578-703f2f431722)

          ---

       2. Categorizacion de la inversion

          ![image](https://github.com/user-attachments/assets/7958c6a0-4772-4670-b581-1251aad63f43)
          
          ---

# 📈 Flujo de Trabajo del Proyecto


El flujo de trabajo general del proyecto se puede resumir en los siguientes pasos:

1. Adquisición de Datos: Obtención de datos de Vinted y Vestiaire
   
2. Incorporación de Datos: Extraccion, integración y adaptacion de nuevos datos con los datos existentes utilizando Scripts/extraer-precios-vinted.ipynb.
   
3. Análisis Exploratorio de Datos (EDA): Realización de un EDA para comprender las características de los datos utilizando Scripts/proyecto-final-eda.ipynb.
   
4. Preprocesamiento de Datos: Limpieza y transformación de los datos
   
5. Modelado, construcción y entrenamiento del modelo utilizando Scripts/proyecto-final-modelo.ipynb

6. Comparacion de modelos, busqueda del mejor prediccion final y categorizacion de las inversiones Scripts/comparacion-de-modelos y categorizacion.ipynb.

7. Visualización: Creación de visualizaciones para comunicar los resultados del proyecto utilizando tabmien Scripts/comparacion-de-modelos y categorizacion.ipynb. y Power BI.

8. Documentación: Documentación del proyecto en Proyectofinal_memoria.pdf y README.md.

---


        







  




