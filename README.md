#📄Informe final

**Introducción**

El objetivo de este análisis es explorar los datos de TelecomX para identificar los factores que contribuyen a la pérdida de clientes (Churn). Comprender por qué los clientes cancelan el servicio es crucial para desarrollar estrategias efectivas de retención y mejorar la rentabilidad de la empresa. Este informe presenta los hallazgos clave del análisis y sugiere acciones para reducir perdidas.

**Limpieza y Tratamiento de Datos**

Se cargaron los datos desde un archivo JSON y se convirtieron a un DataFrame de pandas. Se utilizó la función `json_normalize` para aplanar la estructura anidada del JSON.

Se realizaron las siguientes verificaciones y tratamientos:

- **Valores únicos:** Se verificó el número de valores únicos en cada columna para entender la cardinalidad de los datos.
- **Duplicados:** Se comprobó que no existen filas duplicadas.
- **Espacios vacíos:** Se buscó columnas con espacios vacíos, identificando que la columna 'account.Charges.Total' contenía valores que eran espacios en blanco y se eliminaron las filas correspondientes.
- **Conversión de tipo de dato:** La columna 'account.Charges.Total' fue convertida a tipo numérico (`float64`) utilizando `pd.to_numeric` con `errors='coerce'` para manejar posibles errores durante la conversión.
- **Creación de nueva columna:** Se creó la columna 'Cuentas_Diarias' para obtener el valor mensual.

**Análisis Exploratorio de Datos**

Se realizaron varios análisis exploratorios para identificar patrones y comprender los factores que influyen en el Churn:

- **Proporción de Churn:** Un gráfico de pastel mostró la proporción de clientes que se han dado de baja en comparación con los que no.
- **Churn por Género y Ciudadano Senior:** Los histogramas mostraron la distribución del Churn en relación con el género y si el cliente es un ciudadano senior. No se observaron diferencias significativas en la tasa de Churn entre géneros, pero los ciudadanos senior mostraron una mayor propensión a la pérdida de clientes.
- **Churn por Tenure:** Un histograma y un gráfico de línea mostraron la tasa de Churn en función del tiempo que el cliente ha sido un cliente (tenure). Se observó que los clientes con menor tenure tienen una tasa de Churn significativamente mayor.
- **Tenure vs. Cargos Mensuales por Churn:** Un gráfico de dispersión exploró la relación entre el tenure, los cargos mensuales y el Churn. Se observó una tendencia de mayores cargos mensuales para los clientes que se dan de baja, especialmente en los primeros meses.
- **Churn por Tipo de Contrato:** Un histograma mostró la distribución del Churn según el tipo de contrato. Los clientes con contratos mes a mes tienen una tasa de Churn mucho mayor que aquellos con contratos a largo plazo.
- **Churn por Cargos Mensuales:** Un diagrama de caja comparó la distribución de los cargos mensuales para los clientes que se dan de baja y los que no. Se confirmó que los clientes que se dan de baja tienden a tener cargos mensuales más altos.
- **Churn por Servicio Telefónico y de Internet:** Los histogramas mostraron la distribución del Churn en relación con el servicio telefónico y el tipo de servicio de internet. Los clientes con servicio de internet de fibra óptica tienen una tasa de Churn más alta.
- **Churn por Streaming TV y Método de Pago:** Los histogramas mostraron la distribución del Churn en relación con el servicio de Streaming TV y el método de pago. El método de pago con cheque electrónico se asoció con una mayor tasa de Churn.

**Conclusiones y recomendaciones**

En base en el análisis, algunas sugerencias estratégicas para reducir la pérdida de clientes pueden ser:

*   **Enfocarse en los nuevos clientes:** La tasa de pérdida de clientes es mayor durante los primeros meses. Ofrecer incentivos o soporte especializado a los nuevos clientes para mejorar su experiencia y animarlos a quedarse.
*   **Abordar los problemas con el servicio de internet de fibra óptica:** Los clientes con internet de fibra óptica tienen una mayor tasa de pérdida de clientes. Investigar las razones y trabajar para mejorar la calidad del servicio o brindar un mejor soporte a estos clientes.
*   **Fomentar los contratos a largo plazo:** Los clientes con contratos mensuales tienen una tasa de pérdida de clientes significativamente mayor en comparación con aquellos con contratos de uno o dos años. Anime a los clientes a cambiar a contratos a largo plazo ofreciendo descuentos u otros beneficios.
*   **Revise las tarifas mensuales:** El diagrama de caja muestra que los clientes que se dan de baja tienden a tener tarifas mensuales más altas. Analice la estructura de precios y considere ofrecer planes más flexibles o descuentos a los clientes con facturas mensuales elevadas, especialmente a aquellos con contratos mensuales.
*   **Mejore la experiencia con el método de pago con cheque electrónico:** Investigar si existen problemas o inconvenientes asociados con este método de pago y trabajar para mejorar la experiencia del usuario.
*   **Dirigirse a personas mayores:** Estas personas tienen una mayor tasa de abandono. Desarrolle estrategias de comunicación personalizadas o paquetes de servicios que se adapten a sus necesidades y preferencias específicas.