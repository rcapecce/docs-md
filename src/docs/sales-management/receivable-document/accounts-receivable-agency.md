---
title: Documentos por Cobrar Agencia
category: Documentation
star: 9
sticky: 9
tag:
  - Agencia
article: false

---

## Documentos por Cobrar Agencia

Facturar en moneda distinta con la que se generó el Proyecto:

Si se desea facturar en una moneda distinta con la que se generó el Proyecto podremos cambiar la misma en la Orden de Venta indicando la correspondiente tasa de cambio, (en el caso que la misma se encuentre en estado Borrador).

En el caso que las Ordenes de venta estén Completas se deberán anular y generar de nuevo, ya que si se reactivan se tendrán que anular la Ordenes de Venta Honorarios que se generen.

### Generar Órdenes de Venta recurrente desde Contrato de Servicios

A partir de la definición de las líneas de un contrato se puede generar Órdenes de Venta según los Servicios Recurrentes que deban ser facturados según determinada recurrencia. De esta manera se podrán generar Órdenes de Venta según las mensualidades definidas en los Contratos.

El proceso será el siguiente:

Definición correcta del Contrato de Servicios: el primer paso para comenzar el proceso es verificar que todos los contratos estén correctamente definidos, tanto según las fechas del mismo como también las líneas.

Crear “Cuotas a Facturar”: a partir de la definición de líneas en los contratos con su recurrencia correspondiente e importe, se deberá proceder a generar las “Cuotas a Cobrar” a partir del mismo. Este proceso puede generarse tanto desde la ventana “Contrato de Servicios” mediante el Proceso “Generar Cuotas desde Contrato” ubicado en los procesos asignados al registro, de esta manera se generarán TODAS las Cuotas a Facturar desde 1 solo contrato. También se tiene la opción de realizarlo de manera masiva para todos los contratos desde el proceso “Generar Cuotas a Facturar desde Contrato” ubicado en el menú, en este caso podrá no seleccionar ningún Contrato de Servicios en especial generando así Cuotas para Todos los Contratos.

![Generar Cuotas desde Contrato](/assets/img/docs/sales-management/sam-agency1.png)

Generar Orden de Venta desde Cuota a Facturar de Contrato de Servicios: Una vez se tienen todas las “Cuotas a Facturar de los Contratos de Servicios” creadas, se podrá generar a partir de las mismas las Órdenes de Venta para que puedan ser ingresadas luego al Proceso de Facturación. Estas Órdenes de Venta se sugiere utilizar el Tipo de Documento “Orden de Venta Fee”. En el Proceso se podrán filtrar según el Socio del Negocio, la Organización o la Fecha de la Cuota a facturar. En este proceso se podrá definir un sólo Socio del Negocio o todos los que desee. Se recomienda filtrar según Fecha para asegurarse que se está generando las cuotas correspondiente al mes que desea. En los parámetros del proceso podrá ver que está editable la Fecha del Documento que desea generar.

IMPORTANTE: Para poder generar las Órdenes de Venta FEE desde el proceso “Generar OV desde Cuota de Contrato” es obligatorio que el Cliente tenga creado un Proyecto en el cuál tenga definido el check de “Es por defecto para FEE”.

![Generar OV desde Cuota de Contrato](/assets/img/docs/sales-management/sam-agency2.png)

### Orden de Venta a Facturar en Cuotas

Una Orden de venta podrá definirse que se pueda facturar en N Cuotas.

Para ello se definió el campo de “Regla de Facturación” donde se podrá escribir cómo se desea que una Orden de Venta sea facturada o bien como una Orden de compra deberá ser facturada por el Proveedor.

Para la generación de esta Orden de Venta o Compra, se sugiere definir una CANTIDAD que sea igual al número de cuotas que se deberá facturar y el importe unitario por el valor de dicha cuota.

**Para el caso que una Orden de Venta u Orden de Compra deba ser Facturada en diferentes “Cuotas” se deberá definir en la Fase del Proyecto:**

