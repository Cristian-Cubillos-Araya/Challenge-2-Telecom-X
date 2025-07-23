# Informe: Análisis de Cancelación de Clientes

## 1. Modelos Evaluados 

Se probaron dos modelos para predecir cuándo los clientes podrían cancelar sus contratos. Los modelos son: 

- **XGBoost con SMOTEENN** (Seleccionado final)
- **RandomForest con SMOTEENN**
  
Ambos mostraron resultados muy parecidos. La técnica de **SMOTEENN** ayudó a equilibrar las clases, combinando sobremuestreo (SMOTE) con limpieza de datos (ENN).

## 2. Variables Clave que Influyen en la Cancelación

Según la importancia de las variables en el modelo XGBoost, estas fueron las más relevantes:

| Variable                 | Importancia (%) | Interpretación                                                                 |
|-------------------------|-----------------|--------------------------------------------------------------------------------|
| Contrato_Month-to-month | 50.8            | Los contratos mes a mes concentran la mayoría de cancelaciones.               |
| Seguridad_Online_No     | 11.2            | La ausencia de seguridad online se asocia a una mayor tasa de cancelación.   |
| Servicio_Tecnico_No     | 9.9             | La falta de soporte técnico podría llevar a experiencias negativas y baja.   |

* Variables como `Antigüedad` y `Cargos Totales` tuvieron menos impacto en el modelo en comparacion con el modelo RandomForest, en el cual tienen mayor impacto.

## 3. Comparación de Modelos 

| Modelo                  | Métricas Principales | Valor Aprox. | Observaciones                                                         |
|------------------------|-------------------|--------------|------------------------------------------------------------------------|
| XGBoost + SMOTEENN     | F1-score, Recall           | 0.63, 0.73       | Buen equilibrio entre precisión y recall. Buenas explicaciones.       |
| RandomForest + SMOTEENN| F1-score, Recall           | 0.63, 0.73      | Desempeño muy cercano. Ligera desventaja frente a XGBoost.            |
### Metricas RandomForest
<img width="356" height="137" alt="image" src="https://github.com/user-attachments/assets/6239dfe3-c97d-4d10-9a11-fe9688634f45" />

### Metricas XGBoost
<img width="355" height="136" alt="image" src="https://github.com/user-attachments/assets/4acacced-7357-4039-8648-b716ae518e97" />


## 4. Recomendaciones para Mantener a los Clientes 

1. **Revisar los Contratos mes a mes** - Ofrecer incentivos para que pasen a contratos de más tiempo. 
2. **Añadir Seguridad Online como servicio estándar** - Incorporarlo automáticamente o destacarlo mejor en la venta. 
3. **Mejorar el Servicio Técnico** - Aumentar la cobertura. 
4. **Contactar proactivamente a clientes en riesgo** - Usar el modelo para identificar y comunicarse con quienes podrían cancelar para prevenirlo.
