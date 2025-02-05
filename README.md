## Alzheimers Project

En este estudio se evaluaron los tres modelos de clasificación más prometedores para predecir la probabilidad de Alzheimer a partir de información clínica y resultados de exámenes médicos. Se utilizó el AUC-ROC como métrica principal debido a su capacidad para evaluar la discriminación del modelo sin depender de un umbral de clasificación fijo.

#### Resultados Iniciales (sin optimización)
- **Random Forest:** AUC-ROC = 0.9363  
- **Gradient Boosting Classifier:** AUC-ROC = 0.9305  
- **XGBoost:** AUC-ROC = 0.9291

![Comparacion de Modelos](img/comparacion_modelos_val_cross_relevantes.png)

---

#### Random Forest Optimizado
- **Entrenamiento:** AUC-ROC = 0.9629  
- **Prueba:** AUC-ROC = 0.9408  
- **Validación:** AUC-ROC = 0.9257  

Este modelo muestra un desempeño sólido y consistente, con una ligera disminución del AUC-ROC de entrenamiento a validación, lo cual es normal y sugiere buena capacidad de generalización.

![Random Forest Optimizado](img/curva_roc_random_forest_classifier_opt_relevantes.png)

![Metricas de Random Forest Optimizado](img/metricas_random_forest_classifier_opt.png)


---

#### Gradient Boosting Optimizado
- **Entrenamiento:** AUC-ROC = 0.9937  
- **Prueba:** AUC-ROC = 0.9377  
- **Validación:** AUC-ROC = 0.9307  

Aunque el modelo presenta un AUC-ROC casi perfecto en entrenamiento, la diferencia con los conjuntos de prueba y validación indica un posible sobreajuste, lo que podría limitar su desempeño en datos nuevos.

![Gradient Boosting Optimizado](img/curva_roc_random_gradient_boosting_classifier_opt_relevantes.png)

![Metricas de Gradient Boosting Optimizado](img/metricas_gradient_bossting_opt.png)

---

#### XGBoost Optimizado
- **Entrenamiento:** AUC-ROC = 0.9775  
- **Prueba:** AUC-ROC = 0.9365  
- **Validación:** AUC-ROC = 0.9272  

Este modelo ofrece buenos resultados en general, aunque sus métricas en validación son ligeramente inferiores a las obtenidas por el modelo Random Forest optimizado.

![XGBoost Optimizado](img/curva_roc_random_xgboost_classifier_opt_relevantes.png)

![Metrica de XGBoost Optimizado](img/metricas_random_xgboster_opt.png)

---

![Distribucion de indice de Riesgo](img/Distribucion_indices_riesgo_test_valid.png)

#### Selección del Modelo Final

Considerando la consistencia de los resultados en entrenamiento, prueba y validación, **el modelo Random Forest optimizado** se destaca por su equilibrio y robustez. Con un AUC-ROC de 0.9629 en entrenamiento, 0.9408 en prueba y 0.9257 en validación, este modelo demuestra una sólida capacidad de generalización y se escoge como la opción final para predecir qué pacientes podrían tener Alzheimer a partir de la información clínica y de exámenes médicos.