* **Producto a Facturar:** Como la facturación no se realizará producto a Producto que fue solicitado, se debe definir un Producto Genérico que será el que finalmente será facturado.
* **Descripción:** Escribir en la Descripción de la FASE cómo se desea que sea Facturado para que Administración se entere y
* **Cantidad:** Además en el Campo “Cantidad” de la Fase se deberá definir la Cantidad de Cuotas que se desea Facturar, ya sea por el Medio o al Cliente. Ver que como Precio Unitario se deberá visualizar el importe de cada una de las cuotas a ser Facturado.

### Generar Factura desde Orden de Venta

Las órdenes de venta generadas en el sistema pueden ser facturadas de manera ágil y masiva utilizando el proceso **“Generar Factura desde Línea de Orden”.**

![Generar OV desde Cuota de Contrato](/assets/img/docs/sales-management/sam-agency3.png)

#### Precondiciones

Para poder facturar una Orden de Venta, esta tiene que estar

* Estado: Completo
* Con el check “Permite Facturar” = SI
* Regla de Facturación: Inmediata

En este proceso se podrá aplicar el filtro que desee para encontrar aquellas líneas de ordenes que cumplan con dichas condiciones.

Dentro de los filtros a definir podemos encontrar:

#### Generar Factura

Y comenzaremos la búsqueda, a continuación obtendremos las líneas de Orden de Venta que cumplan con la condición.

Procederemos a marcar el check que esté como primer columna para todas las líneas que se deseen facturar.

En la parte inferior de esta ventana veremos distintas opciones utilizadas al momento de generar la factura:

**Fecha de Facturación:** (Obligatorio) Fecha de facturación del Documento por Cobrar generado.

**Acción en el Documento:**

* **Preparar:** Si desea ver la Factura antes de completarla puede seleccionar la opción “Preparar” de manera de que se genere el documento primero en estado “En Proceso” y así poder verificar que todo esté correctamente definido. En este caso al generar el proceso se creará la factura con un Nro de Borrador “DR-2222” y podrá acceder a la misma tanto desde el proyecto u Orden desde donde se generó, cómo también buscando en la ventana “Documentos por Cobrar” según el Nro de borrador presentado abajo a la izquieda del Proceso.
* **Completar:** Si uno está seguro de la información que estará facturando también puede seleccionar la acción “Completar” de manera de que se completen automáticamente las facturas al correr el proceso.

**Organización de la Transacción:** Es la organización con la que se está logeado, necesario cuando el documento pasa a estado completo, debido a que no se pueden realizar envíos a DGI de un documento con una organización que no es con la que se está logueado.

**Criterio de Agrupación:** Según el Criterio de Agrupación definido es la forma en que el sistema agrupará las líneas de órdenes en una Factura, estas puede ser por:

* **Socio del Negocio:** Generará una Factura con todas las líneas de Orden de por cada Socio del Negocio diferente.
* **Contrato:** Generará una factura por cada Contrato establecido en las Órdenes de Venta, agrupará en esa factura todas las Órdenes que pertenezcan al mismo contrato.
* **Proyecto:** Si la línea tiene definido el Proyecto utilizará esta referencia y en caso de no tenerlo establecido tomará el de su respectiva orden (puede ser que en una misma agrupación algunas líneas tengan Proyecto relacionado y a la vez otras que se tenga que obtener de su respectivo Cabezal), Siguiendo este criterio se generará un Documentos por Cobrar por proyecto diferente.
* **Orden:** La agrupación que agrupa menos registros, se generará cada factura agrupando líneas de Orden por su respectivo cabezal.
* **Impuesto:** Agrupará por Impuesto definido en cada Línea de Orden seleccionada. Se generará una factura por tipo de impuesto encontrado. El criterio de agrupación no es por % (Ej: 22%, 10% o 0%), sino por diferente Tipo de Impuesto.
* **Orden de Compra Cliente:** Si se selecciona este Criterio de Facturación se generará una Factura por cada Número de la Orden de Compra Cliente que se encuentre en todas las líneas seleccionadas. Este criterio de agrupación incluye además la clasificación según diferentes clientes.

