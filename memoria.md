**MACHINE LEARNING APLICADO A LA PREDICCIÓN DE PRECIOS DE ARTÍCULOS DE LUJO**



El proyecto consiste en un asesor de reventa de artículos de moda. Existen muchas plataforma de reventa de ropa como Vestiaire que se centra en artículos de lujo o Vinted que en principio no apunta tanto hacia el lujo sino más por lo vintage o simplemente darle salida a ropa que no se usa, independientemente de la marca y eso hace que la media del precio de los productos (incluso los de lujo) sea más baja que la de Vestiaire, lo que es una oportunidad de negocio si sabes reconocer las prendas que pueden tener salida. Esto siempre ha sido un proceso mental mío durante todos estos años de dedicarme a la reventa y cuando empecé este curso me di cuenta de que con la inteligencia artificial se podría agilizar mucho este proceso.



**LAS BASES DE DATOS DEL PROYECTO**

Constamos de dos bases de datos:


- El dataset de **Vestiaire** consta de 900000 artículos que están subidos a la plataforma con sus correspondientes características (36 en total) que nos aportan información del artículo y del usuario.** Lo hemos limitado a productos vendidos, lo cual es esencial para más adelante entrenar los modelos de regresión de precios, además hemos filtrado marcas y lo hemos limitado para agilizar procesos.


![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.001.png)





- Al scrapear el de **Vinted** aplicamos un filtro para scrapear como máximo productos de 150€ ya que a partir de ahí los productos tardan más en venderse y son inversiones más difíciles de rentabilizar.** Además nos hemos encontrado algunos problemas porque tenía una estructura diferente y además la columna del precio estaba vacía. Como el precio sí que estaba incluido en la columna del título hemos tenido que hacer un código para extraer la cifra y agregarla a la columna. El código también traduce palabras del italiano y el francés y adapta las columnas al dataset de Vestiaire, extrayendo la información de la columna del título.

El codigo consigue que pasemos de un dataset poco inteligible a otro mucho mas claro que incluye toda la informacion necesaria (<https://github.com/alvarofn23/proyectofinal/blob/main/extraer-precios-vinted.ipynb>)

En cuanto al tratamiento de valores nulos, habia pocos en los dos datasets pero se 


![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.002.png)










Para visualizar la diferencia de precio de los dos datasets y la **oportunidad de negocio** hemos limitado el de Vestiaire también a 150 y hemos hecho unos gráficos:

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.003.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.004.png)















**APARTADO LEGAL**

El scraping de datos de Vinted o Vestiaire para uso interno y analítico, centrándote en precios y atributos de producto, es legal siempre que:

- No incumplas gravemente sus ToS (limitando volumen y velocidad).
- No infrinjas el derecho sui generis (no copiar bases completas).
- No proceses datos personales sin justificarlo y anonimices todo lo posible.
- No redistribuyas imágenes o descripciones protegidas por copyright.

**ANÁLISIS EXPLORATORIO DE LOS DATOS**

Para la toma de decisiones en la inversión es esencial hacer un buen EDA que nos ayude a saber cuales son las características de los productos mas vendidos.

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.005.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.006.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.007.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.008.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.009.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.010.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.011.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.012.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.013.png)



Con estas visualizaciones podemos saber en qué tipo de marcas, colores y productos conviene más invertir.








**METODOLOGÍA Y MINERÍA DE DATOS**

En este proyecto, estamos aplicando una metodología de minería de datos predictiva y seguimos una serie de pasos que forman parte de una metodología comúnmente conocida como CRISP-DM (Cross-Industry Standard Process for Data Mining). 

El CRISP-DM (*Cross-Industry Standard Process for Data Mining*) es una metodología estándar y ampliamente aceptada para llevar a cabo proyectos de minería de datos. Fue desarrollada en los años 90 por un consorcio de empresas (incluyendo IBM) con el objetivo de crear un enfoque estructurado, aplicable a múltiples industrias.


![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.014.png)















### <a name="_gwc6vxtssjqx"></a>**¿Qué es exactamente?**
- Fases del CRISP-DM

