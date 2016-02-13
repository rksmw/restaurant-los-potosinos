## Diccionario de Datos ##

Aquí se muestra las tablas con sus datos y sus respectivas descripciones


# Usuario #
| **Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:---------------|:---------|:-------|:-----------|:--------------|

|Pk | id\_usuario | int| 5|llave unica de usuario|
|:--|:------------|:---|:-|:---------------------|
|   |nombre       | varchar	|30| nombre del usuario   |
|   |apellidos    |	varchar	|30|apellidos del usuario |
|   |tipo\_user   |	varchar	|15|	descripcion del tipo de usuario (administrador, cajera)	|
|   |contraseña   |	varchar	|12|	contraseña del usuario|


# Proveedor #
| **Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:---------------|:---------|:-------|:-----------|:--------------|
|Pk              |id\_proveedor|	varchar	|5           |	llave unica del proveedor|
|                |	nombre	  |varchar	|20          |	nombre del provedor (empresa)|
|                |	direccion|varchar |25          |	direccion del proveedor	|
|                |	telefono |	varchar	|13          |	telefono del proveedor	|
|                |	contacto |	varchar	|50          |	nombre de la persona relacionada al proveedor	|

# Producto #
| **Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:---------------|:---------|:-------|:-----------|:--------------|
|Pk              |	id\_producto|	varchar|	5	         |llave unica del proveedor|
|                |	nombre   |	varchar	|30          |	nombre de producto|
|                |	costo    |	moneda	|	           |costo de adquisición del producto|
|                |	precio	  |moneda  |		precio del producto| |
|                |	unidad	  |varchar |	20         |	unidad de medida del producto|
|                |	existencia|	int    |	5          |	cantidad de producto existente|
| Fk             |	id\_proveedor|	int    |	5          |	id del proveedor|


# Mesero #
| **Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:---------------|:---------|:-------|:-----------|:--------------|
|Pk              |	id\_mesero|	int    |5	          |	llave unica del mesero|
|                |	nombre   |	varchar	|50          |	nombre del mesero|

# Mesa #
|**Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:--------------|:---------|:-------|:-----------|:--------------|
|Pk             |	id\_mesa |	int	   | 3          |	llave unica de mesa|

# Venta #
|**Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:--------------|:---------|:-------|:-----------|:--------------|
|Pk             |	id\_venta|	int    |5           |		llave unica de venta|
|               |	fecha	   |varchar |	30         |	fecha de la venta |
|Fk             |	id\_mesa	|int	    | 5          |	numero de mesa que se cobra|
|               |	total	   |moneda	 |            |	total de la venta |
|               |	tipodeservicio	|varchar |	20         |	tipo de servicio (consumo en mesa o banquete)|
|               |	status	  |varchar |	1          |	si la venta esta activa o inactiva(por cobrar o cobrada)|
|Fk             |	id\_cliente|	varchar|	5          |	numero de cliente al que se atendio|
| Fk            |	_id\_usuario_|	int    |	5	         |nomero de ajeroo administrador que hace el cobro|
| Fk            |	id\_mesero|	int    |	5          |	numero de mesero que atendio la mesa|

# Des-Venta #
|**Tipo Llave** |**Campo** |**Tipo**|**Longitud**|**Descripción**|
|:--------------|:---------|:-------|:-----------|:--------------|
|Pk             |	id\_desglose\_venta|	int    |5           |		llave unica de desglose de venta|
| Fk            | id\_producto|	int    |	5          |	clave del producto a vender |
|               |	cantidad |	int	   |5           |	cantidad vendida de un solo producto |
|               |	subtotal	|int	    |5           |	subtotal de la cantidad vendida de un solo producto|
|Fk             | id\_venta |	int    | 5          |		numero de la venta que se esta haciendo desgloce |