![Ventana Selección](/assets/img/docs/sales-management/sam-agency4.png)

### **¿Por qué motivo puede no referenciarse un Proyecto en una factura?**

El Proyecto se referenciará en la factura siempre que el criterio de agrupación que se haya elegido para agrupar las lineas de Orden al correr el proceso Generar factura desde línea de Orden haya sido “Proyecto”.

Por ejemplo se puede tener N proyectos por Contrato pero solo Un Contrato por cada proyecto. Por lo que si se agrupa por Contrato, como las lineas de orden pueden ser de varios proyectos, al generar la factura no establece el campo de Proyecto en el cabezal.

Respecto al Tipo de documento, el sistema controlará si el Socio del Negocio a quien se está facturando tiene definido un RUT o una Cédula y le generará una e-Factura o un e-ticket según corresponda.

### **Criterios Implícitos**

Además de los criterios definidos manualmente, siempre se agrupará una factura teniendo en cuenta que deben ser:

* Para un mismo Socio de Negocio
* Una misma localización para ese Socio de Negocio (Su dirección de facturación seleccionada)
* Misma Moneda: Tener en cuenta que es la moneda a Facturar de la Orden de Venta, por si la misma hace un cruzamiento de monedas.

Estos son requerimientos obligatorios por la naturaleza del CFE.

Nota: En el caso que se defina la opción para Completar el documento se ejecutará automáticamente el proceso Generar líneas de CFE.

#### **Criterio de Facturación (definición de Líneas de Factura)**

El **Criterio de Facturación** permite generar líneas más resumidas de la información que se está Facturando, adaptando así según la necesidad de cliente, definiendo en ellas la información exacta que el cliente desea recibir en cada “Concepto de Facturación”.

Debido a que el ERP puede tener una definición muy detallada de las “líneas de las órdenes” presentando en ellas un concepto de **Servicios**, **Cantidades** y **Precios** que si bien puede ser de gran utilidad para la gestión interna y el control de sus Costos, en ciertas ocasiones a los clientes no les interesa contar con tal detalle.

De esta manera, el **Criterio de Facturación** que tendrá cada Factura será criterio que se va a utilizar para generar las líneas que se detallarán en el CFE (e-Factura o e-Ticket).

### Facturación de Honorarios en Línea independiente

El Criterio de Facturación aplicará siempre para las líneas de “Inversión” del cliente, agrupando según el criterio seleccionado. Esto quiere decir que el criterio nunca aplicará la agrupación para aquellas líneas que correspondan a Honorarios Variables calculados en un Proyecto o Fase de Proyecto, estos siempre irán en una línea aparte detallando que son Honorarios.

### Proceso automático

El Criterio que se definirá en cada factura será el que cada cliente tenga definido en su ficha, pudiendo ser por Línea (normal), por Proyecto, por Fase de Proyecto o por Factura. .

Al utilizar como criterio “Proyecto”, el sistema agrupará en una línea a todas las líneas del Proyecto y definirá la descripción de la misma según el campo “Detalle Factura” ubicado en el Proyecto en cuestión.

::: note
Siempre se agrupan las líneas que no sean Honorarios ya que éstos van en otra línea a parte.
:::

Si utilizamos como criterio “Fase del proyecto”, el sistema agrupará todas las líneas de una fase en una línea, por lo que la factura tendrá tantas líneas de CFE como fases se estén facturando. En la descripción de cada línea se obtendrá según el campo “Detalle Factura” ubicado en cada Fase del Proyecto en cuestión.

Este proceso se puede realizar de forma automática o manual.

### Proceso Manual

Si para alguna factura en especial se desea utilizar un Criterio de Facturación diferente al que tiene definido el Cliente por defecto, se podrá generar el mismo desde el cabezal de la factura.

Si se desea realizar el proceso de forma manual se deben seguir los siguientes pasos luego de generar la factura:

