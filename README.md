# TechCore — Análisis y Dashboard de Ventas

Proyecto integrador del bootcamp **DataScience** (Henry, carrera). Cubre el flujo completo de un pipeline de analítica de datos: desde la limpieza de datos crudos de ventas hasta un dashboard interactivo en Power BI, pasando por el modelado relacional en Python.

---

## 📌 Resumen del proyecto

| Avance | Herramienta |
|---|---|---|
| 1 | Power Query | Limpieza y transformación de datos crudos de ventas |
| 2 | Python + Pandas | Modelo relacional tipo copo de nieve (8 tablas) |
| 3 | Power BI | Dashboard de 4 páginas con medidas DAX |

---

## Avance 1 — ETL (Power Query)

Limpieza y transformación de los datos crudos de ventas.

**Tareas principales:**
- Renombrado de columnas a español en formato camelCase
- Conversión de tipos de datos (fechas, numéricos)
- Eliminación de duplicados
- Imputación de valores nulos
- Extracción de marca de producto con *Text Before Delimiter*
- Creación de la columna `CiudadSucursal`
- Derivación de columnas `Año`, `Mes`, `Día` a partir de la fecha de venta

---

## Avance 2 — Modelado Relacional (Python + Pandas)

Construcción de un modelo relacional tipo copo de nieve a partir de los datos limpios.

**Tablas generadas:**
`Ciudades`, `Sucursales`, `Vendedores`, `Clientes`, `MetodosPago`, `Productos`, `Facturas`, `DetalleFacturas`

**Tareas principales:**
- Reconstrucción de `FechaVenta` a partir de columnas separadas
- Loop de slots de producto para generar `DetalleFacturas`
- Validación de integridad referencial con `isin()`
- Exportación final a `modeloVentas.xlsx`

### Modelo Relacional

![Modelo Relacional TechCore](modelo_relacional.png)

---

## Avance 3 — Dashboard en Power BI

Construcción de un dashboard de 4 páginas sobre el modelo relacional, con una tabla dedicada de medidas DAX (`_Medidas`).

**Elementos clave:**
- Corrección de `CROSSFILTER` para permitir el filtrado por `MarcaProducto` sobre `VentasTotales`
- Página de KPIs Generales con: `VentasTotales`, `TicketPromedio`, `ProductosVendidos`, `MargenVentas`
- Segmentadores sincronizados de fecha y ciudad, que propagan el filtro a todas las páginas del reporte
- Visualizaciones: ventas por método de pago, ventas por año, ventas por ciudad
- Páginas adicionales con detalle de Top Productos y Top Vendedores

---

## 🛠️ Stack técnico

`Python` · `Pandas` · `Power Query` · `Power BI` · `DAX`

---

## 📂 Estructura del repositorio

```
techcore-powerbi-analytics/
├── M3_A1/                      # Avance 1 — ETL (Power Query)
│   ├── M3_A1_ventas
│   ├── ventas.xlsx
│   └── VentasTransformed.xlsx
├── M3_A2/                      # Avance 2 — Modelado relacional (Python + Pandas)
│   ├── Avance2_Modelo_Relacional
│   ├── modeloVentas.xlsx
│   └── VentasTransformed.xlsx
├── M3_A3_Dashboard.pbix         # Avance 3 — Dashboard en Power BI
├── modelo_relacional.png        # Diagrama del modelo de datos
└── README.md
```

---


