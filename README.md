# PronosticoDeDemanda/ Predicting Product Demand
@ Leilani A., Maria Jose E., & Maryam F.

# Objetivo
Este proyecto se centró en la predicción de la demanda de un producto durante los
próximos doce meses, utilizando como base los datos históricos de ventas de los últimos cinco
años. Para lograr este objetivo, se llevó a cabo un análisis comparativo entre dos modelos de
pronóstico: `Alisado Triple (Holt-Winters)` y `ARIMA`, con el objetivo de identificar cuál ofrecía
una mayor precisión en la predicción de la demanda futura.

# Análisis de Datos y Preparación:
Se analizaron los datos y encontramos necesario crear una columna index llamada fecha
para asegurar que la serie estuviera en un orden cronológico. Se identificó una tendencia
creciente y una estacionalidad anual en la demanda, la cual se repetía cada año.

# Modelado y Evaluación:
- En la etapa de modelado y evaluación, se exploraron las variantes aditiva y multiplicativa
del modelo `Alisado Triple (Holt-Winters)`. Se observaron diferencias significativas en las
predicciones a largo plazo entre ambos modelos. Al final, se determinó que el modelo
multiplicativo ofrecía un mejor ajuste, ya que capturaba el incremento de las variaciones
estacionales.
<img width="873" alt="Screenshot 2025-03-27 at 14 14 46" src="https://github.com/user-attachments/assets/35af51ba-dbda-4d20-9329-2ea4ac81e7c3" />


- En cuanto al modelo ARIMA, era necesario diferenciar la serie temporal para lograr la
estacionariedad. Se utilizó la función auto_arima para optimizar la selección de parámetros, y al
final se determinó que el modelo `ARIMA(1,1,0)(0,1,0,12)` ofrecía el mejor rendimiento, con
coeficientes significativos y los valores más bajos de AIC y BIC. También, se demostró que los
residuos de este modelo cumplían con los criterios de ruido blanco, normalidad y varianza
constante.
<img width="910" alt="Screenshot 2025-03-27 at 14 13 09" src="https://github.com/user-attachments/assets/c791e9d3-4127-426b-896b-b490e61ea92d" />

- Se llevó a cabo una validación para comparar ambos modelos, en la que se comprobó que
el modelo `ARIMA(1,1,0)(0,1,0,12)` era el que mejor se ajustaba a los datos, al presentar los
valores más bajos de `RMSE`,`MAPE` y `MAE`.

<img width="913" alt="Screenshot 2025-03-27 at 14 10 16" src="https://github.com/user-attachments/assets/4a3b02a6-cb9b-4d79-a8b9-20051d9c58aa" />



# Pronóstico y Conclusión:
Se concluyó que ambos modelos capturaban la estacionalidad de los datos, aunque con
variaciones en la magnitud de las fluctuaciones. Sin embargo, se seleccionó el modelo
ARIMA(1,1,0)(0,1,0,12) como el más preciso para el pronóstico de los próximos doce meses. El
pronóstico resultante mostró una tendencia de crecimiento continuo, con fluctuaciones
estacionales consistentes con el patrón histórico. De cumplirse el pronóstico, la demanda tendrá
un crecimiento proyectado para el futuro de 14.04%. En resumen, se desarrolló un modelo
robusto y preciso para pronosticar la demanda, lo que permitirá a la empresa optimizar la gestión
de inventario, la planificación de la producción y la toma de decisiones estratégicas.


# 🇬🇧 VERSION: 
The project focuses on predicting product demand for the next twelve months using historical sales data from the past five years. It involves a comparative analysis of two forecasting models: `Triple Exponential Smoothing (Holt-Winters)` and `ARIMA`. The goal is to determine which model provides higher accuracy in predicting future demand. The analysis includes data preparation, model evaluation using metrics like `RMSE`, `MAPE`, and `MAE`, and forecasting using the selected model. The project determined that `ARIMA(1,1,0)(0,1,0,12)` was the most precise.

- **Data Analysis and Preparation**: The historical sales data is analyzed, and a date index is created to ensure chronological order. The analysis identifies a growing trend and annual seasonality in demand.
- **Model Selection and Evaluation**:
    - `Holt-Winters`: Additive and multiplicative variations are explored. The multiplicative model is chosen because it better captures increasing seasonal variations.
    - `ARIMA`: The time series is differentiated to achieve stationarity. The auto_arima function is used to optimize parameter selection, resulting in the `ARIMA(1,1,0)(0,1,0,12)` model. The residuals are checked to meet white noise, normality, and constant variance criteria.
Model Validation: The two models are compared, and ARIMA(1,1,0)(0,1,0,12) is selected as the best fit based on the lowest RMSE, MAPE, and MAE values.
- **Forecasting and Conclusion**: The `ARIMA` model is used to forecast demand for the next twelve months. The forecast indicates continued growth with consistent seasonal fluctuations.
  
Sequence Diagram: 

<img width="685" alt="Provides data and requests forecast" src="https://github.com/user-attachments/assets/ad188259-28fc-4e74-8bff-56b8229df5a7" />