Elegir en el campo “Criterio de Facturación” ubicado en la Factura el Nuevo Criterio que se desee aplicar.

![Criterio de Facturación](/assets/img/docs/sales-management/sam-agency5.png)

Luego procederemos a correr el proceso “Generar líneas de factura para CFE”, seleccionando la opción desde los Procesos asociados a la Factura.

![Criterio de Facturación](/assets/img/docs/sales-management/sam-agency6.png)

## Posibles Errores Controlados

**Varios Términos de Pago en las Órdenes de Venta seleccionadas**

Cuando se están facturando en una misma factura varias Órdenes de Venta que tienen diferentes Términos de Pago no permitirá generar una única factura y figurará el siguiente mensaje de Error:

Esto se debe a que no puede determinar que término de pago se desea definir en la Factura a Generar.

**Solución: Para solucionarlo lo ideal sería abrir en la ventana de “Órdenes de Venta” todas las Ordenes de venta que se están intentando facturar Varios Términos de Pago en las Órdenes de Venta seleccionadas.**

**Ver las mismas en formato “Grilla” para identificar qué Orden de Venta tiene un Término de Pago diferente.**

**Para modificarlo deberá Rectivar la Orden, modificar el Término de Pago y luego completarla nuevamente.**

**Varios Agentes Comerciales definidos en las Órdenes de Venta**

En principio el proceso definirá el Agente Comercial en la Factura según el Agente que esté definido en la Orden de Venta en cuestión.

En caso de que existan diferentes Agentes Comerciales definidos en las Órdenes de Venta el proceso tomará el Agente Comercial definido en el Socio del Negocio.

Si no tiene ninguno definido en el Socio del Negocio tomará el Agente Comercial definido en las Ordenes de Venta. Si estos son diferentes dará un error.

### Generar Líneas de CFE

En vista a que las líneas del Documento por Cobrar no siempre se corresponden con las líneas a enviar en el CFE e imprimir en la representación impresa, además de disponer en esta venta a de las líneas del documento (la pestaña convencional), se ha agregado una pestaña donde figuran las líneas que deberán enviarse en el CFE.

A grandes rasgos es la misma información que las líneas convencionales del Documento por Cobrar solo que en un estado más resumido.

**Precondición:** Para generar o Modificar las líneas CFE, la factura no puede estar completa porque en este caso ya estaría enviada a DGI y no tendría sentido realizar modificaciones sobre sus respectivas líneas.

**Observación:** No aplica para Resguardos

En el cabezal del Documento por Cobrar en la sección Facturación hay un campo llamado **“Criterio de Facturación”**, este campo indica dentro de este documento cómo deben agruparse sus respectivas líneas (en orden jerárquico).

* Factura: Realizará solo una línea agrupando todas las líneas de este documento: Descripción de línea queda vacío, deberá completarse manualmente
* Contrato: Descripción de línea: (Línea Factura) -> Proyecto -> Contrato.Nombre (Ver Nota 1)
* Proyecto: Descripción de línea: (Línea Factura) -> Descripción del Proyecto (Ver Nota 1)
* Fase de Proyecto: Descripción de línea: (Línea Factura) -> Descripción de Fase (Ver Nota 2)
* Línea: Descripción de línea: (Línea Factura) -> Si tengo Producto utilizo su nombre y descripción, Si no tengo Producto pero si Cargo utilizo Nombre y Descripción del Cargo. Si no tengo ninguno retornará un error.

::: note
Siempre que para todas las líneas de Factura tenga el mismo proyecto, en caso contrario quedará vacío
:::

:::note
Siempre que para todas las líneas de Factura tenga la misma fase de proyecto, en caso contrario quedará vacío
:::

### **Configuración del Socio del Negocio**

#### **Criterio de Líneas en Factura**

En cada Socio del Negocio se podrá pre configurar el criterio de facturación que se desee. Esto se debe definir en la pestaña Cliente de la ventana Socio del Negocio en el campo Criterio de Facturación.