|**Fase**|**Descripción**|
| :-: | :-: |
|**1. Comprensión del negocio**|Entender los objetivos del negocio y cómo la minería de datos puede ayudar a alcanzarlos.|
|**2. Comprensión de los datos**|Recopilar, explorar y describir los datos disponibles para entender su calidad y relevancia.|
|**3. Preparación de los datos**|Limpiar, transformar, seleccionar y estructurar los datos necesarios para el modelado.|
|**4. Modelado**|Aplicar técnicas de modelado (como regresión, árboles de decisión, etc.) y ajustar parámetros.|
|**5. Evaluación**|Verificar si los modelos cumplen los objetivos de negocio y funcionan correctamente.|
|<p>**6. Implementación**</p><p></p><p></p>|<p>Integrar los resultados en el entorno empresarial (puede ser un informe, una app, un dashboard, etc.).</p><p></p><p></p><p></p><p></p><p></p><p></p><p></p>|
**Predicción de precios**

El primer paso para la predicción de los precios que alcanzarán los artículos de vinted en vestiaire es entrenar el modelo de regresión con los propios datos de vestiaire. Hemos filtrado el dataset por productos vendidos y con unas marcas especificas que serán las mismas que hay en el dataset de vinted. Para ello primero vamos a probar con LightGBM y luego con otros para comprobar.

LightGBM es un algoritmo de **machine learning** basado en árboles de decisión, optimizado para **alta velocidad y eficiencia**. Utiliza técnicas como **histogramas** y **crecimiento por hojas** (en lugar de por niveles) para construir árboles más profundos y precisos. Soporta grandes volúmenes de datos y alta dimensionalidad sin pérdida de rendimiento. Funciona muy bien en tareas de clasificación, regresión y ranking. Está diseñado para ser **más rápido y consumir menos memoria** que otros métodos de boosting como XGBoost.

LightGBM funciona construyendo múltiples árboles de decisión de forma secuencial para **minimizar el error de predicción**. En cada iteración, ajusta un nuevo árbol para corregir los errores del modelo anterior, usando el **gradiente de la función de pérdida** (por eso es "gradient boosting"). A diferencia de otros algoritmos, crece los árboles **por hojas** (leaf-wise), eligiendo la hoja con mayor ganancia para dividir, lo que mejora la precisión pero puede sobreajustar si no se controla. Además, usa técnicas como **binning de histogramas** para acelerar el entrenamiento y reducir memoria.


![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.015.png)
## <a name="_bef0hts6ur1x"></a>**Parámetros clave que he usado**

|**Parámetro**|**Función principal**|
| :-: | :-: |
|objective='rmse'|Minimiza el error cuadrático medio.|
|learning\_rate=0.1|Paso de actualización al añadir cada nuevo árbol.|
|n\_estimators=10000|Número máximo de árboles (se detiene antes si converge).|
|max\_depth=5|Profundidad máxima de cada árbol.|
|num\_leaves=62|Número de hojas por árbol (complejidad).|
|subsample=0.9|Uso de una fracción de datos para cada árbol (bagging).|
|colsample\_bytree=0.5|Fracción de features usadas por árbol (feature bagging).|
|reg\_alpha=0.1|Penalización L1 en pesos de los árboles.|
|reg\_lambda=1.0|Penalización L2 en pesos de los árboles.|
|min\_child\_samples=10|Mínimo número de observaciones por hoja.|

Estos hyperparámetros buscan un equilibrio entre **sesgo** (bias) y **varianza** (overfitting).

Una vez explicado el modelo veamos los resultados:

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.016.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.017.png)

Como podemos apreciar, el modelo predice muy bien los precios de los artículos, pasemos ahora a la comparación de modelos para quedarnos con el mejor.









**Otros modelos a considerar para comparar**

Para validar que LightGBM es la mejor opción, conviene compararlo frente a otros enfoques:

|**Modelo**|**Ventajas**|**Cuándo usarlo**|
| :-: | :-: | :-: |
|**XGBoost**|Otro GBDT muy optimizado, con regularización robusta.|Si quieres comparar otras implementaciones GBDT.|
|**CatBoost**|Maneja categorías nativamente, menos necesidad de codificar.|Cuando hay muchas variables categóricas.|
|**Random Forest Regressor**|Ensamble de árboles independientes, menos tuning fino.|Para tener un baseline rápido y estable.|
|**Ridge / Lasso / ElasticNet**|Modelos lineales penalizados, interpretables.|Si sospechas de relación lineal fuerte o quieres interpretabilidad.|
|**Support Vector Regressor (SVR)**|Robusto en datasets medianos, kernels no lineales.|Con pocas muestras y features, kernel RBF.|
|**k-Nearest Neighbors**|Modelo muy simple, sin entrenamiento pesado.|Para detectar patrones locales en el espacio.|
|**Redes Neuronales (MLPRegressor)**|Modela relaciones complejas no lineales.|Si dispones de mucha data y potencia de cómputo.|
|**Gaussian Process Regressor**|Predicción probabilística y cuantifica incertidumbre.|<p>Cuando quieras intervalos de confianza en predicción.</p><p></p>|
![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.018.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.019.png)

