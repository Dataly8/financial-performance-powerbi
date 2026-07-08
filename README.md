# Profitability Analysis, Margin Control & Pricing Optimization

End-to-end business intelligence project analyzing the financial performance of a manufacturing company, built on **SQL Server** and **Power BI**. The goal: identify which products, customers and operations create profit — and which erode it.

📊 **[Live dashboard (Power BI)](ADD-YOUR-POWERBI-LINK-HERE)** · 📖 **[Full project write-up (Notion)](https://shimmering-channel-2df.notion.site/An-lisis-de-rentabilidad-control-de-margen-y-optimizaci-n-de-pricing-35a0587b6ac480e9b2ece9b4c11d8245)**

---

## Overview

Built on the `IEBS_Manufacturing` database (Microsoft SQL Server), a practice environment simulating a metalworking company that buys materials, transforms them through production, and sells finished goods. Source data comes from a **Microsoft Dynamics NAV (Navision)** ERP: sales, purchases, products, customers, suppliers, returns and bill-of-materials.

The project builds an analytical model that turns raw transactional ERP data into a decision-support system for commercial and financial decisions.

## Technical approach

- **Data source:** SQL Server (restored from ERP backup), exploring the NAV table structure.
- **Modeling:** star schema in Power BI — fact tables (invoiced sales, purchase costs, returns) and dimensions (customers, products, suppliers, calendar, geography).
- **Transformation:** cleaning and normalization in **Power Query** (data types, nulls, date formats, key standardization, relationship validation).
- **Metrics:** centralized **DAX** measures — gross/net sales, returns, margin, margin %, return ratio, applied discounts, cost of goods sold.
- **Product segmentation:** catalog classified by `ProductID` prefix into finished, plastic, raw-material, semi-finished and electronic products (~18,600 distinct products).

## What the analysis covers

A seven-page dashboard answering concrete business questions:

1. **Executive summary** — sales, cost and margin evolution; headline KPIs.
2. **Product portfolio profitability** — descriptive view of margin, discounts and return outliers.
3. **Strategic product segmentation** — Star / Opportunity / Neutral / Problematic tiers by value creation.
4. **Customer profitability segmentation** — Premium / Opportunity / Inefficient / Problematic profiles.
5. **Customer behavior by geography** — market concentration and per-country profitability.
6. **Procurement cost analysis** — supplier concentration and cost structure.
7. **Returns impact** — economic effect of returns across segments and time.

## Key findings

- The business is profitable in aggregate (**~20% margin on €150M net sales**), but that figure hides wide dispersion: **~26% of products run a negative margin** and the *Problematic* customer segment destroys over **€10M** of value.
- **Discounts are the main driver of margin erosion** (~30% of gross sales), with some markets showing discounts above the product's value — a data anomaly flagged for commercial audit.
- **Semi-finished products are structurally unprofitable (-19.5%)** even with lower discounts than finished goods, pointing to a production-cost problem rather than a commercial-policy one.
- Procurement is **highly concentrated**: three suppliers account for over **57%** of total spend — an operational risk.

## Analytical maturity: model limitations

The most valuable part of the project. The initial margin calculation used *global purchase cost* as the reference — but many finished products have no direct purchase cost, since they're manufactured from multiple raw materials and intermediate components. This led to identifying the need to incorporate the **Bill of Materials (BOM)** table to compute true manufacturing costs and more accurate industrial margins. The project evolved from a descriptive financial dashboard toward genuine production-profitability control.

## Tools

SQL Server · Power BI · Power Query · DAX · Microsoft Dynamics NAV (data source)

## Note

The detailed project write-up and dashboard commentary are in Spanish, available in the [Notion page](https://shimmering-channel-2df.notion.site/An-lisis-de-rentabilidad-control-de-margen-y-optimizaci-n-de-pricing-35a0587b6ac480e9b2ece9b4c11d8245).

---

## Versión en español

Proyecto integral de business intelligence que analiza el desempeño financiero de una empresa manufacturera, construido sobre **SQL Server** y **Power BI**. El objetivo: identificar qué productos, clientes y operaciones generan rentabilidad y cuáles erosionan el margen.

📊 **[Dashboard en vivo (Power BI)](ADD-YOUR-POWERBI-LINK-HERE)** · 📖 **[Memoria completa del proyecto (Notion)](https://shimmering-channel-2df.notion.site/An-lisis-de-rentabilidad-control-de-margen-y-optimizaci-n-de-pricing-35a0587b6ac480e9b2ece9b4c11d8245)**

### Resumen

Construido sobre la base de datos `IEBS_Manufacturing` (Microsoft SQL Server), un entorno de práctica que simula una empresa metalúrgica que compra materiales, los transforma mediante producción y vende productos elaborados. Los datos proceden de un ERP **Microsoft Dynamics NAV (Navision)**: ventas, compras, productos, clientes, proveedores, devoluciones y estructura de fabricación.

### Enfoque técnico

- **Origen:** SQL Server (restaurado desde backup del ERP), explorando la estructura de tablas de NAV.
- **Modelado:** esquema en estrella en Power BI — tablas de hechos (ventas facturadas, costes de compras, devoluciones) y dimensiones (clientes, productos, proveedores, calendario, geografía).
- **Transformación:** limpieza y normalización en **Power Query** (tipos de datos, nulos, formatos de fecha, estandarización de claves, validación de relaciones).
- **Métricas:** medidas **DAX** centralizadas — ventas brutas/netas, devoluciones, margen, % margen, ratio de devoluciones, descuentos aplicados, coste de ventas.
- **Segmentación de productos:** catálogo clasificado por prefijo de `ProductID` en elaborados, plásticos, materias primas, semi-elaborados y dispositivos electrónicos (~18.600 productos distintos).

### Qué cubre el análisis

Cuadro de mando de siete páginas que responde a preguntas de negocio concretas:

1. **Enfoque ejecutivo** — evolución de ventas, costes y márgenes; KPIs principales.
2. **Rentabilidad del portafolio de productos** — visión descriptiva de margen, descuentos y outliers en devoluciones.
3. **Segmentación estratégica de productos** — niveles Estrella / Oportunidad / Neutro / Problemático según creación de valor.
4. **Segmentación de clientes por rentabilidad** — perfiles Premium / Oportunidad / Ineficiente / Problemático.
5. **Comportamiento de clientes por geografía** — concentración de mercado y rentabilidad por país.
6. **Análisis de costes de compras** — concentración de proveedores y estructura de costes.
7. **Impacto de las devoluciones** — efecto económico de las devoluciones por segmento y en el tiempo.

### Hallazgos clave

- El negocio es rentable en agregado (**~20% de margen sobre 150M€ de ventas netas**), pero esa cifra esconde una dispersión amplia: **~26% de los productos opera con margen negativo** y el segmento de clientes *Problemáticos* destruye más de **10M€** de valor.
- Los **descuentos son el principal factor de erosión del margen** (~30% sobre ventas brutas), con mercados donde superan el valor del producto — una anomalía de datos señalada para auditoría comercial.
- Los **semi-elaborados son estructuralmente no rentables (-19,5%)** incluso con descuentos menores que los elaborados, lo que apunta a un problema de coste de producción y no de política comercial.
- El aprovisionamiento está **muy concentrado**: tres proveedores acumulan más del **57%** del gasto total — un riesgo operativo.

### Madurez analítica: limitaciones del modelo

La parte más valiosa del proyecto. El cálculo inicial del margen usaba el *coste de compras global* como referencia, pero muchos productos elaborados no tienen coste de compra directo, ya que se fabrican a partir de múltiples materias primas y componentes intermedios. Esto llevó a identificar la necesidad de incorporar la tabla **BOM (Bill of Materials)** para calcular costes reales de fabricación y márgenes industriales más precisos. El proyecto evolucionó desde un dashboard financiero descriptivo hacia un control real de rentabilidad productiva.

### Herramientas

SQL Server · Power BI · Power Query · DAX · Microsoft Dynamics NAV (origen de datos)

## 📸 Dashboard
<img width="750" height="400" alt="1  Visió General del Desempeño Financiero" src="https://github.com/user-attachments/assets/98736987-6aeb-48fd-9cac-9ae2d0a45727" 
/>

<img width="750" height="400" alt="2  Análisis Descriptivo de Rentabilidad de Productos" src="https://github.com/user-attachments/assets/ab8b4b9c-5523-4bc6-9519-e7027e6c9a75" 
/>

<img width="750" height="400" alt="3  Segmentación del Portafolio de Productos" src="https://github.com/user-attachments/assets/ff5a86a0-2a62-48bc-a692-8b5145799209" 
/>

<img width="750" height="400" alt="4  Análisis de Rentabilidad y Segmentación de Clientes" src="https://github.com/user-attachments/assets/18f2cb43-3c9a-4cc5-b124-88a23cfac926" 
/>

<img width="750" height="400" alt="5  Análisis del Comportamiento de Clientes por Geografía" src="https://github.com/user-attachments/assets/170d85a7-ea0f-4f87-a59f-f525958c94fa" 
/>

<img width="750" height="400" alt="6  Análisis de Compras y Variación de Costes de Suministros" src="https://github.com/user-attachments/assets/ce8df0d7-5a45-4541-a33d-2b6def3f52fb" 
/>

<img width="750" height="400" alt="7  Análisis del Impacto de las Devoluciones" src="https://github.com/user-attachments/assets/e5b73f9a-af0e-4b1f-ad2e-e34b3d839112" 
/>