![Socio del Negocio](/assets/img/docs/sales-management/sam-agency7.png)

#### Facturar al Cliente en moneda diferente al Costo

En caso que al Cliente se le deba Facturar en otra moneda, la Orden de Venta deberá ser en la misma moneda que se comprará al Proveedor, pero se podrá definir en la Orden de Venta una moneda diferente a ser Facturado junto con su Tasa de Cambio acordada.

En caso de querer definir la Tasa de conversión luego de completar la Orden o modificar la misma luego de completarla se podrá hacer desde el proceso.

### Facturación por Proyecto

Al facturar por Proyecto el sistema generará una línea por todas las líneas que posea el Proyecto con la descripción del mismo, la cual obtiene del campo “Detalle en Factura” del cabezal del Proyecto.

En la ventana Socio del Negocio, pestaña Cliente, en el campo “Criterio de Facturación” se puede indicar “Proyecto”, para este Socio de negocio. De esta forma se puede automatizar este procedimiento ya que la factura tomará de forma automática este dato.

Luego, mediante la ventana Generar factura desde línea de Orden, se procederá a facturar buscando entre las diferentes líneas que tengan las Órdenes de Venta en estado Completo.

En la parte inferior de esta ventana veremos distintas opciones utilizadas al momento de generar la factura.

* Fecha de Facturación: (Obligatorio)
* Acción en el Documento: (Preparar, completar)
* Organización de la Trans.
* Criterio de Agrupación: Es el criterio para agrupar las líneas de orden ya sea por Socio de negocio, Contrato, Proyecto, Orden , Impuesto, POReference, Adicionales).

::: note
Tener en cuenta que el “Criterio de Agrupación” y el “Criterio de Facturación” NO son lo mismo.
:::

Luego seleccionaremos el botón de OK y se generará el Documento por cobrar correspondiente.

Al mismo podemos acceder desde el ícono de documentos relacionados desde el cabezal de la orden de venta.

Este factura tendrá definido en el cabezal de la misma, en la región de Facturación, el correspondiente Criterio de Facturación elegido.

Si elige no hacerse este procedimiento de forma automática lo podremos hacer manualmente.

Para realizarlo seleccionaremos la opción “Proyecto” en el campo Criterio de Facturación de la factura y a continuación correremos el proceso “Generar líneas de factura para CFE” utilizando el ícono de la tuerca.

Generará también en la pestaña Línea de la factura CFE una línea cuya Descripción tendrá definida lo mismo que se definió en el campo “Detalle en Factura” en el cabezal del Proyecto.

**Siempre se agrupan las líneas que no sean Honorarios ya que éstos van en otra línea a parte.**

### **Facturación por Fase**

Al facturar por Fase el sistema generará una línea agrupándolas por Fase del Proyecto con la descripción de las mismas, las cuales obtiene del campo “Detalle en Factura” de las fases del Proyecto.

En la ventana Socio del Negocio, pestaña Cliente, en el campo Criterio de Facturación se puede indicar “Fase de Proyecto”, para este Socio de negocio.

De esta forma se puede automatizar este procedimiento ya que la factura tomará de forma automática este dato.

Luego, mediante la ventana Generar factura desde línea de Orden, se procederá a facturar buscando entre las diferentes líneas que tengan las Órdenes de Venta en estado Completo.

Podremos acceder al Documento por cobrar desde el ícono de documentos relacionados desde el cabezal de la orden de venta.

Este factura tendrá definido en el cabezal de la misma, en la región de Facturación, el correspondiente Criterio de Facturación elegido.

Si elige no hacerse este procedimiento de forma automática podremos hacerlo manualmente.

Para realizarlo seleccionaremos la opción “Proyecto” en el campo Criterio de Facturación de la factura y a continuación correremos el proceso “Generar líneas de factura para CFE” utilizando el ícono de la tuerca.

Generará también en la pestaña Línea de la factura CFE la cantidad de líneas según la cantidad de fases que tenga el Proyecto.