Para determinar cuál de los modelos es mejor, es importante tener en cuenta varias métricas de evaluación que se muestran en las gráficas y la tabla. Las métricas clave para un modelo de regresión suelen ser:

1. **RMSE (Root Mean Squared Error)**: Indica la magnitud promedio de los errores en las predicciones. Cuanto más bajo sea el valor de RMSE, mejor será el modelo en cuanto a precisión.
1. **MAE (Mean Absolute Error)**: Mide el error absoluto promedio de las predicciones. Al igual que el RMSE, un valor más bajo es mejor.
1. **R² (Coeficiente de determinación)**: Mide la calidad del ajuste del modelo, es decir, cuánto de la varianza en los datos se explica por el modelo. Un valor cercano a 1 indica un buen ajuste.
1. **Tiempo de entrenamiento**: Indica cuánto tiempo tarda el modelo en entrenarse. Aunque no afecta la precisión, un tiempo de entrenamiento más bajo es generalmente preferido si no compromete el rendimiento.
1. **Tiempo de predicción**: Similar al tiempo de entrenamiento, este valor indica cuánto tarda el modelo en realizar las predicciones, siendo importante en situaciones de producción en tiempo real.






### <a name="_7q1rnfzcpc5k"></a>**Análisis de los resultados:**
1. **RMSE y MAE**:
   1. **SVR** (Support Vector Regression) tiene el mayor RMSE y MAE, lo que indica que tiene un rendimiento inferior en comparación con otros modelos.
   1. **KNN** (K-Nearest Neighbors) también muestra un rendimiento deficiente en estas métricas, especialmente en RMSE y MAE altos.
   1. **MLP** (Multi-layer Perceptron) es el mejor modelo en términos de RMSE y MAE, con los valores más bajos de ambas métricas, lo que significa que es el más preciso en la predicción.
1. **R²**:
   1. **MLP** es el modelo con el mayor R², lo que indica que es el que mejor explica la varianza en los datos y, por lo tanto, tiene el mejor ajuste entre los modelos evaluados.
   1. Modelos como **RandomForest**, **ElasticNet**, y **Ridge** también tienen un buen desempeño, con valores altos de R², aunque no superan al MLP.
1. **Tiempo de entrenamiento**:
   1. El **MLP** tiene el mayor tiempo de entrenamiento, lo que podría ser un inconveniente si el tiempo de cómputo es una preocupación.
   1. Los modelos como **KNN** y **SVR** tienen los tiempos de entrenamiento más bajos, lo que los hace más adecuados para escenarios donde la rapidez de entrenamiento es crucial.
1. **Tiempo de predicción**:
   1. **LightGBM** y **XGBoost** tienen los tiempos de predicción más rápidos, lo que puede ser beneficioso en aplicaciones donde las predicciones deben hacerse en tiempo real.
   1. **MLP** y **SVR** tienen tiempos de predicción más largos, lo que podría ser un problema en aplicaciones sensibles al tiempo.



### <a name="_58y99hj8ez7o"></a>**Conclusión:**
- **Mejor modelo**: **MLP (Multi-layer Perceptron)** es el mejor modelo en términos de precisión (bajos RMSE y MAE) y ajuste (alto R²). Sin embargo, tiene un tiempo de entrenamiento largo.
- **Modelos alternativos**:
  - Si el tiempo de entrenamiento es crucial, **KNN** y **SVR** ofrecen tiempos de entrenamiento más rápidos, aunque con un rendimiento inferior en términos de precisión.
  - **LightGBM** y **XGBoost** ofrecen un buen equilibrio entre precisión y tiempos de predicción rápidos, siendo buenos para aplicaciones en tiempo real.

En resumen, **MLP** es el modelo más preciso, pero si el tiempo de entrenamiento o de predicción es una preocupación, **LightGBM** o **XGBoost** podrían ser mejores opciones.

El **MLP (Multilayer Perceptron)** es un tipo de red neuronal compuesta por una **capa de entrada**, **una o más capas ocultas** y una **capa de salida**. Cada neurona combina entradas con pesos, aplica una función no lineal (como ReLU) y transmite la señal.El modelo aprende ajustando los pesos usando **retropropagación** y **descenso del gradiente**.Sirve para tareas de **clasificación y regresión**, capturando relaciones complejas entre variables.Es un modelo supervisado que requiere datos etiquetados para entrenar.

