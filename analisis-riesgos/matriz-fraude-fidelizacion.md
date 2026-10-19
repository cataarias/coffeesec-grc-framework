# 📊 Análisis de Impacto Económico y Matriz de Riesgos: Fraude en el Sistema de Fidelización
**Código del Documento:** R-RISK-FID-001  
**Versión:** 1.0  
**Clasificación:** Uso Interno  

---

## 1. Objetivo y Metodología
El propósito de este documento es evaluar y cuantificar económicamente el riesgo de fraude operativo interno detectado en el ecosistema POS-App de la organización. El análisis se fundamenta metodológicamente en las directrices de la norma **ISO/IEC 27005:2022** y los criterios de cálculo de impacto financiero de **MAGERIT v3**.

## 2. Identificación del Activo y la Amenaza
*   **Activo a Proteger:** Reputación de marca, base de datos de usuarios de la aplicación móvil e inventario físico de producto comercializable (Café de especialidad, Bakery, Retail).
*   **Amenaza:** Fraude interno por elusión de controles lógicos (Apropiación indebida de transacciones de clientes no registrados para inflar cuentas anónimas o perfiles personales de la plantilla y canjear saldo en producto gratuito o "Coffee Cards" de hasta 100€).

---

## 3. Cuantificación Financiera del Impacto (Escenario Estimado)

Para justificar la inversión en los controles informáticos ante la junta directiva en la central de Madrid, se realiza una estimación matemática del coste del fraude basada en los precios de carta reales y un modelo de expansión de 20 locales comerciales en territorio nacional:

### A. Parámetros de Cálculo por Punto de Venta (Tienda / Takeaway)
*   **Coste medio por producto defraudado (Café/Bakery básica):** 3,50 € *(Gama de precios observada: 2,90 € a 4,20 €)*.
*   **Volumen estimado de desvío fraudulento:** 3 productos diarios por tienda (debido a la alta rotación de personal y uso de usuarios de caja compartidos).
*   **Pérdida diaria por tienda:** 3 productos × 3,50 € = **10,50 € / día**.

### B. Impacto Financiero Global Anualizado (20 Tiendas)
*   **Pérdida diaria de la cadena:** 10,50 € × 20 locales = **210 € / día**.
*   **Pérdida mensual de la cadena:** 210 € × 30 días = **6.300 € / mes**.
*   **Impacto Económico Anual Directo (Pérdida en inventario):** 210 € × 365 días = **76.650 € / año**.

*Nota de Auditoría:* Este cálculo contempla únicamente la pérdida directa en producto estándar de barra (café y bakery). No incluye el riesgo de pérdida por desviación en productos de mayor valor como bolsas de café retail (16 € - 29 €) o equipamiento (cafeteras/molinos) si las credenciales compartidas del POS permiten alterar inventarios globales sin trazabilidad nominal.

---

## 4. Matriz de Riesgo Inherente vs. Riesgo Residual

Siguiendo la lógica de **MAGERIT v3**, medimos el riesgo multiplicando la **Probabilidad (1 a 5)** por el **Impacto Financiero (1 a 5)**.

### 🔴 4.1. Estado Actual (Riesgo Inherente - Sin Controles)
*   **Vulnerabilidad operativa:** Búsquedas parciales permitidas en el POS, campos anónimos en la app ("C. A."), ausencia de validación (SMS/Email) y contraseñas compartidas escritas en las tablets.
*   **Probabilidad:** **5 (Muy Alta)**. Ocurre de forma continua en los turnos diarios debido a la alta rotación de personal.
*   **Impacto:** **3 (Moderado)**. Pérdida financiera directa acumulada superior a 75.000 € anuales.
*   **Valor del Riesgo Inherente:** 5 × 3 = **15 (Riesgo Crítico / Rojo)**. Requiere intervención inmediata de la central.

### 🟢 4.2. Estado Deseado (Riesgo Residual - Con Controles de GRC Aplicados)
*   **Controles aplicados:** Implementación obligatoria de cuentas nominales temporales, bloqueo de consultas parciales en base de datos y validación OTP por SMS/Email para activar la acumulación de la App.
*   **Probabilidad:** **1 (Muy Baja)**. El sistema informático impide de forma lógica el desvío manual de puntos.
*   **Impacto:** **2 (Bajo)**. El fraude potencial se reduce a casos aislados e identificables nominalmente en los registros (*logs*).
*   **Valor del Riesgo Residual:** 1 × 2 = **2 (Riesgo Aceptable / Verde)**. El riesgo queda mitigado y bajo control del negocio.