Estas líneas tendrán definidas en el campo “Descripción” lo mismo que se definió en el campo “Detalle en Factura” a las fases del Proyecto.

**Siempre se agrupan las líneas que no sean Honorarios ya que éstos van en otra línea a parte.**

### **Nota de Crédito Cliente**

**Existen las siguientes razones por la cual se debe realizar una Nota de Crédito:**

**Solicitud del Cliente de Re-facturación:** Se recibe solicitud del cliente que necesita que su Orden de Compra sea Facturada nuevamente por lo que se debe hacer una NC sobre la Factura ya realizada.

**Servicio Entregado No Aceptado:** Cuando un servicio se realizó (Delivery) pero que no es aceptado por el Cliente total o parcialmente por lo cual solicita una *Devolución* junto con su correspondiente *Nota de Crédito*.

**Servicio Facturado pero No Entregado:** Cliente solicita Nota de Crédito por la Facturación de un servicio que no fue entregado.

**NC Manual por Diferencia de Precio o Descuento Financiero:** NO RECOMENDADO

#### Generar Devoluciones a Cliente

Se deberá realizar la “Devolución de Cliente” cuando un Cliente solicita o el Ejecutivo de Ventas solicita en nombre del cliente, la emisión de una Nota de Crédito debido a una “Entrega” (Delivery) No aceptada por el cliente. Esta “Devolución Cliente” deberá ser generada desde el Proceso “Generar Devoluciones”, seleccionando la Orden de Venta del Cliente que se querrá devolver.

Este proceso se deberá realizar si se desea “Corregir” un checking ya realizado en un Período anterior que se encuentra ya CERRADO. Lo que realizará esta “Devolución Cliente” son 2 acciones:

Generar un Movimiento contrario a la Entrega realizada por el Checking. Restando así el Ingreso reconocido con dicha “Entrega”

Generar una Devolución de Proveedor Espejo, es decir se generará una Devolución Cliente y una Devolución Proveedor por la MISMA CANTIDAD definida. Dichas devoluciones luego quedarán a la espera de sus correspondientes Notas de Crédito. Administración podrá ver las Devoluciones Cliente que están pendientes de Generar Nota de Crédito y del lado del Proveedor estarán las “Devoluciones Proveedor” (o RMA) pendientes de generar Notas de Crédito Proveedor cuando estas lleguen.

#### **Generación de Nota de Crédito**

Este acto se complementa con la Generación posterior de la “Nota de Crédito Cliente” a partir de la Devolución Cliente. Esta acción se podrá realizar mediante el Proceso “Generar Nota de Crédito por Devolución”

#### **Generar NC Desde Devolución**

Para que aparezca la información se deberá seleccionar el Tipo de Documento “Devolución Cliente” y se recomienda definir en Acción del Documento “Preparar”se generará un Documento por Cobrar del tipo “e-Factura Nota de Crédito” en estado “En Proceso”. El encargado de facturación deberá tomar el mismo, verificar las Línea CFE y simplemente Completarlo. Dicho documento se debería haber generado con toda la información correspondiente de “Sello, Sello Origen, Contrato de Servicios, DxC que Asignará, Proyecto, etc.

#### **Control Nota de Crédito sólo si está facturado**

Las devoluciones se podrán realizar siempre y cuando exista una Entrega/Recepción pero estas, si bien pueden aparecer no podrán ser Facturadas. Si se intenta Facturar dará Error “Not Invoiced” verificando así que dicha devolución sea sobre una línea que está Facturada.

#### **Servicio Facturado pero No Entregado**

Para este caso, debido a que el importe que se deberá generar una Nota de Crédito aún no fue Entregado, es decir no se realizó Checking, para solicitar la creación de una Nota de Crédito por las Cantidades que fueron Facturadas pero no fueron Entregadas bastará que el Usuario “Cierre” la Orden de Venta correspondiente. Al Cerrar una Orden de Venta las “Cantidad Ordenada” de sus líneas son llevadas a la “Cantidad Entregada”.

