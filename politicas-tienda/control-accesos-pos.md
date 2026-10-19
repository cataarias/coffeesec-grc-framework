# 📋 Política de Control de Accesos y Credenciales en el Punto de Venta (POS)
**Código del Documento:** P-SEC-POS-001  
**Versión:** 1.0  
**Clasificación:** Uso Interno  

---

## 1. Objetivo
Regular el uso de las credenciales de acceso, la gestión de identidades temporales y el comportamiento de los terminales de Punto de Venta (POS) y tablets en las tiendas de la organización. El fin es mitigar el fraude interno, garantizar el principio de no repudio y asegurar el cumplimiento de los estándares de seguridad de la información.

## 2. Alcance
Esta política es de **obligado cumplimiento** para todo el personal base (baristas), mandos intermedios (Head Baristas), personal de refuerzo (extras/horas complementarias) y personal técnico de la central. Aplica a todos los terminales físicos de cobro, tablets de comandas y sistemas unificados de proveedores en local.

## 3. Diagnóstico de Vulnerabilidades Actuales (Análisis de Brechas)
Tras auditorías observacionales en los puntos de venta, se han detectado los siguientes fallos de control crítico (Gaps):
*   **Quiebra de la Trazabilidad:** El uso de correos genéricos vinculados a la tienda (ej. `tienda1@eastcrema.com`) para personal de refuerzo impide la identificación inequívoca de las acciones individuales.
*   **Autenticación Débil y Predecible:** El uso de contraseñas basadas en el código postal de la ubicación física expone el sistema a intrusiones por parte de terceros ajenos a la plantilla.
*   **Exposición Visual de Credenciales:** La anotación o mantenimiento visible de contraseñas o PINs de acceso en las tablets infringe las directrices básicas de seguridad física.
*   **Sesiones Expuestas de Forma Indefinida:** La ausencia de bloqueo automático por inactividad permite que terminales con sesiones activadas queden desatendidos ante clientes o personal no autorizado.

---

## 4. Controles Obligatorios a Implementar (Normativa Interna)

### 4.1. Gestión de Identidades Nominales (Alineado con ISO/IEC 27002 Control 5.16)
1. **Prohibición de Cuentas Genéricas:** Queda terminantemente prohibido el uso de credenciales compartidas o cuentas genéricas de tienda para el registro de operaciones, cierres de caja o control de inventario.
2. **Aprovisionamiento de Usuarios Temporales:** Todo barista contratado para realizar turnos extra o complementarios debe contar con un **usuario nominal temporal** creado de forma centralizada (ej. `extra.nombre.apellido@empresa.com`).
3. **Ciclo de Vida de Cuentas Temporales:** Estas credenciales temporales caducarán y se desactivarán de forma automática en el sistema una vez finalizado el bloque de turnos asignado.

### 4.2. Robustez de la Autenticación (Alineado con ISO/IEC 27002 Control 8.5)
1. **Política de Contraseñas:** Ninguna contraseña del POS o tablet podrá contener datos públicos del local (como la dirección, el teléfono o el código postal).
2. **Acceso Rápido en Barra:** Para no ralentizar la operativa del servicio (CX), se sustituirá el tecleo de credenciales en barra por sistemas de autenticación rápidos e individuales, como códigos PIN personales e intransferibles o llaveros/pulseras RFID/NFC vinculados al perfil único de cada trabajador.

### 4.3. Política de Pantallas Limpias y Bloqueo Operativo (Alineado con ISO/IEC 27002 Control 7.7)
1.  **Bloqueo Manual Obligatorio por Ausencia:** Todo barista o encargado que deba abandonar físicamente el perímetro de la barra (ya sea para acudir al almacén, servicios, o periodos de descanso) está obligado a bloquear manualmente la sesión del terminal POS y de la tablet de comandas antes de retirarse.
2.  **Bloqueo Automático de Respaldo:** Los terminales POS y tablets se configurarán con un temporizador de bloqueo automático por inactividad de **15 minutos**. Este control actúa exclusivamente como medida de seguridad secundaria ante olvidos del personal.

---

## 5. Matriz de Permisos por Roles (Principio de Mínimo Privilegio)

| Rol del Empleado | Operatividad Diaria | Registro de Cierres | Modificación de Comandas | Eliminación de Comandas |
| :--- | :---: | :---: | :---: | :---: |
| **Barista de Plantilla** | Sí | Sí | No | No |
| **Barista Extra / Complementario** | Sí | Solo bajo supervisión | No | No |
| **Head Barista (Encargado)** | Sí | Sí | Sí | Sí |

## 6. Consecuencias del Incumplimiento
La elusión voluntaria de estos controles técnicos (tales como ceder credenciales propias, apuntar contraseñas en zonas visibles o utilizar el perfil de otro compañero) será motivo de sanción disciplinaria conforme a la legislación laboral vigente y las políticas de cumplimiento interno de la compañía.