Una vez hemos dado con el mejor modelo, ahora solo nos queda usarlo para predecir los precios del dataset de Vinted y tendremos una aproximación del beneficio que le podemos sacar a cada uno. Como extra para la toma de decisión, hemos agregado otra predicción basada en la comparación de características usando la técnica de **similitud del coseno** entre representaciones vectoriales TF-IDF de texto. 

- Se calcula una **matriz de similitud** donde cada fila representa un producto de Vinted y cada columna un producto de Vestiaire, usa **TF-IDF** sobre el product\_name y product\_keywords para representar los textos como vectores. luego mide la **similitud del coseno** entre estos vectores para saber qué productos son “parecidos” en términos de descripción textual.

  ![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.020.png)






- Para cada producto de Vinted (idx), selecciona los **top 5 productos más similares** en Vestiaire, luego **calcula el precio medio** de esos productos y lo usa como estimación del precio para el producto de Vinted.

  ![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.021.png)



Es útil porque no requiere entrenamiento y se basa solo en texto, siendo ideal cuando los productos están bien descritos. Sirve como referencia simple e interpretable frente a modelos complejos como LightGBM o XGBoost.


![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.022.png)


En esta tabla de PowerBi podemos ver el precio del producto en Vinted, y el precio estimado que podría alcanzar en Vestiaire. Aunque vimos que el MLP era el que mejores resultados dio, da unos precios demasiado optimistas para dejarnos llevar solo por su predicción.

















**CATEGORIZACIÓN**

En el código se realizan **dos formas distintas de categorización** de inversión para los productos de Vinted, basadas en la relación entre el precio real y el precio estimado:

### <a name="_g14wmuj9noxf"></a>**1. Categorización manual por regla lógica (condicional):**
Se calcula el promedio de todas las predicciones de precio  (predicted\_price\_avg) y luego se aplica una **función de decisión** que compara ese promedio con el precio real (price\_usd):

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.023.png)





Esto evalúa cuánto más (o menos) vale el producto según los modelos comparado con su precio real:

- **Alta inversión (High Investment)**: el producto parece estar **muy infravalorado** (es una buena oportunidad).
- **Inversión moderada (Moderate Investment)**: el producto está **ligeramente infravalorado**.
- **Baja inversión (Low Investment)**: el producto está **sobrevalorado**.






### <a name="_5vlpydvn6lb0"></a>**2. Categorización automática con KMeans (clustering no supervisado):**
- Aquí se usan **todas las predicciones y el precio real** como características para aplicar KMeans, se estandariza con StandardScaler() para que todas las variables pesen igual, y luego agrupa los productos en **3 clústeres** automáticamente, según patrones en sus precios reales y estimados.

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.024.png)

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.025.png)

Finalmente, se analizan los clústeres para asignarles etiquetas:

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.026.png)

Resultado:

- investment\_category: categorización explícita por reglas.
- investment\_category\_from\_cluster: categorización descubierta por agrupamiento automático.

![](Aspose.Words.732c45bf-e78d-4b51-85d6-ac6987e91b78.027.png)


**CONCLUSIÓN**

Este proyecto demuestra cómo el machine learning puede aplicarse eficazmente al mercado de reventa de artículos de lujo, automatizando la estimación del valor de productos mediante modelos entrenados con datos reales de Vestiaire. A partir del scraping y procesamiento del contenido de Vinted —incluyendo limpieza, extracción de precios desde el título y normalización multilingüe— se construyó un dataset comparable, lo que permitió entrenar y aplicar modelos como LightGBM, XGBoost y MLP.

El modelo MLP fue el más preciso en términos de error y ajuste, mientras que LightGBM y XGBoost ofrecieron un rendimiento más equilibrado y tiempos de predicción rápidos. Además, se implementó un sistema de estimación por similitud semántica (TF-IDF + coseno) entre productos de ambas plataformas, útil como referencia adicional sin necesidad de entrenamiento.

Finalmente, se categorizaron los productos según su potencial de inversión utilizando dos enfoques: uno lógico basado en reglas y otro automático mediante clustering (KMeans), ofreciendo así una herramienta de apoyo a la decisión robusta, práctica y aplicable al análisis real de oportunidades de reventa.







