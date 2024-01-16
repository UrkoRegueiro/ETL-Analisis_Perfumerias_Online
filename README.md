# ETL & Analisis - Perfumerías Online Españolas

<div align="center">

  <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTzDnhOC-bhAsq7O2sPGpRGBGwy7EdFVr8Few&usqp=CAU" width="40%">
  
</div>

## Tecnologías usadas

**Lenguaje:** Python.

**Librerias:** numpy, pandas, matplotlib, seaborn, plotly, requests, BeautifulSoup

------------

<h2>
  
Para visualizar la versión detallada del presente proyecto véase el notebook ["analysis"](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/analysis.ipynb)

<h2>
  
------------

## 1. **Introducción**


Se ha llevado a cabo un estudio de las principales perfumerías online españolas con el objetivo de responder a las siguientes preguntas de interés:

- Precisar la orientación de mercado.
- Detectar las marcas y productos más populares entre los consumidores.
- Esclarecer las principales diferencias de precios y descuentos, tanto de marcas como de productos populares entre las tiendas.
- Determinar las tiendas con una mayor actividad de valoración.
- Explorar si existen correlaciones en precios, descuentos y valoraciones de las marcas TOP 5.

Nos hemos centrado en las siete perfumerias online con mayor número de visitas al mes, siendo estas, de mayor a menor número de visitas, las siguientes:
- [*Druni*](https://www.druni.es/), con *2.300.000* visitas al mes.
- [*Primor*](https://www.primor.eu/es_es/), con *1.994.000* visitas al mes.
- [*Douglas*](https://www.douglas.es/es), con *735.000* visitas al mes.
- [*Notino*](https://www.notino.es/), con *447.000* visitas al mes.
- [*Paco Perfumerías*](https://www.pacoperfumerias.com/), con *242.500* visitas al mes.
- [*Perfumes 24 horas*](https://perfumes24h.com/), con *198.000* visitas al mes.
- [*Perfumeria.com*](https://perfumeria.com/), con *178.000* visitas al mes.

Mediante el scrapeo web, utilizando las librerías Beautiful Soup y Selenium, se han recabado los siguientes datos para cada una de las tiendas online:
- <ins>Categoría</ins>: Se presentan en dos, para hombre y para mujer.
- <ins>Marca</ins>: Se recoge cada una de las marcas vendidas por cada tienda.
- <ins>Nombre</ins>: El nombre de cada producto en la página web.
- <ins>Tipo</ins>: Se han analizado los principales tipos de productos vendidos, tales como: eau de cologne, eau de toilette, eau de parfum y parfum.
- <ins>Precios</ins>: Se toman los precios con o sin descuento de cada producto, así como su porcentaje de descuento.
- <ins>Valoración</ins>: Puntuación media del 0 al 5 que recibe un producto en base al número de valoraciones.
- <ins>Número de valoraciones</ins>: Cantidad de valoraciones de un producto por los clientes.

<h2>
  
 En la carpeta ["scrapers"](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/tree/main/ETL%26Analysis_Online_Perfumeries/scrapers) puede visualizarse el código y todo el proceso de extracción de datos realizado.

<h2>

Pasemos a continuación a analizar los datos obtenidos.

## 2. **Análisis por categoría**

### 2.1. **Distribución de la cantidad de productos para hombres y mujeres, en total y por tienda**

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_1_cat.png)

</div>

Se observa claramente como la <ins>**orientación de mercado**</ins> se dirige hacia el <ins>**público femenino**</ins>, teniendo una mayor cantidad de productos.

### 2.2. **Estudio del precio medio por tipo de producto en cada una de las categorías.**

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_2_cat.png)

</div>

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_2_cat_desc.png)

</div>


Se descubre como el <ins>**precio medio**</ins>, tanto con descuento como sin descuento, es <ins>**mayor para el género masculino**</ins>. Esto puede deberse a un menor número de compras por parte del público masculino.

### 2.3. **Evaluación del descuento promedio en los productos por categoría.**

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_3_cat.png)

</div>

El resultado nos muestra que <ins>**no hay una diferencia significativa**</ins> de descuento entre categorías, siendo el mayor descuento promedio para la categoría mujer.

### 2.4. **Determinación de las marcas TOP 5 más valorados en cada categoría.**

Se han considerado las 5 marcas con mayor número de valoraciones y se ha representado con gradiente de color la puntuación media de la marca.

- Para el <ins>**público masculino**</ins> las marcas más valoradas son las siquientes:

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_4_cat_masc.png)

</div>

- Para el <ins>**público femenino**</ins> las marcas más valoradas son las siquientes:

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_4_cat_fem.png)

</div>

### 2.5. **Determinación del TOP 3 de productos más valorados en cada categoría.**

- Para el <ins>**público masculino**</ins> las marcas más valoradas son las siquientes:

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_5_cat_masc.png)

</div>

- Para el <ins>**público femenino**</ins> las marcas más valoradas son las siquientes:

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/2_5_cat_fem.png)

</div>

## 3. **Análisis por tienda.**

### 3.1. **Estudio de los precios en cada una de las tiendas.**

En esta subsección se han tomado los precios sin descuento para hacer una comparación objetiva del precio de los productos por tienda.

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/3_1_tienda.png)

</div>

