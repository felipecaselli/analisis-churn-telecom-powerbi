# Análisis de Fuga de Clientes (Churn) en Telecom con Power BI

![Banner de Power BI o Telecom](https://i.imgur.com/g9b4O8R.png) 
*( reemplazar esta imagen con una captura de pantalla del dashboard terminado)*

## 1. Contexto del Proyecto

Este proyecto es un análisis exploratorio de datos (EDA) completo sobre un dataset de una empresa de telecomunicaciones ficticia. El objetivo principal es **identificar los factores clave** que influyen en la fuga de clientes (churn) y **presentar estos hallazgos en un dashboard interactivo** en Power BI, diseñado para la toma de decisiones gerenciales.

Este repositorio contiene:
* El notebook de Jupyter (`analisis_churn.ipynb`) con todo el proceso de limpieza y análisis.
* El dataset original (`WA_Fn-UseC_-Telco-Customer-Churn.csv`).
* El archivo final de Power BI (`reporte_churn.pbix`) y el dataset limpio (`churn_limpio.csv`).

## 2. Stack Tecnológico 🛠️

Para este proyecto se utilizaron las siguientes herramientas:

* **Python:** Como lenguaje principal de análisis.
* **Pandas:** Para la manipulación y limpieza de datos.
* **NumPy:** Para operaciones numéricas (especialmente en la limpieza).
* **Matplotlib & Seaborn:** Para la visualización de datos estática durante la fase de exploración.
* **Jupyter Notebook:** Como entorno de trabajo interactivo.
* **Power BI:** Para la creación del dashboard interactivo final.

## 3. Proceso de Análisis y Limpieza de Datos

El notebook de Jupyter documenta el siguiente proceso:

1.  **Carga de Datos:** Importación del dataset `.csv`.
2.  **Exploración Inicial:** Uso de `.info()`, `.describe()` y `.isnull().sum()` para un primer diagnóstico.
3.  **Limpieza de Datos:**
    * **Manejo de `TotalCharges`:** Se identificó que la columna `TotalCharges` era de tipo `object` (texto) debido a valores vacíos.
    * **Investigación:** Se descubrió que estos valores correspondían a clientes con `tenure = 0` (clientes nuevos).
    * **Transformación:** Se convirtieron los valores vacíos a `0` y se cambió el tipo de columna a `float64` (numérico).
4.  **Análisis Exploratorio (EDA):**
    * Se analizó la distribución de la variable objetivo (`Churn`).
    * Se crearon visualizaciones (gráficos de barras, histogramas) para entender la relación entre la fuga de clientes y otras variables como:
        * Tipo de contrato (`Contract`)
        * Antigüedad (`tenure`)
        * Método de pago (`PaymentMethod`)
        * Servicios contratados (ej. `OnlineSecurity`, `TechSupport`)

## 4. Dashboard Interactivo en Power BI

El análisis del notebook se utilizó como base para construir un dashboard dinámico en Power BI que permite a un usuario de negocio (ej. un gerente) filtrar y explorar los datos sin necesidad de código.

[ **Ver el Dashboard Interactivo (Enlace Público)** ] 
*( enlace del reporte de Power BI en la web)*

### Captura del Dashboard
![Captura de pantalla del dashboard de Power BI](https... .png)

## 5. Principales Hallazgos (Key Insights) 💡

* **Contrato:** Los clientes con contrato **mes a mes** tienen una tasa de fuga drásticamente mayor que los clientes con contratos anuales.
* **Servicios Clave:** Los clientes **sin** servicios de soporte como `OnlineSecurity` o `TechSupport` son mucho más propensos a irse.
* **Antigüedad:** La mayoría de la fuga ocurre en los **primeros 6 meses** de servicio.
