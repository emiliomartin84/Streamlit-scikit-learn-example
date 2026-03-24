# INTELIGENCIA BIG DATA

---

### Extensión de la Práctica #1:
**Desplegando el Modelo Final (Pipeline Completo) de Suscripción de Producto Bancario mediante Streamlit**

**2025-26**

---

### Índice de Contenidos

- [Introducción](#introducción)
- [Pasos a seguir](#pasos-a-seguir)
  1. [Generar el archivo con tu Pipeline Final e información adicional](#1-generar-el-archivo-con-tu-pipeline-final-e-información-adicional)
  2. [Adaptar el script `app_produccion.py` de Streamlit a tu problema](#2-adaptar-el-script-app_produccionpy-de-streamlit-a-tu-problema)
  3. [Verificar que la aplicación de Streamlit funciona y genera predicciones correctas](#3-verificar-que-la-aplicación-de-streamlit-funciona-y-genera-predicciones-correctas)
- [Qué debes entregar](#qué-debes-entregar)

---

### Introducción

El objetivo de esta extensión a la primera práctica es simular la puesta en producción del modelo final obtenido al terminar dicha práctica. En otras palabras, desplegar el modelo de forma que pueda ser consultado e inferido con nuevos datos de clientes.

Para usar el modelo final (o más adecuadamente tu pipeline completo final, que incluye todo el preprocesamiento de datos) con la plataforma Streamlit, es necesario proveer a la interfaz web con el modelo en sí mismo y la metadata y parámetros básicos acerca de las variables numéricas y categóricas, para que Streamlit pueda diseñar automáticamente la interfaz y los controles adecuados donde introducir los nuevos datos al vuelo.

- El notebook **`entrenamiento_modelo.ipynb`** (proporcionado junto con tu material) muestra cómo guardar usando `joblib` el modelo y la información mencionada antes en un paquete para uso posterior en Streamlit. En el código proporcionado verás un pequeño ejemplo ficticio con simulaciones. En la vida real (para la práctica) el uso es más complejo puesto que existen variables tanto numéricas como categóricas y tu modelo usa un preprocesado avanzado (el pipeline entero conforma el modelo), pero puedes observar esta mecánica como guía. Por lo tanto, tendrás que adaptar `entrenamiento_modelo.ipynb` al código de tu primera práctica. Tras ejecutarse, tu notebook generará y guardará el fichero **`modelo_produccion.joblib`**, que luego levantará Streamlit.
  
- Para ejecutar todo correctamente (incluyendo Streamlit y el resto de las bibliotecas del modelo), debes instalar las dependencias del proyecto. Abre tu línea de comandos o terminal en esta carpeta y ejecuta:
  `pip install -r requirements.txt`
  (se da por entendido que cuentas ya con una distribución y entorno de Python como Anaconda o similar).

- Finalmente, hay que lanzar la aplicación web. Te proporcionamos también el fichero **`app_produccion.py`**, que es un panel de ejemplo que aprovecha toda la potencialidad de Streamlit y el archivo serializado anteriormente. Una vez que tu fichero `modelo_produccion.joblib` esté en la misma carpeta, la aplicación se levantará con el modelo del caso de prueba. El objetivo es que consigas que funcione de para tu conjunto de datos, requiriendo muy poco esfuerzo al ser una plantilla casi lista para ser productivizada.

  La aplicación se despliega cómodamente desde tu entorno de comandos ejecutando:
  `streamlit run app_produccion.py`

Se te abrirá una interfaz en tu navegador por defecto que permitirá cambiar de forma interactiva e insertar de forma cómoda cualquier conjunto nuevo de valores simulando su captura, y obteniendo una predicción en tiempo real.

---

### Pasos a seguir

1. **Generar el archivo con tu Pipeline Final e información adicional**
   Adapta el notebook `entrenamiento_modelo.ipynb` para que recoja tu pipeline final entrenado de la primera parte de tu práctica y extraiga la información útil de las columnas. Guardalo todo en un diccionario que finalice persistido en disco como tu fichero consolidado **`modelo_produccion.joblib`**.

2. **Adaptar el script `app_produccion.py` de Streamlit a tu problema**
   Usa la estructura proporcionada o adáptala a tu gusto si el diseño te pide otros enfoques.

3. **Verificar que la aplicación de Streamlit funciona y genera predicciones correctas**
   Escoge tres nuevos registros (es decir, decide internamente 3 escenarios y combinaciones de valores para clientes nuevos que no estaban en tu conjunto). Introdúcelos en la interfaz visual de Streamlit y captura la predicción obtenida. Luego, compara de manera transparente dicha predicción con la misma que tendrías ejecutando esos mismos datos en puro código Python a través de tu pipeline recién guardado.

   El trabajo a presentar debe contener tres capturas de pantalla de la interfaz de Streamlit donde se aprecien los tres ejemplos distintos junto con sus respectivas predicciones al apretar el botón. Al mismo tiempo, en tu informe deberá constar el código equivalente (por ejemplo, desde el final de tu mismo notebook) usado para obtener los mismos resultados llamando a `pipeline.predict`. Lógicamente, los resultados devueltos por Streamlit y por el trozo de código en el cuaderno deberán ser el mismo valor exactamente.

---

### Qué debes entregar

1. Un Jupyter notebook (`.ipynb`) que cargue tu pipeline definitivo, analice la variables y finalmente efectúe el volcado en tu sistema del fichero de ensamblado exportable `modelo_produccion.joblib`. Este cuaderno puede tomar prestadas sin límite las líneas mostradas en el notebook base **`entrenamiento_modelo.ipynb`**. De hecho, para que esté completo este cuaderno ilustrará también la validación en código contra tres puntos aleatorios adicionales (aquellos mismos que vayas a contrastar posteriormente en la interfaz elaborada por Streamlit).
2. Un script en Python puro (`.py`) que encierre toda la lógica de tu plataforma Streamlit, basado altamente en el archivo provisto de muestra **`app_produccion.py`**.
3. Un pequeñísimo documento o informe visual, con las tres capturas de pantalla o recortes extraídos directamente desde el panel que levanta Streamlit web reflejando las tres predicciones sobre los 3 puntos de prueba inventados o referenciados durante el paso número 1.
