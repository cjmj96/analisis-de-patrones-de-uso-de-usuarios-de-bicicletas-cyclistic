# Análisis de patrones de uso de usuarios de bicicletas en Cyclistic

## Antecedentes y visión general

En 2016, Cyclistic lanzó una exitosa oferta de bicicletas compartidas. Desde entonces, el 
programa ha crecido hasta contar con una flota de 5,824 bicicletas que están geo
 localizadas y bloqueadas en una red de 692 estaciones en Chicago. Las bicicletas
 se pueden desbloquear en una estación y devolver a cualquier otra estación del sistema en cualquier momento.

Hasta ahora, la estrategia de marketing de Cyclistic se ha basado en generar 
conciencia general y atraer a amplios segmentos de consumidores. Un enfoque
 que ayudó a hacer posibles estas cosas fue la flexibilidad de sus planes de precios: pases
 de un solo viaje, pases de un día completo y membresías anuales. Los clientes que
 compran pases de viaje sencillo o de todo el día se denominan **casuales**. Los clientes
 que compran membresías anuales son conocidos **miembros**.

Los analistas financieros de Cyclistic han concluido que los miembros anuales
 son mucho más rentables que los ciclistas ocasionales. Aunque la flexibilidad
 en los precios ayuda a Cyclistic a atraer más clientes, la directora de
 mercadotecnia cree que maximizar el número de miembros anuales
 será clave para el crecimiento futuro. En lugar de crear una campaña
 de marketing que apunte a nuevos clientes, se cree que hay una 
muy buena oportunidad de convertir a los usuarios casuales en miembros. Ella
 señala que los usuarios casuales ya están al tanto del programa Cyclistic y han
 elegido Cyclistic para sus necesidades de movilidad.

Este proyecto analiza los datos históricos de viajes en bicicleta de Cyclistic para
diseñar estrategias de mercadotecnia destinadas a convertir a los 
ciclistas ocasionales en miembros anuales.

El conjunto de datos utilizado es de una compañía real llamada [Divvy](https://divvybikes.com/). Aquí
se encuentran los [datos](https://divvybikes.com/system-data).

Los descubrimientos y recomendaciones son proporcionadas en las siguientes áreas claves:

- Análisis comparativo temporal: Analiza y descubre patrones en diferentes granularidades temporales.

- Análisis del comportamiento: Analiza los patrones de uso de los usuarios de Cyclistic.

## Estructura de datos y revisiones iniciales

Cyclistic tiene datos del segundo trimestre de 2024, conteniendo 1,735,239 observaciones, cada una
representa un viaje. Los datos proporcionados estan anonimizados, entonces no es posible determinar cuantos usuarios
realizaron esa cantidad de viajes en el período de tiempo usado. El conjunto de datos tiene 13 columnas que recoge
información de cada viaje realizado. Aquí se muestra el propósito de cada columna:

| Columna            | Propósito                                                                 |
|---------------------|---------------------------------------------------------------------------|
| ride_id             | Número que identifica de manera única un viaje                            |
| rideable_type       | Tipo de bicicleta utilizada. Puede ser clásico, eléctrico o parqueado     |
| started_at          | Fecha de inicio de un viaje                                               |
| ended_at            | Fecha de finalización de un viaje                                         |
| start_station_name  | Nombre de la estación de inicio de un viaje                               |
| start_station_id    | Número que identifica de manera única una estación                        |
| end_station_name    | Nombre de la estación final de un viaje                                   |
| end_station_id      | Número que identifica de manera única una estación                        |
| start_lat           | Latitud registrada al inicio de un viaje                                  |
| start_lng           | Longitud registrada al inicio de un viaje                                 |
| end_lat             | Latitud registrada al final de un viaje                                   |
| end_lng             | Longitud registrada al final de un viaje                                  |
| member_casual       | Tipo de membresía del usuario que realizó el viaje                        |

El informe detallado se puede encontrar en [Kaggle](https://www.kaggle.com/code/christianmontenegro/caso-de-estudio-de-cyclistic).
El modelo de proceso de estándar abierto usado es [CRISP-DM](https://www.datascience-pm.com/crisp-dm-2/).


## Resumen ejecutivo

### Visión general de descubrimientos

Los usuarios presentan diferentes patrones al usar Cyclistic. Los usuarios casuales realizaron una menor cantidad de
 viajes, de mayor duración y distancia al inspeccionarlo en diferentes granularidades. Estos viajes son realizados
 en rutas cerca del lago Michigan que incluyen parques naturales y otros lugares de entretenimiento. Los usuarios
 anuales hacen lo contrario. Realizan viajes en rutas que abarcan múltiples tipos de negocios, propiedades residenciales,
 condominios, o complejos residenciales. El uso máximo del servicio se da a las 8:00 a.m. y 5:00 p.m (usuarios anuales)
 y entre las 1:00 p.m. y 4:00 p.m. (usuarios casuales).  Ambos prefieren más el uso de bicicletas clásicas sobre eléctricas.