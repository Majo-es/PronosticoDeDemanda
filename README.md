# PronosticoDeDemanda

# Objetivo
Este proyecto se centró en la predicción de la demanda de un producto durante los
próximos doce meses, utilizando como base los datos históricos de ventas de los últimos cinco
años. Para lograr este objetivo, se llevó a cabo un análisis comparativo entre dos modelos de
pronóstico: **Alisado Triple (Holt-Winters**) y **ARIMA**, con el objetivo de identificar cuál ofrecía
una mayor precisión en la predicción de la demanda futura.

# Análisis de Datos y Preparación:
Se analizaron los datos y encontramos necesario crear una columna index llamada fecha
para asegurar que la serie estuviera en un orden cronológico. Se identificó una tendencia
creciente y una estacionalidad anual en la demanda, la cual se repetía cada año.

# Modelado y Evaluación:
- En la etapa de modelado y evaluación, se exploraron las variantes aditiva y multiplicativa
del modelo Alisado Triple (Holt-Winters). Se observaron diferencias significativas en las
predicciones a largo plazo entre ambos modelos. Al final, se determinó que el modelo
multiplicativo ofrecía un mejor ajuste, ya que capturaba el incremento de las variaciones
estacionales.
- En cuanto al modelo ARIMA, era necesario diferenciar la serie temporal para lograr la
estacionariedad. Se utilizó la función auto_arima para optimizar la selección de parámetros, y al
final se determinó que el modelo ARIMA(1,1,0)(0,1,0,12) ofrecía el mejor rendimiento, con
coeficientes significativos y los valores más bajos de AIC y BIC. También, se demostró que los
residuos de este modelo cumplían con los criterios de ruido blanco, normalidad y varianza
constante.
- Se llevó a cabo una validación para comparar ambos modelos, en la que se comprobó que
el modelo ARIMA(1,1,0)(0,1,0,12) era el que mejor se ajustaba a los datos, al presentar los
valores más bajos de **RMSE**,**MAPE** y **MAE**.

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
