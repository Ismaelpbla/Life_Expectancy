
# Analysis of Life Expectancy

A lo largo de este proyecto de analisis de datos vamos a intentar ver la relación existente entre 
el producto Interior Bruto (GDP) y la esperanza de vida de 6 paises (Chile, Alemania, USA, Mexico, China y Zimbabwe) desde el año 2000 a 2015


## Authors

- [@Ismaelpbla](https://github.com/Ismaelpbla)


## DATA

En este proyecto vamos a analizar la esperanza de vida en diferentes paises.
Para ello vamos a utilizar el archivo csv que se nos ha proporcionado 
en Codecademy: all_data.csv.

En un primer vistazo a los 5 primeros datos vemos lo siguiente:

|  Country |Year   |Life Expectancy at birth (years)   |GDP   |
|---|---|---|---|
|   Chile|   2000|   77.3|   7.786093e+10|
|   Chile|   2001|   77.3|   7.097992e+10|
|   Chile|   2002|   77.8|   6.973681e+10|
|   Chile|   2003|   77.9|   7.564346e+10|
|   Chile|   2004|   78.0|   9.921039e+10|

Si observamos los últimos 3 datos observamos algo distinto:

|   Country|   Year|Life Expectancy at birth (years)    |GDP   |
|---|---|---|---|
|   Zimbabwe|   2013|   58.0|   1.545177e+10|
|   Zimbabwe|   2014|   59.2|   1.589105e+10|
|   Zimbabwe|   2015|   60.7|   1.630467e+10|

De estos vistazos podemos deducir que el Dataframe esta compuesta de 4 variables.
Dos de ellas son varaibles cuantitativas (Life Expectancy at birth (years) y GDP), 
mientras que las otras dos ('Country' y 'Year') son variables cualitativas que además
estan organizadas alfabeticamente y numericamente de mayor a menor respectivamente.

En este Dataframe manejamos 96 datos, con lo cual no es necesario aplicar SQL, ya que este cantidad
es muy manejable.

Los dtypes de cada una de las variables son coherentes con respecto al tipo de variables que son: year tiene int64, Country es Object y Life expectancy at birth (years)
y GDP son float64.

Si observamos los valores maximos y minimos vemos:

- Que el año mas reciente es el año 2015 y el mas antiguo 2000
- Que la variable de la esperanza de vida es de minimo 41 años y maximo 81
- Que el valor minimo del GDP de todos los paises es de aproximadamente 4000  millones y el maximo valor es de 18 trillion 100 million

La media de las variables cuantitativas son:
- 72.8 años en cuanto a la esperanza de vida de todos los paises con una desviación estandar de 10.67
- 3.880 trillones en cuanto al GDP habiendo una desviación estandar de 5.2 trillones

Al ver que existe mucha diferencia entre el minimo, la media y el valor maximo
en el caso de la variable GDP, calculamos el coeficiente de variación, observando que:
- La variable de esperanza de vida tiene un coeficiente de variación cercano a 0
de tal forma que existe poca variabilidad.
- La variable GDP presenta, por el contrario, un coeficiente de variación cercano a 1
existiendo, entonces, mucha variabilidad.



## LIMPIEZA DE DATOS

En el primer vistazo que hemos echado al Dataframe parece que los datos
estan bastante limpios. No obstante vamos a comprobar unas cuantas cosas:
1) Si existen Missing Data
2) Si existen duplicados
3) Check inconsistent data (Capitalization, Formats, and sintax errors)

Mediante el metodo del heatmap, observamos que no hay missing data en todo el Dataframe.

Comprobamos que en todo el dataframe no existen duplicados mediante el metodo duplicated()

No hay inconsistent data, pero el nombre de la variable "Life expectancy at birth (years)"
es demasiado largo y nos dara problemas en eñ futuro. Por ello vamos a cambiarla mediante el metodo rename() a
'Life_exp'.

Tambien se modificó el nombre de "United States of America" por "USA", por las mismas razones.
Esta vez se usó el metodo .replace().


## DATA ANALYSIS

