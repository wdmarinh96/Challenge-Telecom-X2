
# Telecom X - Parte 2: Predicción de Cancelación de Clientes (Churn)

## Propósito del Análisis

El objetivo principal de este proyecto es **predecir la cancelación (churn) de clientes** en Telecom X utilizando variables relevantes extraídas y preparadas a partir de la base de datos original. Esta predicción busca ayudar a la empresa a identificar clientes con riesgo de abandono para tomar medidas preventivas y mejorar la retención.

## Proceso de Preparación de Datos

1. **Clasificación de variables:**

   - **Variables categóricas:** incluyen columnas como `gender`, `Contract`, `PaymentMethod`, `InternetService`, entre otras que representan atributos discretos o cualitativos.
   - **Variables numéricas:** abarcan `tenure`, `Charges.Monthly`, `Charges.Total`, `Cuentas_Diarias` (nuevo cálculo de gasto diario).

2. **Limpieza y corrección:**

   - Se corrigieron valores faltantes o erróneos en columnas como `Charges.Total`.
   - Se eliminaron o imputaron valores faltantes para asegurar consistencia.
   - Transformación de variables anidadas en columnas planas.

3. **Normalización y codificación:**

   - Para modelos sensibles a la escala (Regresión Logística y KNN), se aplicó estandarización (`StandardScaler`) a las variables numéricas para evitar que magnitudes diferentes afecten la modelización.
   - Las variables categóricas se codificaron usando One-Hot Encoding para convertirlas en un formato numérico comprensible para los modelos.

4. **División del dataset:**

   - El conjunto de datos se dividió en entrenamiento (70%) y prueba (30%) usando una división estratificada para preservar la proporción de cancelación en ambos conjuntos.
   - Esta estrategia asegura que el modelo pueda generalizar mejor y evaluarse objetivamente.

---

## Justificación de Decisiones durante la Modelización

- Se eligieron dos modelos representativos:
  - **Regresión Logística**, que requiere normalización, para aprovechar su capacidad interpretativa y buen desempeño en problemas lineales.
  - **Random Forest**, que no requiere normalización, para capturar posibles relaciones no lineales y evaluar la robustez ante diferentes escalas.

- La normalización fue fundamental para el modelo logístico y KNN, ya que estos dependen de las magnitudes o distancias entre variables.

- La división estratificada protege frente a sesgos que puedan surgir por desbalance en la variable objetivo.

---

## Análisis Exploratorio de Datos (EDA) - Gráficos e Insights

- **Distribución del churn:**  
  Aproximadamente el 26% de los clientes cancelan el servicio, lo que representa un punto crítico para la empresa.

- **Churn por tipo de contrato:**  
  Clientes con contratos mes a mes son los que más cancelan, indicando mayor vulnerabilidad sin compromisos largos.

- **Relación entre antigüedad y churn:**  
  Clientes con menor tiempo en la empresa presentan mayor riesgo de cancelar, especialmente en los primeros meses.

- **Impacto de método de pago:**  
  El pago por cheque electrónico muestra asociación con mayor tasa de cancelación, sugiriendo posibles mejoras en opciones de pago.

- **Cargos y abandono:**  
  Cargos mensuales más altos parecen aumentar la probabilidad de churn, indicando percepción de valor a revisar.

Estos insights respaldaron la construcción y justificación de los modelos predictivos.

---

## Instrucciones para Ejecutar el Cuaderno

### Requisitos - Bibliotecas principales

- Python 
- pandas
- numpy
- scikit-learn
- seaborn
- matplotlib
- requests (para cargar datos originales desde la URL)

Puedes instalarlas con:

pip install pandas numpy scikit-learn seaborn matplotlib requests

text

### Carga de Datos Tratados

 el cuaderno incluye el código en formato raw :https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/main/TelecomX_Data.json para descargar y preparar los datos desde el JSON público, realizar la limpieza y generación del CSV.

### Ejecución

- Ejecuta todas las celdas del cuaderno de principio a fin para reproducir el análisis completo.
- Verás desde la preparación, exploración, modelamiento, evaluación y visualización.

---

Este proyecto busca ser claro y reproducible para apoyar la toma de decisiones en Telecom X y está abierto a mejoras con nuevos modelos o variables según el avance del análisis.

---


¡Gracias por revisar este trabajo!