Se observa que, para productos de mujer, los menores precios se presentan en la tienda de Notino, mientras que para hombre en Primor. Destacar que para ambos casos la tienda con mayores precios es Druni, con una diferencia aproximada con respecto a las más baratas de 25€.

Analicemos a continuación la diferencia de precios por tipo de producto en cada tienda:

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/3_1_tienda_prod.png)

</div>

De aquí podemos extraer la siguiente **<ins>información acerca del precio por tipo de producto en cada tienda**</ins>:

Para la **<ins>categoría Hombre**</ins>:
- Eau de cologne: El precio más asequible lo encontramos en la tienda Notino, siendo de 31€ .
- Eau de toilette: El menor precio se encuentra en la tienda Notino, siendo este de 32€.
- Eau de parfum: El precio más bajo se encuentra en la tienda Notino, siendo de 67€.
- Parfum: El menor precio se encuentra en la tienda Perfumeria.com, siendo de 88€.<br>

Para la **<ins>categoría Mujer**</ins>:
- Eau de cologne: El precio más asequible lo encontramos en las tiendas Perfumes24h y Perfumeria.com, siendo de 33€.
- Eau de toilette: El menor precio se encuentra en las tiendas Perfumes24h y Perfumeria.com, siendo este de 50€.
- Eau de parfum: El precio más bajo se encuentra en la tienda Notino, siendo de 42€.
- Parfum: El menor precio se encuentra en la tienda Perfumeria.com, siendo de 75€.

Concluimos que en la tienda **<ins>Notino**</ins> por lo general el **<ins>precio**</ins> por tipo de producto en la **<ins>categoría hombre**</ins> es el **<ins>menor**</ins>. Sin embargo, para la **<ins>categoría mujer**</ins>, el **<ins>menor precio**</ins> lo encontramos en la tienda **<ins>Perfumeria.com**</ins>.

### 3.2. **Determinación de la distribución de descuentos en la cantidad de productos para cada tienda.**

En esta subsección visualizamos la distribución de los descuentos(mayores a 0%) aplicados en cada tienda, comparando su disposión.

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/3_2_tienda.png)

</div>

### 3.3. **Análisis del número de valoraciones totales para cada tienda.**

Se analiza en que tiendas los clientes tienden a valorar más y en que tipo de producto.

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/3_3_tienda.png)

</div>

Con gran diferencia **<ins>las dos tiendas con mayor número de valoraciones son Druni y Douglas**</ins>. Cabe destacar como factor común entre las tiendas que **<ins>los tipos con mayor número de valoraciones son: Eau de toilette y Eau de perfum**</ins>, pudiendo concluir que estos parecen ser los productos más demandados.

### 3.4. **Estudio de posibles correlaciones en el precio, descuento y valoraciones en las marcas TOP 5.**

<div align="center">

![](https://github.com/UrkoRegueiro/HACK-A-BOSS-PROJECTS/blob/main/ETL%26Analysis_Online_Perfumeries/images/3_4_tienda.png)

</div>

Tras visualizar el gráfico podemos observar:<br>
<ol>
  <li>Existe una leve correlación negativa entre la valoración y el descuento. Esto se traduce en que una mayor valoración disminuye el descuento.</li>
  <li>Observamos una pequeña correlación positiva entre el precio con descuento y la valoración, es decir, parece que se valora con mayor puntuación si el precio es con descuento.</li>
</ol>

Obviamente estas son observaciones cualitativas ya que no se puede suponer, con los datos obtenidos, tal relación entre estas variables.

## 4. **Conclusiones.**

Tras la información recabada podemos destacar lo que sigue:

- La **<ins>orientación de mercado**</ins> se dirije hacia el **<ins>público femenino**</ins>.
  
- El **<ins>precio promedio**</ins> de los productos es **<ins>mayor**</ins> para la **<ins>categoría hombre**</ins>.
  
- **<ins>No hay diferencias apreciables en descuentos**</ins> por categoría.
  
- Las **<ins>tres marcas con mayor número de valoraciones**</ins>, de mayor a menor, son **<ins>las mismas en ambas categorías**</ins>, siendo estas:<br>

  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. Armani
  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. Yves Saint Laurent
  
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;3. Calvin Klein

- La **<ins>marca**</ins> con **<ins>mayor valoración**</ins> en la **<ins>categoría hombre**</ins> es **<ins>Hugo Boss**</ins>.

- La **<ins>marca**</ins> con **<ins>mayor valoración**</ins> en la **<ins>categoría mujer**</ins> es **<ins>Lancome**</ins>.
  
- La **<ins>categoría mujer**</ins> tiende a realizar **<ins>más valoraciones en los productos**</ins>.
  
- La **<ins>tienda con mayores descuentos para las marcas TOP es Primor**</ins> en ambas categorías.
  
- Las **<ins>tiendas con más cantidad de valoraciones**</ins> son **<ins>Druni**</ins>, **<ins>Douglas**</ins> y **<ins>Primor**</ins>.
  
- La **<ins>tienda con menores precios**</ins> , sin descuento por tipo, es **<ins>Notino**</ins> para la **<ins>categoría hombre**</ins> y **<ins>Perfumeria.com**</ins> para la **<ins>categoría mujer**</ins>.
  
- **<ins>No se encuentra una clara correlación entre precios, descuentos y valoraciones de las marcas TOP 5.**</ins>
