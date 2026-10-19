# 📊 Análisis de Riesgo Operativo: Desviación y Fraude en el Programa de Fidelización (App-POS)
**Código del Documento:** R-RISK-FID-001  
**Versión:** 1.1  
**Clasificación:** Uso Interno  

---

## 1. Objetivo y Metodología
El propósito de este documento es evaluar y cuantificar el impacto operativo y financiero derivado de la desviación manual de transacciones comerciales hacia cuentas anónimas o personales en el programa de puntos. El análisis se fundamenta metodológicamente en las directrices de la norma **ISO/IEC 27005:2022** y los criterios de gestión de riesgos lógicos.

## 2. Identificación del Activo y la Amenaza
*   **Activo a Proteger:** Integridad de los datos analíticos de negocio, control de inventario de producto y sostenibilidad financiera del programa de recompensas (*Coffee Card*).
*   **Amenaza:** Fraude por elusión de controles lógicos. Aprovechamiento de ventas de clientes no registrados para acumular sellos de forma manual en cuentas fantasma o perfiles de la plantilla. Esto elude el canal oficial de beneficio al empleado (`EMPLEADOS20` con 20% de descuento) y genera saldos ilegítimos de hasta 100€ en producto real.

---

## 3. Análisis de Impacto y Generación de Pasivo Financiero

El fraude no genera un descuadre inmediato en la caja diaria (el producto inicial se cobra al cliente), sino que inyecta un **riesgo financiero diferido** y una alteración de datos críticos:

### A. Impacto Económico Directo (Canje de Producto)
*   **Generación de Pasivo Oculto:** Al acumular saldos acumulativos de 100€ o decenas de cafés gratuitos de forma no legítima, la central de Madrid adquiere una deuda en producto con cuentas fantasma. 
*   **Pérdida en el Momento del Canje:** Cuando el saldo acumulado se ejecuta, la empresa sufre una pérdida directa del coste de materia prima (café de especialidad, bakery) y anula el margen de beneficio de transacciones futuras que deberían ser cobradas.

### B. Impacto en la Gobernanza de Datos (Data Integrity)
*   **Corrupción de Métricas de Negocio:** El desvío de tickets inyecta datos falsos en el POS. El sistema registra patrones de compra hiperactivos inexistentes, invalidando las analíticas de marketing, previsiones de stock y algoritmos de fidelización de la compañía.
*   **Quiebra del Control de Beneficios Internos:** La elusión del código de descuento oficial nominal para empleados (`EMPLEADOS20`) impide a la dirección monitorizar el uso correcto de los incentivos laborales aprobados.

---

## 4. Matriz de Control Lógico y Mitigación de Riesgos

Para solventar esta brecha sin aplicar restricciones que penalicen la experiencia del cliente (CX), se establecen los siguientes controles en el software:

### 🔴 4.1. Escenario de Riesgo Inherente (Estado Actual)
*   **Vulnerabilidad:** El POS permite asociar números de teléfono de forma masiva e ilimitada sin validar patrones de comportamiento anómalos.
*   **Probabilidad:** **5 (Muy Alta).** Ocurre de forma sistemática ante la falta de controles lógicos y la alta rotación de personal.
*   **Impacto:** **3 (Moderado).** Altera la integridad de la base de datos global de la app y genera pérdidas de inventario a medio plazo en las más de 20 tiendas.

### 🟢 4.2. Escenario de Riesgo Residual (Controles Propuestos)
*   **Control Lógico 1 (Detección de Anomalías):** Implementar una regla en el servidor de la app que genere una **alerta automática y bloqueo temporal de acumulación** si una misma cuenta de cliente registra más de 3 transacciones de fidelización o escaneos QR en un periodo inferior a 12 horas en el POS.
*   **Control Lógico 2 (Validación de Cuentas):** Bloquear la generación de saldos económicos en la *Coffee Card* a perfiles que no completen una verificación obligatoria doble factor (OTP) vía SMS o correo electrónico, eliminando las cuentas anónimas sin nombre en el sistema.
*   **Riesgo Residual:** **Mitigado (Verde).** La probabilidad disminuye a 1 (Muy Baja) al estar el sistema capado lógicamente contra la acumulación masiva fraudulenta.
