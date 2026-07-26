# ConnectaTel Customer Analysis

# Project Objective

As a data analyst, the objective of this project is to evaluate the **behavior of ConnectaTel's customers**, a telecommunications company in Latin America, with data recorded through the year **2024**.

The analysis aims to:
- Clean and validate the quality of the available data.
- Build a per-user usage profile (messages, calls, minutes).
- Segment customers by **usage level** and **age**.
- Translate the findings into **actionable recommendations** for the business, focused on plan offerings and commercial opportunities.

  # Datasets Used

  | File | Description |
  |---|---|
  | `plans.csv` | Information on current plans: price, included minutes, included GB, cost per extra unit. |
  | `users_latam.csv` | User data: name, age, city, plan, registration date, and churn date. |
  | `usage.csv` | Per-user usage log: calls (duration) and messages (length), with date and event type. |

  **Note:** Files are loaded from the `/datasets/` folder within the execution environment.

  # Analysis Stages

  1. **Loading and exploration** — reading the 3 datasets, reviewing shape (`shape`), data types, and overall structure (`.info()`).
  2. **Identifying data quality issues** — null values, sentinels (`-999` in `age`, `"?"` in `city`), and out-of-range dates (impossible years like 2026).
  3. **Basic data cleaning** — imputing sentinels, standardizing dates, and verifying MAR (Missing At Random) nulls in `duration` and `length` based on event type (`call`/`text`).
  4. **Usage statistics per user** — aggregating `usage` by `user_id` (number of messages, calls, and total minutes) and merging with the user profile.
  5. **Distribution and outlier visualization** — histograms per key variable (age, messages, calls, minutes) and boxplots to detect extreme values using the IQR method.
  6. **Customer segmentation** — classification into usage groups (`Bajo uso`, `Uso medio`, `Alto uso`) and age groups (`Joven`, `Adulto`, `Adulto Mayor`).
  7. **Executive insight** — translating findings into conclusions and business recommendations for stakeholders.
 
  # How to Run the Notebook

  1. Open the `Project-ConnectaTel.ipynb` file in Google Colab (https://colab.research.google.com/) or in a local Jupyter environment.
  2. Make sure the files `plans.csv`, `users_latam.csv`, and `usage.csv` are available at the `/datasets/` path (upload them manually if using Colab, or adjust the path if working locally).
  3. Install the required dependencies if you don't already have them: `pip install pandas numpy seaborn matplotlib`.
  4. Run the cells in order, top to bottom (`Runtime → Run all` in Colab, or `Kernel → Restart & Run All` in Jupyter).
    
  # Reproduction Guide

   - The notebook is sequential: each step depends on the transformations made in the previous step (cleaning → aggregation → segmentation → visualization).
   - No credentials or external connections are required; all processing is local on the three CSV files.
   - If the source datasets are updated, simply re-run the full notebook to regenerate the updated metrics, charts, and segments.
       
          ---

     # Análisis ConnectaTel

      # Objetivo del proyecto

         Como analista de datos, el objetivo de este proyecto es evaluar el **comportamiento de los clientes** de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica, con información registrada hasta el año **2024**.

         El análisis busca:
         - Limpiar y validar la calidad de los datos disponibles.
         - Construir un perfil de uso por usuario (mensajes, llamadas, minutos).
         - Segmentar a los clientes por **nivel de uso** y **edad**.
         - Traducir los hallazgos en **recomendaciones accionables** para el negocio, orientadas a la oferta de planes y oportunidades comerciales.
         
     # Datasets utilizados

           | Archivo | Descripción |
           |---|---|
           | `plans.csv` | Información de los planes actuales: precio, minutos incluidos, GB incluidos, costo por extra. |
           | `users_latam.csv` | Datos de los usuarios: nombre, edad, ciudad, plan, fecha de registro y de baja (churn). |
           | `usage.csv` | Registro de uso por usuario: llamadas (duración) y mensajes (longitud), con fecha y tipo de evento. |

           **Nota:** Los archivos se cargan desde la carpeta `/datasets/` dentro del entorno de ejecución.

     # Etapas del análisis

          1. **Carga y exploración** — lectura de los 3 datasets, revisión de forma (`shape`), tipos de datos y estructura general (`.info()`).
          2. **Identificación de problemas de calidad de datos** — valores nulos, sentinels (`-999` en `age`, `"?"` en `city`), y fechas fuera de rango (años imposibles como 2026).
          3. **Limpieza básica de datos** — imputación de sentinels, estandarización de fechas y verificación de nulos MAR (Missing At Random) en `duration` y `length` según el tipo de evento (`call`/`text`).
          4. **Estadísticas de uso por usuario** — agregación de `usage` por `user_id` (cantidad de mensajes, llamadas y minutos totales) y combinación con el perfil de usuario.
          5. **Visualización de distribuciones y outliers** — histogramas por variable clave (edad, mensajes, llamadas, minutos) y boxplots para detectar valores extremos mediante el método IQR.
          6. **Segmentación de clientes** — clasificación en grupos de uso (`Bajo uso`, `Uso medio`, `Alto uso`) y de edad (`Joven`, `Adulto`, `Adulto Mayor`).
          7. **Insight ejecutivo** — traducción de los hallazgos en conclusiones y recomendaciones de negocio para stakeholders.
           
     # Cómo ejecutar el notebook

          1. Abre el archivo `Project-ConnectaTel.ipynb` en Google Colab (https://colab.research.google.com/) o en un entorno Jupyter local.
          2. Asegúrate de que los archivos `plans.csv`, `users_latam.csv` y `usage.csv` estén disponibles en la ruta `/datasets/` (súbelos manualmente si usas Colab, o ajusta la ruta si trabajas en local).
          3. Instala las dependencias necesarias si no las tienes: `pip install pandas numpy seaborn matplotlib`.
          4. Ejecuta las celdas en orden, de arriba hacia abajo (`Runtime → Run all` en Colab, o `Kernel → Restart & Run All` en Jupyter).
              
     # Guía de reproducción

          - El notebook es secuencial: cada paso depende de las transformaciones realizadas en el paso anterior (limpieza → agregación → segmentación → visualización).
          - No se requieren credenciales ni conexiones externas; todo el procesamiento es local sobre los tres archivos CSV.
          - Si se actualizan los datasets de origen, basta con volver a correr el notebook completo para regenerar las métricas, gráficos y segmentos actualizados.
