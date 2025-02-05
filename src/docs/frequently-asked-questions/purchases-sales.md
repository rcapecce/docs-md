---
title: Compras/Ventas
category: Documentation
star: 9
sticky: 9
article: false
---

## Compras/Ventas

### ¿Cuáles son los requisitos para poder eliminar un documento?

Para eliminar un documento, la primera regla general es que no se haya utilizado el mismo en ningún otro documento. Si ya se referenció en cualquier otro registro, no se podrá borrar justamente por razones de coherencia/consistencia de la base de datos. 
 
Más allá de esto, puede ser que un documento una vez creado no permita ser borrado. En este caso se deberá inactivar el mismo o Anular.
Cabe destacar que si se trata de un documento que puede ingresar en un proceso masivo, lo ideal será anularlo (como por ejemplo un Contrato de Servicio, que pueda ingresar en la generación masiva de cuotas).

#### ¿El proceso “Reabrir Orden” existe solamente para las Órdenes de Compra/Venta?

SI, sólo existe para las Órdenes tanto de venta como de compra (en este último caso deberá encontrarse destildado el check Transacción de Ventas ).

#### ¿Cómo hago para re contabilizar un asiento?

Para re contabilizar un asiento se debe abrir el asiento desde el documento en cuestión y hacer click en el botón “Re-Contabilizar” ubidado en el extremo inferior izquierdo. 

El Período de la fecha que dicho asiento fue contabilizado debe estar ABIERTO para permitir re-contabilizar (caso contrario, se deberá abrir el mismo desde la ventana Año, Calendario y Período).

#### ¿Facturas ya pagadas se ven en el Estado de Cuenta Corriente y en Saldos pendientes?

En el estado de cuenta se ven las facturas Pagas porque muestra todos los documentos (facturas y pagos) sin filtrar si se encuentra o no pagada (no muestra los documentos con estado cerrado).
No se muestran en el reporte Saldos Pendientes justamente porque este reporte muestra solo facturas con saldo abierto o pendiente.

#### ¿En el Cierre de Caja de Punto de Venta qué muestra el campo “Diferencia Monto”?

El campo “Diferencia Monto” representa el monto resultante de la sumatoria del Monto total de la apertura más el Total cobrado menos el Total de los retiros.

### Documentos por Cobrar

**Cómo realizar un pago:**

**Forma de Pago Caja en Documentos por Cobrar**

Para poder realizar un cobro en ‘Efectivo’, cuando en el contexto no hay un POS, el tipo de documento utilizado en la orden de venta debe tener asociado una cuenta bancaria. 

Dicha cuenta bancaria será la utilizada para realizar el Pago/Cobro.

### Proceso de Facturación Masivo

#### **Controles Facturar Orden de Venta**

* Check “Permite Facturar”: Para poder facturar una orden de venta luego de completarla debe tener el check de permite facturar, y su regla de facturación debe ser inmediata.
* **Regla de Facturación “Después de Entrega”**

### Como Generar Factura desde Cuota de Contrato

  
Este proceso tomará todos los Informes de Gastos (Conceptos a Facturar) que existan creados en los contratos y generará la factura al “SDN a Facturar” que ellos tengan definido.

Importante: El proceso de Facturación, si bien en el Contrato se define un Precio de Lista, al generar la Factura el Precio de lista se define automáticamente directo desde la Versión de Lista de Precios vigente para la fecha y no la obtendrá desde la Línea del Contrato. Esto puede llevar a que si no se Actualiza correctamente los precios de las Líneas del Contrato (tanto Precio de Lista como Precio), si bien el precio si será definido según el definido en la línea y en la Cuota del Contrato (Informe de Gastos), no así el Precio de Lista, definiendo siempre el ACTUALIZADO. 
Esto puede llevar a que el % de Descuento REAL definido en la línea de La Factura quede desactualizado (ya que el Precio es el "con descuento" pero según un Precio de lista viejo, y el Precio de Lista que se defina en la factura será uno nuevo).

### Cómo generar una Nota de crédito

#### Solicitud de Nota de Crédito

La Solicitud de Notas de Crédito por parte de los usuarios a ADministración se realiza en Solop ERP mediante la creación de una Solicitud de Devolución de Cliente. Administración recepciona todas las Autorización de Devolución de Cliente para definir cuáles corresponden y si se les debe generar una Nota de Crédito sobre las cantidades definidas.

  
Para ello hay que tener creado los Tipos de Documento de “Solicitud de Devolución” donde el Usuario definirá la “Entrega” que el Cliente solicita su NC. Dicho Documento debe tener el Tipo de Documento de Recepción así como también el Tipo de Documento de Facturación (en este caso Nota de Crédito).

