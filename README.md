# Riesgo Cuantitativo: Value at Risk (VaR) mediante Simulación Montecarlo

## Descripción del Proyecto
Este proyecto implementa un modelo cuantitativo para evaluar el riesgo de mercado de un portafolio de inversión. Utilizando el método de **Simulación de Montecarlo**, el modelo proyecta miles de trayectorias posibles para los activos financieros, lo que permite calcular el **Value at Risk (VaR)** a un nivel de confianza definido (por ejemplo, 95% o 99%).

## Problema Financiero a Resolver
En la gestión de riesgos (*Risk Management*), es fundamental responder a la pregunta: *"¿Cuál es la máxima pérdida que podría sufrir este portafolio en un horizonte de tiempo específico, con un determinado nivel de confianza?"*. Los modelos paramétricos tradicionales a menudo subestiman el riesgo al asumir distribuciones estrictamente normales. Este modelo resuelve dicho problema simulando estocásticamente el comportamiento del mercado para generar una distribución empírica de Pérdidas y Ganancias (PnL), proporcionando una medida de riesgo más flexible y robusta.

## Fundamentos Matemáticos

El **Value at Risk (VaR)** se define estadísticamente como el cuantil de la distribución de pérdidas. Si $L$ representa la pérdida del portafolio, el VaR con un nivel de confianza $\alpha$ es el valor tal que la probabilidad de que la pérdida supere el VaR es igual a $1 - \alpha$:
$$P(L > VaR_{\alpha}) = 1 - \alpha$$

Para calcular este valor empíricamente a través de la Simulación de Montecarlo, el algoritmo ejecuta el siguiente flujo matemático:
1. **Calibración:** Se extraen los rendimientos esperados ($\mu$) y la volatilidad histórica ($\sigma$) de la serie de datos.
2. **Generación Estocástica:** Se simulan $N$ escenarios futuros (trayectorias) utilizando variables aleatorias que replican la dispersión observada en el mercado.
3. **Valuación:** Se calcula el valor proyectado del portafolio en el horizonte temporal $T$ para cada trayectoria.
4. **Inferencia del Riesgo:** Se construye la distribución de PnL y se aísla el percentil correspondiente al nivel de significancia deseado para determinar la barrera del VaR.

## Stack Tecnológico
* **Lenguaje:** Python 3
* **Cálculo Numérico y Simulación:** `NumPy`, `Pandas`
* **Visualización de Distribuciones:** `Matplotlib` (o librerías afines utilizadas en el entorno).

## Instrucciones de Ejecución
1. Clonar el repositorio.
2. Instalar las dependencias correspondientes (`pandas`, `numpy`, `matplotlib`, etc.).
3. Ejecutar secuencialmente el notebook `Value_at_risk.ipynb` en un entorno compatible (Jupyter Notebook, JupyterLab o VS Code).
