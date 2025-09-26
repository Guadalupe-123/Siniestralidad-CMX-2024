# Siniestralidad-CMX-2024
Proyecto de analítica aplicada a la siniestralidad vial en la Ciudad de México (2024) con un flujo
Excel → RStudio → Power BI. La base se limpia y normaliza en R (incluida la integración de población
por alcaldía para calcular tasas por 100 mil habitantes), se generan KPIs en /outputs (.csv) y se
orquesta un dashboard en Power BI (Siniestralidad-Dashboard.pbix) conectado a dichos KPIs. El repo
incluye una base consolidada en DuckDB para consultas eficientes. La estructura permite actualizar
rápido los indicadores y ofrecer lectura ejecutiva vía tablero.
# Siniestralidad-CDMX-2024 (Excel → RStudio → Power BI) — sin macros

Proyecto con flujo **Excel (base)** → **RStudio (limpieza/normalización)** → **Power BI (dashboard)**.  
Los **KPI** se publican en la carpeta `outputs/` y alimentan el dashboard.

## Estructura del proyecto

- **/outputs/**
  - `kpi_severidad.csv` — KPIs por severidad (daños, lesionados, fallecidos).
  - `kpi_alcaldia_mes.csv` — incidencia/tasa por **alcaldía × mes**.
  - `kpi_horas_pico.csv` — distribución horaria (picos AM/PM).
  - `ranking_alcaldia.csv` — ranking de alcaldías (top/bottom por casos o tasa).
  - `tipo_evento_pareto.csv` — **Pareto** por tipo de evento (choque, atropellamiento, etc.).
- `poblacion_alcaldia.xlsx` — población por alcaldía (normalización a tasa por 100k).
- `siniestralidad.duckdb` — base consolidada (consulta eficiente).
- `Siniestralidad-Dashboard.pbix` — dashboard en Power BI (resumen, severidad, horas pico, alcaldías, Pareto).

> (*Opcional*) Carpeta `src/` para scripts de R que limpian datos y generan los KPIs.

## Uso

1. **Actualizar datos**: reemplaza/añade fuentes y, si aplica, ejecuta los scripts de R para regenerar KPIs en `outputs/`.
2. **Revisar KPIs en `outputs/`**: CSV listos para conectar al dashboard.
3. **Abrir `Siniestralidad-Dashboard.pbix`** (Power BI) y **Actualizar** conexiones hacia `outputs/`.
4. Explorar páginas: **Resumen · Severidad · Horas Pico · Alcaldías · Pareto**.

## Resumen de KPIs (completa con tus cifras)

**Periodo cubierto por los datos:** 2019–2023 (último año disponible: **2023**)

**Versión ejecutiva (2023):**  
En **2023** se registraron **29,033 incidentes** con **34,024 lesionados** y **472 fallecidos**, lo que da un **índice de severidad** de **1.19** [(lesionados+fallecidos)/incidentes]. La **actividad en horas pico** concentró en promedio el **28.62%** de los eventos (máximo en **MILPA ALTA: 35.39%**). Por carga de incidentes en 2023, las alcaldías con mayor volumen fueron **CUAUHTEMOC (4,331)**, **IZTAPALAPA (4,124)**, **GUSTAVO A MADERO (3,395)**, **BENITO JUAREZ (2,272)** y **VENUSTIANO CARRANZA (2,165)**. Por **tipo de evento**, el Pareto muestra que **CHOQUE** explica **57.49%**, seguido de **DERRAPADO (19.26%)** y **ATROPELLADO (17.55%)**.

**Detalle (2023):**
- Incidentes: **29,033**  
- Lesionados: **34,024** · Fallecidos: **472**  
- Índice de severidad ( (lesionados+fallecidos)/incidentes ): **1.19**  
- Horas pico (prom. CDMX): **28.62%**  
  - Top 3 horas pico por alcaldía: **MILPA ALTA (35.39%)**, **IZTAPALAPA (33.21%)**, **MAGDALENA CONTRERAS (32.92%)**  
- Top 5 alcaldías por incidentes (2023):  
  **CUAUHTEMOC (4,331)** · **IZTAPALAPA (4,124)** · **GUSTAVO A MADERO (3,395)** · **BENITO JUAREZ (2,272)** · **VENUSTIANO CARRANZA (2,165)**
- Pareto por tipo de evento (acumulado): **CHOQUE 57.49%** · **DERRAPADO 19.26%** · **ATROPELLADO 17.55%**

**Contexto de serie (2019–2023):**  
Total acumulado **2019–2023**: **117,051 incidentes**. El índice de severidad promedio del periodo es **1.18**.

## Notas

- No se usan macros (si algún Excel es `.xlsm`, es por compatibilidad).
- Si hay datos sensibles, mantener el repo **Privado**.
- Recomendado: subir una **captura** del dashboard en `docs/` y enlazarla en “Vistas”.

## Enlaces rápidos

- 📂 **Outputs (KPI):** [/outputs](./outputs)  
- 📊 **Dashboard (PBIX):** [Siniestralidad-Dashboard.pbix](./Siniestralidad-Dashboard.pbix)  
- 🗃️ **Base consolidada:** [siniestralidad.duckdb](./siniestralidad.duckdb)  
- 👥 **Población:** [poblacion_alcaldia.xlsx](./poblacion_alcaldia.xlsx)



<!-- ![Dashboard](docs/dashboard_siniestralidad.png) -->
