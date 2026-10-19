# 📋 Política de Emisión de Recibos y Captación de Datos Personales en Punto de Venta (POS)
**Código del Documento:** P-SEC-POS-002  
**Versión:** 1.0  
**Clasificación:** Uso Interno  

---

## 1. Objetivo
Establecer las directrices de seguridad para la gestión de transacciones comerciales, la emisión de recibos físicos o digitales y la captación de información de contacto en la barra. El fin es evitar la fuga de datos de carácter personal y garantizar que la operativa diaria en barra respete la confidencialidad de los usuarios.

## 2. Alcance
Esta política aplica a todo el personal base (baristas) y encargados (Head Baristas) que operen los terminales unificados de punto de venta (POS) y realicen la atención directa al cliente en el mostrador.

## 3. Diagnóstico de la Operativa Actual y Riesgos de Privacidad
El análisis del flujo de caja actual muestra los siguientes escenarios frente al tratamiento de información:
*   **Emisión Bajo Demanda:** Por criterios de sostenibilidad, el ticket físico en papel no se genera de forma automatizada por defecto, sino a petición expresa del consumidor.
*   **Integración por Código QR:** Los usuarios registrados en la aplicación de fidelización reciben su recibo digital de forma automatizada e integrada en su cuenta mediante el escaneo de su código QR en un solo clic.
*   **Captación Verbal Indirecta:** Para clientes que solicitan un recibo digital pero no disponen de la aplicación móvil instalada, el procedimiento actual requiere la introducción manual de un correo electrónico en el sistema.

---

## 4. Controles Obligatorios y Directrices de Trabajo (Alineado con ISO/IEC 27002)

### 4.1. Recogida de Datos de Contacto en Barra (Alineado con ISO/IEC 27002 Control 8.12)
1.  **Prohibición de Dictado a Viva Voz:** Queda terminantemente prohibido solicitar al cliente que dicte en voz alta su número de teléfono o dirección de correo electrónico en la barra de atención si existen otros consumidores en el perímetro inmediato del mostrador. Esto vulnera el principio de confidencialidad y expone al cliente a la captación de datos por parte de terceros ajenos a la organización.
2.  **Alternativa de Introducción Manual:** En caso de que un cliente no disponga del código QR de la aplicación y requiera un recibo personalizado por correo electrónico, el barista deberá orientar la tablet o pantalla del terminal hacia el cliente para que sea este quien introduzca sus datos de contacto de forma autónoma y privada.

### 4.2. Enmascaramiento de Información en Tickets Impresos (Alineado con ISO/IEC 27002 Control 8.11)
1.  **Datos Financieros:** Todo recibo impreso a petición del cliente debe ocultar los datos de la tarjeta bancaria empleada (datáfono), mostrando únicamente los últimos cuatro dígitos (ej: `**** **** **** 1234`).
2.  **Datos del Cliente:** Si el ticket se asocia a un usuario de la aplicación móvil de fidelización, el documento impreso nunca reflejará el número de teléfono completo ni el correo electrónico del titular en texto claro. El software del POS aplicará técnicas de enmascaramiento por defecto (ej: `ca*******06@gmail.com`).

### 4.3. Gestión de Tickets Físicos Descartados u Olvidados
1.  **Destrucción Inmediata:** Aquellos tickets de compra que se impriman por error o que el cliente decida dejar abandonados en la barra tras el cobro deberán ser destruidos de forma manual e inmediata por el barista. 
2.  **Prohibición de Acumulación:** Queda prohibido acumular o almacenar tickets antiguos impresos junto a la caja registradora, ya que contienen información de los flujos de facturación del local y fragmentos de datos de transacciones comerciales.
