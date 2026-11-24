# Telco Customer Churn — práctica de Git

**Nota sobre datos:** `data/telco_demo.csv` es un dataset **sintético**, con columnas inspiradas en Telco Customer Churn. No es una copia de Kaggle ni contiene datos de clientes reales. Se incluye para que la práctica funcione sin descargar nada. Para las prácticas posteriores se puede sustituir por el dataset real de Kaggle, revisando nombres y esquema.

## Requisitos
- Windows con Python 3.10+ y Git instalados.
- Visual Studio Code con terminal integrada (PowerShell).

## Ejecutar
```powershell
py -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m src.train --model forest
.\.venv\Scripts\python.exe -m src.train --model logistic
.\.venv\Scripts\python.exe -m src.train --model svm
```

Si `py` no existe, sustituirlo por `python`. La ejecución mediante `.venv\Scripts\python.exe` evita cambiar la política de ejecución de PowerShell.

## Git
Seguir `GUIA_GIT.md`. Este ZIP no contiene `.git`, para que cada alumno inicialice su propio repositorio.
Este proyecto utiliza Regresión Logística, Random Forest y SVM.

<<<<<<< HEAD
## Evaluación de modelos
Para medir el desempeño de los algoritmos de clasificación sobre el conjunto de prueba, utilizaremos tres métricas complementarias[cite: 9]:

- **Accuracy:** Proporción total de predicciones correctas realizadas por el modelo[cite: 9].
- **F1:** Media armónica entre precisión y exhaustividad (*recall*), útil para evaluar el equilibrio en la detección de clientes que abandonan el servicio[cite: 9].
- **ROC-AUC:** Área bajo la curva ROC, que mide la capacidad del modelo para distinguir entre clases a partir de sus probabilidades estimadas[cite: 9].
Precision (Precisión): Porcentaje de clientes que realmente abandonaron el servicio entre todos los que el modelo predijo como abandono. Indica qué tan confiables son las alertas positivas.

Recall (Exhaustividad): Porcentaje de casos reales de abandono que el modelo logró identificar correctamente. Mide la capacidad del modelo para no dejar pasar clientes en riesgo.
=======
## Modelo SVM
Support Vector Machine (SVM) es un algoritmo de aprendizaje supervisado que busca el hiperplano óptimo para separar las clases de datos. En este proyecto se utiliza con un kernel RBF (`C=1.0`) y estimación de probabilidades habilitada para clasificar el abandono de clientes (*churn*)[cite: 9].

## Resultados del proyecto
Se entrenaron y evaluaron tres modelos de clasificación supervisada (**Regresión Logística**, **Random Forest** y **SVM**) sobre el conjunto de datos `data/telco_demo.csv`, aplicando una partición estratificada (75 % entrenamiento y 25 % prueba) y un *pipeline* de preprocesamiento con estandarización numérica (`StandardScaler`) y codificación *One-Hot* para variables categóricas.

### Comparativa de métricas
| Modelo | Accuracy | F1-score | ROC-AUC |
| :--- | :---: | :---: | :---: |
| Regresión Logística (`logistic`) | 0.000 | 0.000 | 0.000 |
| Random Forest (`forest`) | 0.000 | 0.000 | 0.000 |
| Support Vector Machine (`svm`) | 0.000 | 0.000 | 0.000 |

### Conclusiones técnicas
- **Reproducibilidad:** El uso de una semilla fija (`random_state=42`) y un entorno virtual aislado garantiza que los experimentos puedan replicarse de forma consistente.
- **Persistencia del modelo:** El pipeline entrenado se serializa automáticamente en `models/model.joblib`, dejándolo listo para inferencia o despliegue sin reentrenar.
- **Flujo colaborativo (MLOps):** La gestión mediante ramas, *commits* atómicos y *Pull Requests* mantiene sincronizados el código y la documentación entre el entorno local y GitHub.

>>>>>>> feature/svm 
