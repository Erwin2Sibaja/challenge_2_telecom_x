Análisis de Retención y Abandono de Clientes (Churn)

Adquirir un nuevo cliente es mucho más caro que retener a uno existente. Este proyecto es un análisis exploratorio de datos enfocado en entender el abandono de clientes de una empresa de telecomunicaciones.

A través de la limpieza de datos y la creación de visualizaciones interactivas, el objetivo fue dejar de adivinar y dejar que los datos nos cuenten la historia: ¿Por qué se van los clientes y qué patrones tienen en común los que deciden quedarse?

Tecnologías y Herramientas
Lenguaje: Python

Entorno: Google Colab / Jupyter Notebook

Limpieza y Manipulación: Pandas, NumPy

Visualización de Datos: Plotly (Gráficos interactivos), Seaborn y Matplotlib (Gráficos estadísticos y de densidad)

El Reto de los Datos: Limpieza y Transformación
El dataset original presentaba un reto técnico interesante: los datos venían en formato de JSON anidado dentro de las columnas de un DataFrame.

Para preparar el terreno, realizamos los siguientes pasos de ingeniería de datos:

1.- Extraimos múltiples diccionarios anidados (customer, phone, internet, account) convirtiéndolos en columnas tabulares estructuradas usando pd.json_normalize.

2.- Limpiamos respuestas redundantes (ej. unificar "No internet service" a simplemente "No") y estandarizamos formatos numéricos regionales (cambio de comas por puntos en facturación).

3.- Transformamos variables categóricas binarias (Yes/No) a formato computacional (1/0) para habilitar el análisis matemático.

4.- Creamos una nueva métrica llamada Cuentas_Diarias a partir de la facturación mensual para medir el gasto a un nivel de mayor granularidad.

Análisis y Visualización
Se construyó un panel de análisis visual enfocado en comunicar hallazgos de manera clara para la toma de decisiones estratégicas:

1.- Gráficos de Barras: Para establecer un "Ranking de Riesgo" e identificar qué tipo de contratos o métodos de pago tienen las mayores tasas de cancelación.

2.- Histogramas Porcentuales: Para entender la distribución numérica y descubrir en qué mes exacto de antigüedad o nivel de precio ocurre la mayor fuga.

<img width="1400" height="699" alt="image" src="https://github.com/user-attachments/assets/31f8bbdd-b9f7-4e41-a339-ccb28035b1bd" />
<img width="857" height="494" alt="image" src="https://github.com/user-attachments/assets/4af504ab-4e7e-4652-bc51-5f5f17b14ef3" />
<img width="850" height="504" alt="image" src="https://github.com/user-attachments/assets/0faced24-5664-4613-9788-653069b9772c" />
<img width="849" height="494" alt="image" src="https://github.com/user-attachments/assets/5cdac7ff-810f-4278-a618-2bf898bf7ab5" />
<img width="853" height="499" alt="image" src="https://github.com/user-attachments/assets/7424a823-5623-461c-92b7-8e008cf64871" />

Descubrimientos Clave
La barrera de los primeros meses: El riesgo de abandono es crítico al inicio. Si un cliente supera los primeros meses de servicio, la probabilidad de que se vuelva leal a largo plazo aumenta drásticamente.

La trampa del mes a mes: Los usuarios con contratos mensuales (Month-to-month) representan el mayor foco rojo de cancelaciones. La fricción de renovar o pagar cada 30 días facilita la salida.

Anomalías en el Servicio: Detectamos una tasa de abandono inusualmente alta en los clientes que cuentan con internet por Fibra Óptica y en aquellos que utilizan Cheque Electrónico como método de pago, sugiriendo áreas urgentes de revisión técnica y administrativa.

El valor del Soporte: Los clientes sin soporte técnico contratado tienden a cancelar su servicio ante la primera falla o frustración.

Cómo ejecutar este proyecto
Clona este repositorio:

Bash
git clone https://github.com/Erwin2Sibaja/challenge_2_telecom_x.git
Abre el archivo Telecom X - Análisis de Evasión de Clientes.ipynb en Google Colab o en tu entorno local de Jupyter.

Asegúrate de tener las librerías instaladas (pip install pandas plotly seaborn matplotlib).

Ejecuta las celdas secuencialmente para ver el proceso de limpieza y la generación de gráficos interactivos.