Luego desde la Ventana se realiza la Devolución correspondiente y desde la misma se puede generar la Nota de Crédito al Cliente en cuestión. 

#### Procedimiento para realizar una Nota de Crédito

Hay varios procesos de generar Notas de Crédito (Nota de Débito es otra cosa, es similar a una factura). 

1. Crear Desde (Orden de venta, Factura o Devolución)
2. Copiar Líneas. (Factura)
3. Proceso de Crear NC desde Devolución.

**Educación y Agencia utilizan el 1 generalmente.**

#### Nota de Crédito Cliente/Proveedor utilizando la opción de Copiar líneas

Para generar una Nota de Crédito Cliente o  Proveedor se utilizará la ventana Documentos por Cobrar o Pagar respectivamente.

Se deberá ingresar:

* Tipo de Documento: Nota de Crédito
* Socio de Negocio: Proveedor que nos facturará
* Dirección de Socio de Negocio

Luego se deberá seleccionar el botón “Copiar líneas”, ubicado en la parte inferior de la pantalla.

Esta opción copiará todas las líneas de la factura a la Nota de crédito, donde se podrán modificar las cantidades y los importes para luego completarla.

#### Nota de Crédito Cliente utilizando la opción “Crear desde”

Para generar una Nota de Crédito Cliente se utilizará la ventana Documentos por Cobrar.

Se deberá ingresar:

* Tipo de Documento: Nota de Crédito
* Socio de Negocio: Proveedor que nos facturará
* Dirección de Socio de Negocio

Luego se deberá seleccionar el botón “Crear desde”:

Este botón permitirá crear la Nota de crédito desde una Orden de venta, Factura o Recibo.

Luego de ingresado el documento permitirá modificarse en la línea de la factura, las cantidades y los importes de la misma para luego proceder a completarla.

Como asignar Nota de crédito a su factura de manera automática:

#### Asignar una Nota de Crédito con su correspondiente Factura relacionada de manera automática

* 1. Desde el proceso de copiar líneas o Crear Desde, además de definir las líneas se agrega dicho Documento por Pagar en la pestaña de "CFE Relacionado".
* 2. Si un Documento por Pagar está definido en la pestaña de CFE relacionado se genera automáticamente la asignación (si es por el 100% del documento).

### Cuándo y por qué se generan Notas de Débito

#### Funcionalidad de la Nota de débito en el sistema

Las notas de débito se hacen cuando una empresa ingresa o genera documentos pero que es sólo un traspaso de gasto. 

Las Notas de Débito Proveedor que ingresa WPP son Facturas que el Proveedor le emite al CLIENTE, es decir pone el RUT del Cliente, pero la Organización las ingresa al sistema ya que ellos le pagan al proveedor.

Para luego cobrarle al cliente se genera una Nota de Débito al Cliente por este mismo importe.

::: note
Estas Notas de Débito NO TIENEN IVA, son todas exentas, ya que el que descuenta el iva compras  es el Cliente.
:::

### POS (Punto de Venta):

#### Se puede Generar desde el POS una factura a credito?

Esa funcionalidad no esta implementada todavia en el POS, para hacerlo debe realizarse desde la ventana Documentos Por Cobrar. 

#### Como se define la Tasa de Cambio y POS:

El tipo tasa de cambio esta definida en la ventana Terminal PDV en el campo “Tipo de Conversión”. Si es “Company” no se carga automaticamente, la define el Cliente o la define OpenUp con una duración especifica. Si es “Spot”, existe un proceso que se ejecuta por medio del CRON y carga la tasa de forma automatica a diario.

### Lista de Precio

#### No se actualiza Moneda en Documento según Lista de Precio:

Cuando el usuario selecciona una Lista de precios, cuya fecha de validez es posterior a la fecha del documento que se está creando, el campo de la moneda no se actualiza. Esto se debe a que en la ventana “Lista de Precios”, seleccionando la lista de precios en cuestion, luego pestaña “Version”, el campo “Valido desde” corresponde a una fecha posterior al documento (por ejemplo Orden de Compra), entonces el campo moneda no refleja el tipo de moneda de la lista de precios en el documento que se esta creando.

