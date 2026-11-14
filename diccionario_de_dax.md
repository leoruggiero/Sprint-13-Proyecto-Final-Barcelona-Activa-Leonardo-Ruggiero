# Diccionario de Fórmulas DAX
**Proyecto Final Data Analytics: Del Hueso a la Pantalla**
**Autor:** Leonardo Ruggiero

Este documento detalla las principales medidas DAX (Data Analysis Expressions) construidas en Power BI para el análisis del mercado financiero del juego online y su impacto clínico en España.

## 1. Métricas Financieras Base (DGOJ)

**GGR Total (Gross Gaming Revenue)**
Beneficio neto de las casas de apuestas (Pérdidas reales de los jugadores).
```dax
GGR_Total = SUM(Fact_MercadoFinanceiro[ggr])
```

**Total Jugado (Volumen de Apuestas)**
Suma de todo el dinero apostado, incluyendo depósitos y dinero reciclado.
```dax
Total_Jugado = SUM(Fact_MercadoFinanceiro[cantidades_jugadas])
```

**Depósitos Totales**
Dinero real inyectado a las plataformas desde cuentas bancarias.
```dax
Depositos_Totales = SUM(Fact_MercadoFinanceiro[depósitos])
```

**Retiradas Totales**
Dinero real que los jugadores lograron sacar de la plataforma hacia sus cuentas.
```dax
Retiradas_Totales = SUM(Fact_MercadoFinanceiro[retiradas])
```

**Inversión en Marketing**
Gasto total de las operadoras en publicidad, bonos y patrocinios.
```dax
Total_Marketing = SUM(Fact_MercadoFinanceiro[gastos_promocion])
```

## 2. Métricas de Impacto y Comportamiento (KPIs Clave)

**Volumen Re-apostado (La Ilusión / Dinero Reciclado)**
Métrica calculada para demostrar la cantidad de dinero virtual que se vuelve a apostar constantemente dentro del ecosistema cerrado de la plataforma. Representa la diferencia entre el volumen total de jugadas y el dinero real depositado.
```dax
Dinero_Reciclado = [Total_Jugado] - [Depositos_Totales]
```

**Depósitos Netos Acumulados (Pérdida Real de Capital)**
Dinero que entró en las plataformas y nunca volvió a los jugadores (indicador que cuadra con el GGR).
```dax
Depositos_Netos = [Depositos_Totales] - [Retiradas_Totales]
```

**Crecimiento del GGR (%)**
Calcula la evolución porcentual del mercado desde el inicio de la serie histórica.
```dax
Crecimiento_GGR_Hist = 
VAR GGR_Inicial = CALCULATE([GGR_Total], Dim_Calendario[ano] == 2013)
VAR GGR_Final = CALCULATE([GGR_Total], Dim_Calendario[ano] == 2025)
RETURN
DIVIDE(GGR_Final - GGR_Inicial, GGR_Inicial, 0)
```

## 3. Métricas Clínicas (Estudio 2016)

*(Nota: Al estar el modelo basado en valores booleanos transformados en el proceso ETL de Python, las medidas cuentan la incidencia clínica sobre la muestra de 512 pacientes).*

**Tasa de Ansiedad Clínica**
```dax
%_Ansiedad = 
DIVIDE(
    CALCULATE(COUNTROWS(Fact_EstudioClinico), Fact_EstudioClinico[atual_ansiedade] == "Sí"),
    COUNTROWS(Fact_EstudioClinico),
    0
)
```

**Tasa de Depresión**
```dax
%_Depresion = 
DIVIDE(
    CALCULATE(COUNTROWS(Fact_EstudioClinico), Fact_EstudioClinico[atual_depressao] == "Sí"),
    COUNTROWS(Fact_EstudioClinico),
    0
)
```

**Pacientes con Deudas de Juego**
```dax
%_Pacientes_Deudas = 
DIVIDE(
    CALCULATE(COUNTROWS(Fact_EstudioClinico), Fact_EstudioClinico[tiene_deudas_juego_actuales] == "Sí"),
    COUNTROWS(Fact_EstudioClinico),
    0
)
```