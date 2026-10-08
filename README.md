# TechStore
Dashboard interactivo en Power BI para una cadena ficticia de tiendas de tecnología en Bolivia. Proyecto enfocado en la construcción de Dashboards y KPIs (Power BI).

<img width="2000" height="1146" alt="TechStore_Dashboard" src="https://github.com/user-attachments/assets/f3100bf5-0bbe-4537-8e5b-91ea51b2f92a" />


## Objetivo

Dar a la gerencia una vista rápida del desempeño comercial: cuánto se vende, con qué margen, en qué tiendas, categorías y productos, y cómo evoluciona mes a mes.

## KPIs

| KPI | Valor | Qué mide |
|---|---|---|
| Total Ventas | Bs 3,28 M | Ingreso bruto de todas las transacciones |
| Margen % | 40,87 % | Ganancia sobre ventas después de costos directos |
| Nro. Transacciones | 800 | Volumen de ventas realizadas |
| Ticket Promedio | Bs 4.100 | Ventas / transacciones |

## Contenido del dashboard

- 4 tarjetas KPI
- Ventas por mes (barras)
- Ventas por categoría (dona): Electrodomésticos 38,2 %, Tecnología 22,6 %, Telefonía 20,4 %, Muebles 18,8 %
- Top 5 productos por ventas y margen
- Ventas por tienda con margen y transacciones
- Segmentadores: Año, Canal de venta, Ciudad y Categoría

## Datos

Dataset sintético generado con IA (Claude, Anthropic), 2023–2024, bajo un **modelo estrella**:

| Tabla | Tipo | Registros |
|---|---|---|
| FACT_Ventas | Hechos | 800 |
| DIM_Fecha | Dimensión | 730 |
| DIM_Producto | Dimensión | 20 |
| DIM_Cliente | Dimensión | 20 |
| DIM_Vendedor | Dimensión | 6 |
| DIM_Tienda | Dimensión | 5 |

`data/TechStore.xlsx` contiene la tabla de hechos (17 columnas: cantidad, precio, descuento, ingreso, costo, margen, canal, método de pago y estado del pedido). Las dimensiones están cargadas en el modelo del `.pbix`.

> Los datos son ficticios y no representan a ninguna empresa real.

## Hallazgos

- Las ventas se reparten parejo entre 2023 (Bs 1,62 M) y 2024 (Bs 1,66 M).
- Electrodomésticos aporta casi 4 de cada 10 Bs vendidos.
- El margen es estable entre tiendas (40,0 % – 41,7 %); Miraflores lidera en ventas (Bs 749 mil).
- Marzo y septiembre son los meses más fuertes; julio el más bajo.

## Limitaciones

- Los KPIs incluyen pedidos **Cancelados** (162) y **Pendientes** (159). Solo 479 de las 800 transacciones están **Completadas** (Bs 1,92 M de ventas, margen 40,35 %). Un siguiente paso es filtrar por estado del pedido o añadirlo como segmentador.
- Dataset sintético: no hay estacionalidad ni comportamiento real de clientes.

## Estructura del repositorio

```
techstore-dashboard/
├── README.md
├── data/TechStore.xlsx
├── powerbi/TechStore_Dashboard.pbix
└── docs/
    ├── dashboard.png
    └── Brief_Proyecto_Final.pdf
```

## Cómo usarlo

1. Descargar `powerbi/TechStore_Dashboard.pbix`.
2. Abrirlo con Power BI Desktop.
3. Usar los segmentadores del encabezado para filtrar.

## Herramientas

Power BI Desktop · DAX · Modelado dimensional · Excel

## Autor

**Nicolas Rivera** — La Paz, Bolivia · [GitHub](https://github.com/nicolas-rivera-dev)
