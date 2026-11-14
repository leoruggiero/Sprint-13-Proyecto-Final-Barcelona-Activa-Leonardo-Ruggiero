Del Hueso a la Pantalla: La Anatomía Económica y Social del Juego en España

Descripción del Proyecto

Proyecto Final del Bootcamp de Data Analytics (IT Academy). Este estudio realiza un análisis profundo sobre la evolución del mercado de apuestas y juego online en España (2013-2025). A través del cruce de datos financieros oficiales y estudios epidemiológicos, el proyecto desmitifica el volumen bruto del juego para exponer el verdadero coste extraído de la sociedad (Gross Gaming Revenue - GGR) y su impacto clínico directo en los usuarios.

Principales Hallazgos

Crecimiento del Mercado: Se registra un aumento histórico del +642% en el GGR, alcanzando más de 11.200 millones de euros en pérdidas reales para las familias españolas a lo largo de la serie analizada.

Dinero Reciclado (La Ilusión Matemática): De un total de 33.600 M€ en depósitos reales, la plataforma generó un volumen de apuestas de 289.000 M€. La diferencia (aprox. 256.000 M€) evidencia un ecosistema diseñado para la re-apuesta continua, basado en la retención del capital y la fricción cero.

Impacto Clínico: El cruce con la matriz de pacientes revela tasas críticas de comorbilidad psiquiátrica. El 68% de los pacientes diagnosticados sufren ansiedad clínica, el 54% depresión, y el 34% presentan deudas acumuladas derivadas de su actividad en las plataformas.

Políticas Públicas: El análisis de dispersión demuestra que la regulación publicitaria (Decreto Garzón 2021) frenó la adquisición masiva de cuentas, pero resulta insuficiente ante la base de usuarios ya captada y el actual modelo de retención.

Tecnologías y Metodología

Extracción y Transformación (ETL): Desarrollo en Python (pandas, numpy, glob, os). Limpieza de registros gubernamentales, estandarización, manejo de valores nulos, categorización binaria de variables clínicas y creación de un esquema en estrella (Star Schema).

Modelado y Visualización: Microsoft Power BI. Diseño de modelo relacional, cálculo de KPIs, inteligencia de tiempo (Time Intelligence) y creación de métricas DAX avanzadas.

Narrativa de Datos (Data Storytelling): Construcción de reportes enfocados en la dualidad entre el rendimiento del mercado y el impacto en salud pública.

Estructura del Repositorio

├── 01_Datos/
│   └── Modelo_Datos_Proyecto_Final_Corrigido.xlsx   # Dataset final limpio (Star Schema)
├── 02_Dashboard_PowerBI/
│   ├── ProyectoFinal_LeonardoRuggiero.pbix          # Archivo fuente de Power BI
│   ├── Dashboard_Exportado.pdf                      # Exportación visual del panel
│   └── Diccionario_Formulas_DAX.md                  # Documentación de métricas DAX
├── 03_Documentacion_Cientifica/
│   └── Informe_Cientifico_ProyectoFinal.pdf         # Memoria final (Normas APA)
├── 04_Presentacion/
│   ├── Presentacion_Defensa.pdf                     # Slides de la defensa (Pitch)
│   └── Presentacion_Defensa.pptx
├── 05_ETL_Scripts/
│   └── ETL_PROYECTO_Leonardo.ipynb                  # Notebook de Python con el proceso ETL
└── README.md


Fuentes de Datos

DGOJ (Dirección General de Ordenación del Juego): Informes históricos del mercado financiero de juego online estatal (2013-2025).

OEDA (Observatorio Español de las Drogas y las Adicciones): Datos epidemiológicos sobre prevalencia de juego.

Estudio Clínico (DGOJ, 2016): Matriz de datos clínicos de factores de riesgo con muestra de 512 pacientes reales.

Autor

Leonardo Ruggiero
Analista de Datos