#### **Control de Facturación correcta en Órdenes de Venta**

El sistema, luego de Cerrar una Orden, realizará un control de verificar si la Orden de Venta está Correctamente Facturada. Este Control implica 2 verificaciones:

Control de Cantidades: En cada una de sus líneas se verificará que su “Cantidad Facturada” NO sea SUPERIOR a la “Cantidad Ordenada”. En caso de encontrar alguna línea que sea superior, es decir que se haya Facturado más de lo Ordenado y que la Orden esté Cerrada, se generará automáticamente una “Solicitud de Nota de Crédito” detallando la Orden de Venta y Factura vinculada y se le asignará al Departamento “Administración”. Este control se aplicará siempre y cuando dicha Orden no haya sido “Modificada”

1. Control de Totales (Orden Modificada): Si en el primer control no encontró nada por lo que deba realizar una Solicitud de NC, se deberá continuar con el siguiente paso que será analizar el “Total de Líneas” de la Orden es Menor que el “Total de Líneas” del Documento por Pagar vinculado a la misma. En caso de que la Orden sea Menor que el DxP entonces deberá correr el proceso de “Solicitud de NC”.

#### **Generar Nota de Crédito Cliente desde la Factura**

Para generar una Nota de Crédito Cliente mediante la opción **“Crear desde”** se utilizará la ventana Documentos por Cobrar.

Se deberá ingresar:

* Tipo de Documento: Nota de Crédito
* Socio de Negocio: Cliente al que se facturará
* Tipo Autorización Devolución: Motivo por el cual se hace la Nota de Crédito

Guardaremos el cabezal y seleccionaremos el botón “Crear desde".

Este botón permitirá crear la Nota de crédito desde una Orden de venta o compra, Factura o Recibo.

![Nota de Crédito](/assets/img/docs/sales-management/sam-agency8.png)

Seleccionaremos el tipo de documento, el documento en cuestión y realizaremos la búsqueda smartbrowser.

Esta búsqueda nos mostrará todas las líneas del documento, las cuales podemos seleccionar mediante un “check” modificando sus cantidades si se desea.

Luego correremos el proceso seleccionando el botón de OK.

Inmediatamente el sistema cargará las líneas a la Nota de crédito (donde se podrán modificar las cantidades y los importes) y definirá en la pestaña CFEs Referidos la factura que estoy asignando.

Por último procederemos a completar la Nota de Crédito.

La misma quedará con el check “pagado” siempre que haya sido por el total de la factura.

![Selección](/assets/img/docs/sales-management/sam-agency9.png)

::: note
Para ingresar una Nota de crédito Proveedor se utiliza el mismo procedimiento de ingreso de una factura de compra, indicando como Tipo de documento una Nota de crédito.
:::

### **Solicitud de Re-facturación**

En caso que se solicite realizar una Nota de Crédito a un Cliente pero sin modificar la Entrega correspondiente ya que está correcta, se deberá generar una Solicitud del Tipo “Solicitud de Nota de Crédito”.

La Solicitud deberá ser creada desde la ventana de “Órdenes de Venta” o “Documentos por Cobrar” desde el Documento en cuestión en base a cuál se debe generar la Nota de Crédito. La Solicitud debe ser enviada a un Usuario de Administración y también definir el “Departamento”: Administración de manera que pueda visualizar dicha solicitud y proceder con la Generación de la NC.

Para generar la NC se deberá generar la misma desde la Ventana “Documentos por Cobrar” seleccionando el SDN a quien será generada. Para obtener la información de la Factura que se estará cancelando se deberá seleccionar la misma desde el botón “Crear Desde”. Con este proceso se definirá todos los campos igual a como estaba la Factura generada. En caso de tener que modificar la Cantidad que se desea hacer NC se deberá ir a las líneas a modificarlas manualmente.

Luego de “Completar” la Nota de Crédito, la Orden de Venta que había sido Facturada quedará nuevamente disponible para volver a ser Facturada.

El asiento contable es el inverso a la Factura.