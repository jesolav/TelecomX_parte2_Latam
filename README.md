# 📊 Telecom X - Parte 2: Predicción de Churn

## 🎯 Propósito del análisis
El objetivo principal de este proyecto es **predecir el churn (cancelación de clientes)** en la empresa ficticia *Telecom X LATAM*, utilizando variables relevantes de comportamiento, facturación y características del cliente.  
Este análisis permite **identificar patrones asociados al abandono** y proponer **estrategias de retención** basadas en datos.

---

## 📂 Estructura del proyecto
- `TelecomX_Churn_Part2.ipynb` → Notebook principal con el flujo completo de análisis, EDA, modelado y conclusiones.  
- `datos_tratados.csv` → Datos previamente limpios y estandarizados en la Parte 1.  
- `model_metrics.csv` → Métricas de los modelos entrenados (Accuracy, Precision, Recall, F1).  

---

## ⚙️ Preparación y preprocesamiento de datos

1. **Clasificación de variables**  
   - **Categóricas**: tipo de plan, método de pago, contrato, etc.  
   - **Numéricas**: tenure (antigüedad), cargos mensuales, cargos totales, etc.  

2. **Transformaciones aplicadas**  
   - One-Hot Encoding para variables categóricas.  
   - Normalización para variables numéricas (cuando aplica).  
   - Imputación de valores faltantes.  

3. **Partición de datos**  
   - Entrenamiento: 80%  
   - Prueba: 20%  
   - Estratificación aplicada para mantener la proporción de churn (≈26–27%).  

4. **Decisiones de modelado**  
   - **Regresión Logística**: modelo interpretable, útil para ver impacto de variables (coeficientes).  
   - **Random Forest**: modelo robusto no lineal, permite capturar interacciones complejas.  
   - **SMOTE**: aplicado para balancear la clase minoritaria y mejorar recall.  

---

## 📈 Exploratory Data Analysis (EDA)
Algunos hallazgos y gráficos clave:
- **Distribución de churn**: ~27% de clientes cancelan → desbalance moderado.  
- **Correlaciones**: fuerte relación entre cargos mensuales y tipo de contrato.  
- **Insights**:  
  - Clientes con **tenure bajo** y **contratos mensuales** tienden más al churn.  
  - Clientes con **facturación alta** también muestran riesgo de cancelación → requieren planes personalizados.  

Ejemplos de gráficos generados:
- Heatmap de correlaciones.  
- Matriz de confusión (por modelo).  
- Importancia de features en Random Forest.  
- Top coeficientes en Regresión Logística.  

---

## 🤖 Resultados de modelado
- **Regresión Logística**: mejor balance entre Precision y Recall para clase churn.  
- **Random Forest**: buen accuracy, pero menor recall para churn.  
- **SMOTE**: mejora el recall en ambos modelos, útil para captar clientes en riesgo.  

---

## ▶️ Ejecución del notebook
### Requisitos
Instalar librerías necesarias:
```bash
pip install pandas numpy scikit-learn imbalanced-learn matplotlib seaborn
