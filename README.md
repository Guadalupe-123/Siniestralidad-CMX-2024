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

- **Incidentes totales 2024:** <total> · **Tasa por 100k hab.:** <tasa>
- **Severidad:** lesionados <n> · fallecidos <n> · índice de severidad <valor>
- **Horas pico:** % en 7–10h: <x>% · % en 17–20h: <y>%
- **Alcaldías (Top 5 por casos/tasa):** <A>, <B>, <C>, <D>, <E>
- **Tipos de evento (Pareto):** <tipo1> <p1>% · <tipo2> <p2>% · <tipo3> <p3>%

> Tip: estos valores salen directo de `kpi_*` y `ranking_alcaldia.csv`.

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
