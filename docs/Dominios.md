# Análisis de Dominios Funcionales (Punto 4.1)

El modelo de base de datos presenta una clara separación en 12 dominios funcionales, lo que permite organizar las entidades según su responsabilidad dentro del sistema. A continuación, se describe cada dominio junto con sus entidades principales y relaciones clave.

---

## 1. Geografía y datos de referencia

**Descripción:**  
Este dominio gestiona la información geográfica y de referencia utilizada en todo el sistema, como ubicaciones, zonas horarias y monedas.

**Entidades principales:**  
- country  
- city  
- address  
- currency  

**Relaciones clave:**  
- Un país pertenece a un continente  
- Una ciudad pertenece a un estado/provincia  
- Una dirección pertenece a un distrito  
- Las direcciones son utilizadas por aeropuertos y proveedores  

---

## 2. Aerolínea

**Descripción:**  
Gestiona la información básica de las aerolíneas.

**Entidades principales:**  
- airline  

**Relaciones clave:**  
- Una aerolínea pertenece a un país  
- Una aerolínea opera vuelos, aeronaves y programas de fidelización  

---

## 3. Identidad

**Descripción:**  
Administra la información personal de los usuarios y clientes del sistema.

**Entidades principales:**  
- person  
- person_document  
- person_contact  

**Relaciones clave:**  
- Una persona puede tener múltiples documentos  
- Una persona puede tener múltiples contactos  
- Una persona puede convertirse en cliente o usuario del sistema  

---

## 4. Seguridad

**Descripción:**  
Controla el acceso al sistema mediante usuarios, roles y permisos.

**Entidades principales:**  
- user_account  
- security_role  
- security_permission  

**Relaciones clave:**  
- Un usuario está asociado a una persona  
- Un usuario puede tener múltiples roles  
- Un rol tiene múltiples permisos  

---

## 5. Clientes y fidelización

**Descripción:**  
Gestiona los clientes y sus beneficios dentro de programas de fidelización.

**Entidades principales:**  
- customer  
- loyalty_account  
- loyalty_program  

**Relaciones clave:**  
- Un cliente pertenece a una aerolínea  
- Un cliente tiene cuentas de fidelización  
- Una cuenta acumula millas mediante transacciones  

---

## 6. Aeropuerto

**Descripción:**  
Administra la infraestructura aeroportuaria.

**Entidades principales:**  
- airport  
- terminal  
- boarding_gate  

**Relaciones clave:**  
- Un aeropuerto tiene múltiples terminales  
- Un terminal tiene múltiples puertas de embarque  
- Un aeropuerto tiene pistas (runway)  

---

## 7. Aeronaves

**Descripción:**  
Gestiona los aviones, su estructura interna y mantenimiento.

**Entidades principales:**  
- aircraft  
- aircraft_model  
- aircraft_seat  

**Relaciones clave:**  
- Una aeronave pertenece a una aerolínea  
- Una aeronave tiene cabinas y asientos  
- Una aeronave tiene eventos de mantenimiento  

---

## 8. Operaciones de vuelo

**Descripción:**  
Gestiona los vuelos y su ejecución.

**Entidades principales:**  
- flight  
- flight_segment  
- flight_status  

**Relaciones clave:**  
- Un vuelo tiene múltiples segmentos  
- Cada segmento conecta aeropuertos  
- Un vuelo tiene un estado (retrasado, activo, etc.)  

---

## 9. Ventas y reservas

**Descripción:**  
Gestiona el proceso de compra de tiquetes.

**Entidades principales:**  
- reservation  
- ticket  
- ticket_segment  

**Relaciones clave:**  
- Una reserva puede tener múltiples pasajeros  
- Un ticket pertenece a una venta  
- Un ticket se divide en segmentos de vuelo  

---

## 10. Abordaje

**Descripción:**  
Controla el proceso de check-in y embarque.

**Entidades principales:**  
- check_in  
- boarding_pass  
- boarding_validation  

**Relaciones clave:**  
- Un check-in está asociado a un ticket  
- Un boarding pass se genera desde un check-in  
- El boarding pass es validado en la puerta  

---

## 11. Pagos

**Descripción:**  
Gestiona los pagos realizados por los clientes.

**Entidades principales:**  
- payment  
- payment_transaction  

**Relaciones clave:**  
- Un pago está asociado a una venta  
- Un pago puede tener múltiples transacciones  

---

## 12. Facturación

**Descripción:**  
Gestiona la generación de facturas y cálculo de impuestos.

**Entidades principales:**  
- invoice  
- invoice_line  
- tax  

**Relaciones clave:**  
- Una factura pertenece a una venta  
- Una factura tiene múltiples líneas  
- Cada línea puede tener impuestos asociados  

---

## Conclusión

El modelo presenta una adecuada separación en dominios funcionales, lo que facilita su mantenimiento, escalabilidad y comprensión. Cada dominio encapsula responsabilidades específicas y se relaciona con otros mediante claves foráneas, garantizando la integridad referencial del sistema.