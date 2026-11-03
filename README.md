# telecom-analysis-sprint7-final-project-. # 📊 Análisis Exploratorio y Preparación de Datos - ConnectaTel (Latinoamérica)

## 🎯 Objetivo del Proyecto
Realizar un flujo guiado y completo de análisis exploratorio de datos (EDA), limpieza y preparación de datos para la empresa de telecomunicaciones **ConnectaTel**, evaluando el comportamiento de los clientes, patrones de uso, tratamiento de valores nulos/sentinels y detección de outliers para soportar la toma de decisiones estratégicas de negocio.

---

## 📂 Datasets Utilizados
El proyecto utiliza tres fuentes de datos principales:
1. **`plans.csv`**: Contiene la información comercial sobre los planes de telecomunicaciones ofrecidos a los clientes.
2. **`users_latam.csv`**: Almacena el perfil demográfico y de clientes (`user_id`, `age`, `city`, `reg_date`, `plan`, `churn`).
3. **`usage.csv`**: Datos transaccionales de uso del servicio móvil (`user_id`, `date`, `type`, `duration`, `length`).

---

## 🛠️ Etapas del Análisis Realizadas
1. **Exploración Inicial**: Carga de datos, revisión de tipos de datos, inspección de valores categóricos y numéricos.
2. **Limpieza Básica y Tratamiento de Sentinels**:
   - Reemplazo de valores centinela en edad (`-999`) por la mediana.
   - Normalización de valores faltantes en ciudad (`?` reemplazado por `pd.NA`).
   - Estandarización y conversión de fechas con detección y filtrado de años futuros imposibles (`2026`).
3. **Diagnóstico de Nulos (MAR)**: Verificación sistemática de los nulos en `duration` y `length` en función de la columna `type`, confirmando que son *Missing At Random* (MAR) y decidiendo mantenerlos como nulos para evitar sesgos.
4. **Agregación de Métricas por Usuario**: Consolidación de los datos transaccionales de `usage` agrupados por `user_id` para obtener variables clave (`cant_mensajes`, `cant_llamadas`, `cant_minutos_llamada`), combinándolas con el perfil demográfico para generar el DataFrame integrado `user_profile`.
5. **Visualización y Detección de Outliers**: Gráficos de distribución (histogramas) por tipo de plan y boxplots automáticos mediante el método IQR, validando y decidiendo mantener los valores atípicos (*power users*).
6. **Insight Ejecutivo**: Traducción de los hallazgos técnicos en recomendaciones comerciales accionables para los stakeholders.

---

## 🚀 Cómo Ejecutar el Notebook
Puedes ejecutar y explorar este proyecto paso a paso de manera interactiva:
1. Sube los archivos del repositorio y los datasets (`plans.csv`, `users_latam.csv`, `usage.csv`) a tu entorno de trabajo en la nube.
2. Abre el notebook principal en **Google Colab** o Jupyter Notebook.
3. Asegúrate de tener instaladas las librerías requeridas (`pandas`, `numpy`, `seaborn`, `matplotlib`).
4. Ejecuta las celdas de forma secuencial de arriba hacia abajo.

---

## 📋 Guía de Reproducción
1. Clona o descarga este repositorio en tu máquina local o entorno en la nube.
2. Verifica que la ruta de los archivos CSV coincida con la definida en las primeras celdas de carga de datos.
3. Ejecute el script de limpieza para transformar los centinelas y normalizar las fechas.
4. Genere las tablas agregadas (`user_profile`) para habilitar las visualizaciones estadísticas y la sección de analítica avanzada.
