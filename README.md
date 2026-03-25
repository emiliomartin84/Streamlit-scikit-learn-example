# Práctica 1: Despliegue con Streamlit 🚀

Este repositorio contiene la simulación de la puesta en producción de un modelo predictivo para la Suscripción de Producto Bancario.

## 📂 Archivos Principales
- **[`entrenamiento_modelo.ipynb`](https://github.com/emiliomartin84-uc3m/Streamlit-scikit-learn-example/blob/main/entrenamiento_modelo.ipynb)**: Notebook de Jupyter donde se crea, entrena y se exporta el *Pipeline* completo de Scikit-Learn.
- **[`modelo_produccion.joblib`](https://github.com/emiliomartin84-uc3m/Streamlit-scikit-learn-example/blob/main/modelo_produccion.joblib)**: El modelo final exportado y listo para ser consumido.
- **[`app_produccion.py`](https://github.com/emiliomartin84-uc3m/Streamlit-scikit-learn-example/blob/main/app_produccion.py)**: Aplicación web interactiva programada en Streamlit.

---

## ⚙️ Instalación y Uso

1. **Instalar dependencias**:
   Abre una terminal en esta misma carpeta y ejecuta:
   ```bash
   pip install -r requirements.txt
   ```

2. **Ejecutar la aplicación**:
   Levanta la interfaz web de predicción en tiempo real simplemente escribiendo:
   ```bash
   streamlit run app_produccion.py
   ```
   *(Automáticamente se abrirá una nueva pestaña en tu navegador web mostrando el dashboard).*
