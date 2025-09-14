# Portafolio de Análisis de datos 

Este repositorio contiene una colección de proyectos análisis de datos completado por Alan Galván. Cada proyecto contiene en su directorio un los datasets, código analítico y un resumen detallado de los hallazgos.

---

## Proyectos

Below is a summary of the projects you can find here. For a complete breakdown of any project, please click the link to navigate to its folder and view its dedicated `README.md`.
Aquí debajo estan los proyectos que econtrarás en este repositorio. Para 

# Análisis de Rentabilidad de Planes Móviles para Megaline

## Resumen del Proyecto

Este proyecto analiza el comportamiento de 500 clientes de la operadora de telecomunicaciones Megaline para determinar cuál de sus dos tarifas de prepago, **Surf** o **Ultimate**, genera más ingresos. El análisis incluye la limpieza y preparación de los datos, el cálculo del consumo mensual por usuario y la aplicación de pruebas de hipótesis estadísticas para comparar la rentabilidad de los planes.

---

## 🎯 Planteamiento del Problema

El departamento comercial de Megaline necesita ajustar su presupuesto de publicidad, pero para ello requiere saber cuál de los dos planes actuales es más rentable. Las preguntas clave a responder son:
* ¿El ingreso promedio generado por los usuarios del plan "Ultimate" es diferente al de los del plan "Surf"?
* ¿El ingreso promedio de los usuarios en la región de "NY-NJ" es diferente al de los usuarios de otras regiones?

---

## 📊 Datos

Se utilizaron cinco conjuntos de datos en formato CSV que contienen información de 500 clientes durante el año 2018:
* `megaline_plans.csv`: Detalles y condiciones de las tarifas Surf y Ultimate.
* `megaline_users.csv`: Datos demográficos de los usuarios (quiénes son, de dónde, qué tarifa usan).
* `megaline_calls.csv`: Registro de llamadas realizadas.
* `megaline_internet.csv`: Registro de sesiones de internet.
* `megaline_messages.csv`: Registro de mensajes de texto enviados.

---

## 🛠️ Metodología

El análisis se estructuró en los siguientes pasos:

1.  **Carga y Preparación de Datos:** Se convirtieron las columnas de fechas a formato `datetime`, se redondearon los minutos de llamada y los gigabytes de internet consumidos según las reglas de negocio, y se enriquecieron los datos creando columnas adicionales como el estado del plan (`status`).
2.  **Agregación de Datos Mensuales:** Se calculó el consumo total de llamadas, minutos, mensajes y GB de internet para cada usuario en cada mes.
3.  **Cálculo de Ingresos Mensuales:** Se implementó una función para calcular el ingreso mensual por usuario, considerando los límites de cada plan y aplicando los costos correspondientes por consumo excedente.
4.  **Análisis Exploratorio (EDA):** Se utilizaron estadísticas descriptivas, histogramas y diagramas de caja para visualizar y comparar el comportamiento de consumo de los usuarios en cada plan.
5.  **Pruebas de Hipótesis (T-test):** Se realizaron pruebas estadísticas para determinar si las diferencias en los ingresos promedio entre los planes y entre las regiones eran estadísticamente significativas.

---

## 📈 Resultados y Hallazgos Clave

* **El plan Ultimate es más rentable:** La prueba de hipótesis confirmó con significancia estadística que **el ingreso promedio de los usuarios del plan Ultimate es mayor** que el de los usuarios del plan Surf.
* **El sobrecosto es clave en el plan Surf:** Aunque el plan Surf tiene una tarifa base más baja, una parte importante de sus ingresos proviene de los **costos por exceder el límite de datos** de internet.
* **La región no es un factor determinante:** La prueba de hipótesis demostró que **no hay una diferencia estadísticamente significativa** entre los ingresos generados en la región de NY-NJ y el resto del país.

---

## 💡 Visualización Destacada


![Ingresos Promedio Mensuales]

<img width="540" height="495" alt="Screenshot from 2025-09-14 09-25-23" src="https://github.com/user-attachments/assets/5cd93fa5-3f48-4fb3-a51c-6a325c72d425" />

*Este gráfico muestra cómo el ingreso promedio del plan Ultimate es consistentemente más alto y estable, mientras que el del plan Surf, aunque menor, tiende a aumentar a lo largo del año debido a los sobrecostos.*

---

## 🚀 Cómo Usar este Repositorio

Para replicar este análisis, sigue estos pasos:

1.  Clona el repositorio: `git clone https://github.com/Ghet-stress/Python_Notebooks.git`
2.  Navega al directorio del proyecto: `cd mobile_phone_data_analysis`
3.  Instala las dependencias: `pip install -r requirements.txt`
4.  Abre y ejecuta el Jupyter Notebook: `jupyter notebook Megaline.ipynb`

---

## 💻 Herramientas y Bibliotecas

