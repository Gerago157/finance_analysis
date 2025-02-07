# Proyecto de Herramienta de Análisis Financiero

Este proyecto fue desarrollado para realizar análisis bursátiles desde varios puntos de vista. 

[App de Análisis Financiero](https://finance-analy3-app.streamlit.app/)

## Análisis de Activo

En la sección **"Análisis de Activo"**, se tienen en cuenta aspectos relacionados únicamente con el activo seleccionado.

La aplicación está integrada con la API de Yahoo Finance, lo que permite obtener los datos que el usuario ingresa a través de los siguientes inputs:

- **Fecha de inicio del análisis**
- **Fecha de fin del análisis**
- **Activo** (el activo financiero que se desea analizar)
- **Mercado de referencia** (contra el cual se desea comparar el activo seleccionado)

### Inputs

![inputs](https://i.imgur.com/jsGqmKG.png)

Una vez completados todos los inputs, se obtiene un resumen de la tabla con los valores recogidos de la API. Se resalta la columna principal, que contiene los valores necesarios para realizar los cálculos estadísticos sobre los retornos diarios, calculando su variación diaria, y desde allí obtenemos el resumen estadístico.

### Resumen Estadístico

![captura de la tabla y resumen estadístico](https://i.imgur.com/KcIIIIX.png)

### Comportamiento de los Retornos Diarios

Si continuamos, podemos observar el comportamiento de esos retornos diarios:

![captura](https://i.imgur.com/bTawnlw.png)

### Gráficos de la Acción y Mercado de Referencia

A continuación, se muestran los gráficos correspondientes a la acción en cuestión y al mercado de referencia. El uso de **Altair** nos proporciona una gran flexibilidad en cuanto a interactividad.

![gráficos de velas](https://i.imgur.com/LpqIhDY.png)

### Comparativa Normalizada

Al normalizar los valores de la acción y el mercado de referencia, obtenemos un gráfico donde se superponen ambos elementos. Esto nos permite una visualización clara de la comparación entre ellos y su comportamiento.

![gráfico comparativo](https://i.imgur.com/LlnDymZ.png)

### Conceptos Claves

Junto al retorno acumulado del activo, tenemos presentes los siguientes conceptos claves, que nos permiten obtener información adicional para la toma de decisiones de inversión:

- **Alpha**: Es una medida del rendimiento de una inversión en relación con un índice de referencia, ajustada por riesgo. Un alpha positivo indica que la inversión ha superado su índice de referencia, mientras que un alpha negativo sugiere que ha tenido un rendimiento inferior. Se utiliza para evaluar la habilidad de un gestor de fondos o estrategia de inversión.
  
- **Beta**: Es una medida de la volatilidad de un activo en comparación con el mercado en general. Un beta de 1 indica que el activo se mueve en línea con el mercado, un beta mayor a 1 indica mayor volatilidad (más riesgo), y un beta menor a 1 sugiere menor volatilidad (menos riesgo). Es útil para entender el riesgo sistemático de una inversión.
  
- **R Cuadrado**: Es una estadística que indica la proporción de la variabilidad en el rendimiento de un activo que se puede explicar por el movimiento de su índice de referencia. Varía entre 0 y 1; un R² cercano a 1 significa que el rendimiento del activo está altamente correlacionado con el índice, mientras que un R² cercano a 0 indica poca o ninguna relación. Se utiliza para evaluar la efectividad de un modelo de regresión en la predicción del rendimiento.

### Predicción de Movimiento Futuro

En el módulo de **predicción**, mediante el uso de un modelo **LSTM (Long Short-Term Memory)**, se podrá predecir el posible movimiento futuro de ese activo durante los próximos 15 días.

![captura de predicción](https://i.imgur.com/23QtCrK.png)

![15 días posteriores](https://i.imgur.com/UYid4JT.png)

---

## Análisis de Cartera

En esta sección, no hay límites en la elección de las acciones que deben componer la cartera. El análisis se realiza sobre la cartera en su totalidad.

Se analizan los retornos diarios de la cartera, al mismo tiempo que se visualiza el gráfico de la distribución de cada activo, que representa su respectiva porción dentro de la cartera. Además, se analiza la correlación entre las acciones para determinar cuán diversificada está la composición de la cartera.

![gráfico de las 4 cosas](ruta/a/la/imagen.png)

### Evolución de la Cartera

Se analiza el comportamiento de los retornos diarios de la cartera y los beneficios acumulados a lo largo del período de tiempo seleccionado.

![distribución + gráfico de evolución](ruta/a/la/imagen.png)

### Cálculo del Sharpe Ratio

**Sharpe Ratio**: (Explicación del concepto)

### Simulación Monte Carlo

Mediante la **Simulación de Monte Carlo**, se analiza cuál es la mejor distribución de los activos dentro de la cartera, considerando diferentes combinaciones de pesos para cada uno de los activos seleccionados. De esta manera, se determina cuál sería el peso ideal de cada uno de ellos en la cartera.

---

## Requisitos

- Python 3.x
- Librerías necesarias (a instalar desde el archivo `requirements.txt`)

## Instalación

1. Clonar el repositorio:
    ```bash
    git clone https://github.com/lalausuario/analisis-financiero.git
    ```

2. Instalar las dependencias:
    ```bash
    pip install -r requirements.txt
    ```

## Uso

Para ejecutar la aplicación, simplemente utiliza el siguiente comando:

```bash
python main.py
