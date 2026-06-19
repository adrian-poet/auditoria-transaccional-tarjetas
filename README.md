Markdown
# Auditoría Transaccional y Comportamiento en Tarjetas de Crédito 💳📊

## Enfoque: Optimización Operacional, Mitigación de Fuga (Churn) y Análisis Dimensional de Consumo con Inversión Cero

---

## 🎯 Objetivo del Proyecto
Realizar un diagnóstico integral y multidimensional del ecosistema transaccional de "Tarjeta X" mediante ingeniería de datos y metodologías avanzadas de Business Intelligence. El análisis audita el comportamiento temporal de los usuarios, segmenta la cartera mediante criterios de Pareto (ABC) y correlaciona variables críticas para dotar a la dirección de **alertas tempranas de fuga (churn)** y **optimizar decisiones de financiación sin costos adicionales de software**.

Para conocer todos los detalles metodológicos y la presentación ejecutiva, puedes consultar el documento principal de este repositorio:  
📄 **[Ver Informe Completo en PDF](AUDITOR%C3%8DA%20TRANSACCIONAL%20Y%20COMPORTAMIENTO%20EN%20TARJETAS%20DE%20CR%C3%89DITO.pdf)**

---

## 🛠️ Tecnologías y Herramientas Utilizadas
* **Python** (Pandas, NumPy) - Procesamiento, limpieza y feature engineering.
* **Jupyter Notebook** - Entorno de desarrollo analítico.
* **Metodologías:** Segmentación de Pareto (ABC), Análisis de Estacionalidad Temporal, Análisis de Frecuencia e Intensidad de Compra.

---

## 🧠 Procesamiento de Datos y "Olfato Analítico"
Al calcular la frecuencia de compra aplicando la función lógica tradicional `shift(1)` sobre las fechas crudas, se detectó una **distorsión crítica**: la presencia de múltiples transacciones de un mismo usuario en un único día (e.g., consumos recurrentes en cafeterías o nafta). Dejar estos valores en cero pulverizaba artificialmente la media de frecuencia, alterando la lógica del negocio.

Para resolverlo, el dataset final se consolidó desde **tres aristas analíticas**:
1. **Frecuencia de Compra:** Limpieza temporal eliminando duplicados por día para aislar "días de actividad unívocos" y calcular métricas de desvío temporal.
2. **Intensidad de Compra:** Agrupación por cliente y fecha aplicando `size()` para mapear el promedio de consumos diarios.
3. **Análisis Económico:** Cálculo de montos totales, ticket promedio y aplicación de **Pareto ABC** sobre la recaudación.

---

## 📈 Hallazgos Clave

### 👥 Análisis de Clientes y Alertas de Churn
* **Alerta Roja de Fuga (Caso Camila Gómez):** Identificada en el segmento de valor medio (B). Su ciclo histórico de uso es de 2.67 días; sin embargo, al momento del análisis registra **12 días de inactividad** (un desvío crítico de +9.33 días por encima de su promedio). Representa una fuga silenciosa en proceso.
* **Validación de Ciclo Real (Caso Gustavo Peralta):** Opera con un promedio de 1.92 compras diarias. La remoción metodológica de duplicados permitió establecer su ciclo real en 2.27 días, evitando falsas alarmas de hiperactividad.
* **Potencial de Tracción Cruzada (Caso Sofía Martínez):** Cuenta con el Ticket Promedio más alto de la muestra ($39.020,70) pero con baja frecuencia (cada 5 días). Siendo Pareto A, es la candidata ideal para campañas de *cross-selling*.

### 📅 Análisis Dimensional de la Operación

#### A. Estacionalidad Mensual
* **El "Efecto Fin de Mes":** El período **"Después del día 21"** concentra la mayor participación de dinero (**38.10% de la recaudación**) y el Ticket Promedio más alto ($26.683,93). Ante el desgaste del salario líquido, los usuarios utilizan masivamente la tarjeta como herramienta de financiamiento para compras mayores.

#### B. Matriz de Canales de Pago
* **Dominio Digital:** El canal **Online (E-Commerce)** retiene el **75.43% del dinero líquido** de la tarjeta, con un ticket promedio de $30.098,06.
* **Subexplotación:** El Débito Automático representa apenas el **1.31% de los ingresos**, evidenciando una oportunidad perdida para la fidelización fija.

#### C. Desempeño por Categoría: El "Espejismo Transaccional"
* **Cafetería vs. Smartphones:** La categoría *Cafetería* lidera en volumen operacional con 19 ventas, pero aporta un marginal **2.84%** de los fondos. En contraposición, *Smartphone Cuotas*, con solo 4 transacciones, inyecta el **15.97%** del flujo económico global gracias al financiamiento en 3 cuotas.

---

## 🚀 Recomendaciones Estratégicas

1. **Disparador Automático de Churn:** Configurar alertas en el CRM cuando una cuenta Pareto A o B triplique su ventana de inactividad histórica (Caso Camila Gómez) para activar retención personalizada de forma proactiva.
2. **Campañas de Financiación Segmentadas:** Implementar alianzas de E-Commerce para ofrecer el *Plan 3 cuotas sin interés* en tecnología y compras mayoristas específicamente después del día 21, maximizando la captura de transacciones premium.
3. **Migración a Débito Automático:** Diseñar campañas de marketing de bajo costo para adherir servicios fijos en usuarios de alta frecuencia diaria (combustible, consumo cotidiano), elevando el piso actual de recaudación recurrentes (1.31%).

---

## 💻 Código Fuente
El desarrollo completo de la vista analítica con el script optimizado se encuentra documentado y listo para su ejecución en la sección de archivos del repositorio:

* 💾 **[Ver Trabajo Completo](./Tarjeta Credito X.ipynb)**

---
## 👤 Autor
* **Adrián Poet** - *Data Analyst & Business Intelligence Specialist*
* [LinkedIn](https://www.linkedin.com/in/adrian-poet)