* **Python 3**
* **Pandas:** Para manipulación y análisis de datos.
* **NumPy:** Para operaciones numéricas.
* **Matplotlib / Seaborn:** Para visualización de datos.
* **SciPy.Stats:** Para las pruebas de hipótesis.

---

# Análisis de Ventas Históricas de Videojuegos

## Resumen del Proyecto

Este proyecto es un análisis de datos históricos sobre las ventas de videojuegos de la tienda online "Ice". El objetivo es identificar patrones y tendencias clave que determinen el éxito comercial de un juego, con el fin de planificar la campaña publicitaria para el próximo año (2017) y enfocar las inversiones en los productos con mayor potencial.

---

## 🎯 Planteamiento del Problema

La tienda online "Ice" necesita tomar decisiones estratégicas basadas en datos para su campaña de 2017. Para ello, es fundamental responder a las siguientes preguntas:
* ¿Qué plataformas y géneros de videojuegos son los más rentables históricamente?
* ¿Cómo influyen las reseñas de la crítica y de los usuarios en las ventas de un juego?
* ¿Existen diferencias significativas en las preferencias de los principales mercados (Norteamérica, Europa y Japón)?
* ¿Las calificaciones promedio de los usuarios son iguales para las plataformas Xbox One y PC?
* ¿Las calificaciones promedio son las mismas para los géneros de Acción y Deportes?

---

## 📊 Datos

El análisis se basa en un único conjunto de datos (`games.csv`) que contiene información histórica de ventas de videojuegos. Las columnas clave incluyen:
* **Plataforma:** La consola en la que se publicó el juego (ej. PS4, XOne, WiiU).
* **Año de lanzamiento:** El año de publicación del juego.
* **Género:** La categoría del videojuego (ej. Acción, Deportes, RPG).
* **Ventas regionales:** Ventas en millones de dólares para Norteamérica, Europa y Japón.
* **Puntuaciones:** Calificaciones de la crítica profesional (`critic_score`) y de los usuarios (`user_score`).
* **Clasificación ESRB:** El sistema de clasificación por edades (`rating`).

---

## 🛠️ Metodología

El proyecto se desarrolló a través de los siguientes pasos:

1.  **Preparación de Datos:** Se realizó una limpieza exhaustiva de los datos, incluyendo la corrección de nombres de columnas, el manejo de valores nulos, la conversión de tipos de datos (ej. `user_score` de objeto a numérico) y la estandarización de las clasificaciones ESRB para una mejor interpretación.
2.  **Análisis Exploratorio de Datos (EDA):**
    * Se analizó el ciclo de vida de las plataformas para identificar su longevidad promedio y determinar un periodo de tiempo relevante para el análisis (2005 en adelante).
    * Se identificaron las plataformas y géneros más populares y rentables por cada región (NA, EU, JP), destacando las diferencias en las preferencias de cada mercado.
    * Se estudió la correlación entre las puntuaciones de críticos/usuarios y las ventas totales para medir su impacto.
3.  **Pruebas de Hipótesis (T-test):**
    * Se compararon estadísticamente las calificaciones promedio de los usuarios entre las plataformas Xbox One y PC.
    * Se compararon estadísticamente las calificaciones promedio entre los géneros de Acción y Deportes.

---

## 📈 Resultados y Hallazgos Clave

* **Ciclo de vida de las plataformas:** Las consolas tienen un ciclo de vida comercial de aproximadamente 8-10 años. Para 2017, **PS4 y Xbox One** se perfilan como las plataformas con mayor potencial de crecimiento.
* **Preferencias regionales marcadas:** **Norteamérica y Europa** muestran una clara preferencia por géneros como Acción, Disparos y Deportes en consolas de sobremesa (PS4, Xbox One). En cambio, **Japón** tiene una fuerte inclinación por los juegos de **Rol (RPG)** y las consolas portátiles como la 3DS.
* **Impacto de las reseñas:** La **puntuación de la crítica profesional** muestra una correlación moderada con el éxito en ventas. Sin embargo, la **puntuación de los usuarios** no parece ser un factor determinante en el éxito comercial de un juego.
* **Diferencias de calificación:** No se encontró una diferencia estadísticamente significativa entre las calificaciones de los usuarios para los géneros de Acción y Deportes. Sin embargo, sí se observó una diferencia significativa entre las calificaciones de las plataformas Xbox One y PC.

---

## 🚀 Cómo Usar este Repositorio

Para replicar este análisis, sigue estos pasos:

1.  Clona el repositorio: `git clone https://github.com/Ghet-stress/Python_Notebooks.git`
2.  Navega al directorio del proyecto: `cd online_game_store`
3.  Instala las dependencias: `pip install -r requirements.txt`
4.  Abre y ejecuta el Jupyter Notebook: `Online_store_ice.ipynb`

---

## 💻 Herramientas y Bibliotecas

* **Python 3**
* **Pandas & NumPy:** Para manipulación y análisis de datos.
* **Matplotlib & Seaborn:** Para visualización de datos.
* **SciPy.Stats:** Para las pruebas de hipótesis.
