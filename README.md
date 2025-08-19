# Análisis de Evasión de Clientes de TelecomX

## Resumen del Proyecto

Este proyecto realiza un análisis exploratorio de datos (EDA) sobre los datos de clientes de TelecomX para comprender los factores que contribuyen a la evasión de clientes (churn). El objetivo es identificar patrones e información que puedan ayudar a desarrollar estrategias para reducir la pérdida de clientes.

## Fuente de Datos

Los datos utilizados en este análisis provienen de un archivo JSON disponible en:
`https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json`

## Pasos del Análisis

El análisis siguió los siguientes pasos clave:

1.  **Extracción de Datos:** Se cargaron los datos directamente desde la URL proporcionada en un DataFrame de pandas.
2.  **Transformación de Datos:**
    *   Se limpiaron y gestionaron los valores faltantes en la columna 'Churn'.
    *   Se normalizaron las columnas JSON anidadas ('customer', 'phone', 'internet', 'account') en columnas separadas.
    *   Se convirtieron las columnas relevantes a los tipos de datos apropiados (por ejemplo, 'Charges_Total' a float, 'Churn' a int).
    *   Se creó una nueva característica 'Cuentas_Diarias'.
    *   Se mapearon las variables categóricas con valores 'Yes'/'No' o 'Yes'/'No'/'No service' a representaciones numéricas (1 y 0).
    *   Se renombraron las columnas para mayor claridad ('Charges_Monthly' a 'Cuenta_Mensual', 'Charges_Total' a 'Cuenta_Total').
    *   Se mapeó la columna 'gender' a valores numéricos.
3.  **Análisis Exploratorio de Datos:**
    *   Se examinó la distribución de la evasión.
    *   Se visualizó la relación entre 'Cuenta_Mensual' y 'Cuenta_Total' con respecto a la evasión.
    *   Se generó un mapa de calor de correlación para comprender las relaciones entre las variables numéricas.
    *   Se analizó la distribución de la evasión en las variables categóricas clave (género, tipo de contrato, método de pago, servicio de internet, servicio de teléfono) utilizando gráficos de conteo.
    *   Se exploró la distribución de las variables numéricas (antigüedad, cargos mensuales, cargos totales) para clientes que evadieron y no evadieron utilizando box plots.
    *   Se calculó la correlación entre 'Cuentas_Diarias' y la evasión.
    *   Se creó una característica 'Total_Internet_Services' y se calculó su correlación con la evasión.

## Hallazgos Clave

Según el análisis exploratorio de datos, se observaron los siguientes hallazgos clave con respecto a la evasión de clientes:

*   Aproximadamente el 25.7% de los clientes en el conjunto de datos han evadido.
*   Los clientes con **contratos mes a mes** tienen una tasa de evasión significativamente mayor en comparación con aquellos con contratos a más largo plazo.
*   Los clientes que utilizan el **cheque electrónico** como método de pago muestran una propensión considerablemente mayor a evadir.
*   Los clientes con **servicio de internet de fibra óptica** tienen una tasa de evasión más alta que aquellos con DSL o sin servicio de internet.
*   Los clientes con **menor antigüedad** (menor tiempo con la empresa) y **menores cargos mensuales/totales** tienden a evadir más.
*   La correlación entre los cargos diarios y la evasión es positiva pero débil.
*   La correlación entre el número total de servicios de internet y la evasión es ligeramente negativa y muy débil.

## Recomendaciones

Basándose en estos hallazgos, se sugieren las siguientes recomendaciones estratégicas para reducir potencialmente la evasión de clientes:

*   Implementar programas de retención dirigidos a clientes con contratos mes a mes, animándolos a cambiar a planes a más largo plazo con incentivos.
*   Investigar las razones detrás de la alta tasa de evasión entre los usuarios de cheques electrónicos y considerar la promoción de métodos de pago alternativos o abordar los problemas subyacentes.
*   Mejorar la calidad del servicio o abordar puntos débiles específicos para los usuarios de internet de fibra óptica para mejorar su experiencia y reducir la evasión en este segmento.
*   Desarrollar estrategias para aumentar la participación y la lealtad del cliente durante las etapas iniciales de su suscripción, especialmente para aquellos con cargos más bajos.

## Próximos Pasos

*   Continuar con la preparación de datos para el modelado de machine learning (por ejemplo, codificación one-hot de las variables categóricas restantes, escalado de características).
*   Construir y evaluar modelos de predicción de evasión.
*   Identificar las características más importantes para la predicción de evasión.
*   Desarrollar e implementar un plan de acción integral basado en los resultados del modelo para reducir la evasión.