::: note
Para que una lista de precios sea correctamente considerada por un Documento la misma debe tener una Fecha (Válido desde) Desde en la Versión Activa igual o mayor al día del Documento.
:::

### FAQ Nota de crédito manual.

Error: Monto total asignado de facturas no puede ser mayor al monto de la nota de crédito

Cuando las Notas de crédito se crean desde el Botón Crear desde en el cabezal de la ventana se crean los registros en la pestaña CFE Referidos y quedarán las lineas de la factura con el monto asignado correcto.

El problema surge cuando la Nota de crédito se crea manualmente, aquí hay que ajustar manualmente el campo Total asignado de la pestaña CFE Referidos en la Nota de crédito, ya que el importe asignado de la factura quedará como todo el disponible de la misma, siendo mayor al de la Nota de crédito.

#### ¿Por qué sucede el siguiente error “Can’t find Bank Account” al completar una Orden de Venta?

El problema es que para  este tipo de Orden de Venta se realizará la Factura y el Pago de manera automática. Si la misma es generada desde la ventana de Orden de Venta puede que no encuentre Punto de Venta por lo tanto no tendrá Cuenta Bancaria definida para hacer el Cobro. 

#### ¿Por que motivo puede NO VISUALIZARSE una Orden de Venta para Facturar?

Puede ser por 4 motivos:

* Que NO esté COMPLETA
* Que no tenga el check de “Permite facturar”
* Ver que Regla de facturación tiene la misma
* Verificar en la línea de la Orden que no tenga Cantidades facturadas

#### ERROR: Producto no está en lista de precios.

Para solucionarlo se debe navegar al producto y agregar en la pestaña Precio la lista de precio que indica el mensaje.

#### Cómo quitar aviso de “Producto sin Inventario” cuando no se desea controlar inventario?

Se soluciona definiendo a los Productos con Tipo “ARTÍCULOS” como Almacenables “N”.

#### Se puede cambiar el nombre de un producto (o SDN) existente?

Los productos tienen un ID que los identifica dentro de la aplicación. Por lo cual si, es posible cambiar el nombre de los productos (O SDN), pero siempre tendrá afectación en todo lugar del sistema donde se visualice dicho producto (inclusive en forma retroactiva). O sea, el nombre que cambien para ese ID producto cambiará para todos los registros en la aplicación.

Por ejemplo si se utilizó este producto en algún Contrato o Factura pasada, el cambio de nombre afectará el nombre del producto definido en dichas facturas... entiendo que en cierta operativa podría afectar si existe alguna factura que aún se encuentra pendiente, entonces en un Estado de Cuenta que se envíe por Morosidad, se reflejará el nuevo Nombre y no el anterior.

#### ¿Por qué al intentar completar una orden de venta  no se completa - POS?

Es posible que la Orden de Venta ya tenga un Pago/Cobro asignado, si es asi, no dejara completar hasta que no se elimine el Pago/Cobro asociado a la Orden de Venta. Luego dejara completar.

#### ¿Cómo genero una Factura Cliente (Documento por Cobrar) a Crédito manualmente?

selecciona el botón forma de pago “A credito”, una vez seleccionado, se despliega el campo “Término de pago”, donde definirá el término deseado. Esta conducta se puede definir en las propiedades del Socio del Negocio para el siguiente Documento por cobrar. Luego de ingresados todos los datos, se da clic en “Completar”.

#### ¿En el Cierre de Caja de Punto de Venta qué muestra el campo “Diferencia Edo. de Cuenta”?

El campo “Diferencia Edo. de Cuenta” representa el saldo que posee la cuenta Caja 

en la que se encuentra realizando el proceso “Cierre de Caja”.

#### ¿Cómo puede igualarse las cantidades ordenadas y entregadas a las cantidades facturadas?

Las Cantidades Facturadas y Entregadas son definidas según la o las Entregas que existan con dicha línea de orden y la o las facturas que existan con dicha línea de orden. no hay otra manera de igualarlas que generando documentos.

Diferente es “Igualar la Cantidad Ordenada a la Cantidad Entregada”. 

Al Cerrar la Orden de Venta / Compra se llevan las cantidades Ordenadas a la cantidad Entregada dejando NINGUNA Cantidad Pendiente de entregar. Esto es “Cerrar una Orden”. a su vez, se actualiza el importe de la orden según la nueva Cantidad definida. 