En este dataframe podemos hacer una comparación bastante evidente, y es ¿Como ha variado la
esperanza de vida desde el año 2000 hasta el año 2015 en los 6 paises del dataframe?.

Primero debemos extraer del dataframe 6 tablas con los 6 paises distintos.

Posteriormente haremos una figura en la que proyectaremos, para cada país,
la esperanza de vida vs la variable Year, para poder ver como ha variado la esperanza de vida en 15 años, desde el año 2000 al 2015.

No obstante como ha variado la esperanza de vida no nos dice demasiado. Podemos observar como hay
algunos paises como Chile o Mexico que tienen momentos en los que su esperanza de vida disminuye rapidamente, para luego volver a subir.
Y paises como China, USA o Alemania cuyo aumento de la esperanza de vida es gradual con el tiempo.

Zimbabwe es el único que presenta una evolución de su esperanza de vida muy particular y diferente al resto.
Se puede observar como la esperanza de vida disminuye muchisimo desde el año 2000 al 2004 y desde ahí vuelve a crecer casi de forma exponencial.

Aunque analizar la evolución de la esperanza de vida es interesante, en nuestra base de datos
tenemos otra variable que es el Producto Interior Bruto (GDP) de cada país. ¿Existirá alguna relación entre la esperanza de vida y el GDP de cada país?

Vamos a proyectar en la misma gráfica que la esperanza de vida, el GDP de cada país. Para ello utilizaremos el metodo twinx().

![set image](https://raw.githubusercontent.com/Ismaelpbla/Life_Expectancy/7df87fe0179e0187b5930034a50f26deac9d6b81/Figures/Lineplot.png)
#### Figura 1

Al ver los dos lineplots, vemos como existe una clara relación entre estas dos variables, que puede apreciarse en todos los paises:

# CONCLUSIONS

Las relaciones que pueden observarse entre Esperanza de vida y GDP en cada país son las siguientes:

a) En Chile puede apreciarse como ambas curvas discurren paralelas hasta 2010 en el que se produce
un descenso de la esperanza de vida, esto puede deverse a una disminución de la tasa de natalidad al existir un periodo de 
recesión económica durante 2008 tal y como se puede apreciar en la curva de GDP.

b) En Alemania se puede apreciar muy bien las crisis económica de 2008 y 2012 y sus correspondientes
recuperaciones en 2010 y 2014. Ambos periodos de recuperación económica se asocian con aumentos en la esperanza de vida.

c) Estados Unidos presenta una coincidencia casi perfecta entre GDP y Esperanza de vida. Viendose una mayor separación entre ambas curvas
en la crisis económica global de 2008. El aumento de la esperanza de vida se realentizó dos años mas tarde, probablemente debido a esa crisis de 2008.

d) Mexico presenta el mayor descenso del GDP de entre todos los paises de este análisis, tambien durante el 2008. Algo que afectó considerablemente
a su esperanza de vida. Resulto curioso el aumento de la esperanza de vida que hubo justo en el momento de menor GDP del país.

e) China presenta una distribución simétrica entre esperanza de vida y GDP. Mientras el GDP aumenta de forma exponencial desde el año 2000,
la esperanza de vida tiende a estabilizarse en los 76 años.

f) Finalmente en Zimbabwe tambien se puede observar como la crisis de 2008 afectó a su ya dañada economía. Pero la esperanza de vida
siguió creciendo exponencialmente desde el año 2004 independientemente de este periodo de crisis. 
Cabe destacar la coincidencia del aumento de esperanza de vida y del GDP, en este país, entre los años 208 y 2011.

En lineas generales, en todos los paises puede observarse:

1. Que las crisis económica y la perdida de riqueza de los paises, afecta, unos años después,  a la esperanza de vida de estos.
2. Que las recuperaciones económicas implican exactamente lo contrario, es decir a mayor riqueza, mayor esperanza de vida.
3. Que estas dos últimas conclusiones no es algo aplicable a todos los paises, existen excepciones como China o Zimbabwe donde no se ven los efectos
del aumento (en el caso de China) o de la perdida (caso de Zimbabwe) de riqueza en la esperanza de vida.

