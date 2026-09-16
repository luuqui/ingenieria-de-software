==ID: Realizar cobro==.
Título: Como empleado quiero realizar un cobro para un cliente.
Reglas de negocio:
- 2do vencimiento de la factura no permite cobro.
- 1er vencimiento de la factura genera recargo al monto original.
- Facturas sin vencimientos se cobra el monto original.

Escenario 1: Cobro exitoso sin vencimiento.
Dada la fecha actual 15/9/2026, el envío de token "abc123" con vencimiento 23/9/2026 vigente para la consulta con la central de cobro, la conexión exitosa con la central de cobro, y el código de pago electrónico 123456 existente en el servidor con primer vencimiento 25/9/2026.
Cuando se ingresa el código de pago 123456 y se presiona el botón "Cobrar"
Entonces el sistema se conecta con la central, espera respuesta, recupera la información, registra el pago por el monto original, imprime un comprobante e informa pago exitoso por el monto original.

Escenario 2: Cobro exitoso con 1er vencimiento.
Dada la fecha actual 15/9/2026, el envío de token "abc321" con vencimiento 23/9/2026 vigente para la consulta con la central de cobro, la conexión exitosa con la central de cobro, y el código de pago electrónico 4321 existente en el servidor con primer vencimiento 14/9/2026.
Cuando se ingresa el código de pago 4321 y se presiona el botón "Cobrar".
Entonces el sistema se conecta con la central, espera respuesta, recupera la información, registra el pago con recargo al monto original, imprime un comprobante e informa pago exitoso con recargo por primer vencimiento.

Escenario 3: Cobro fallido por 2do vencimiento.
Dada la fecha actual 15/9/2026, el envío de token "asd123" con vencimiento 23/9/2026 vigente para la consulta con la central de cobro, la conexión exitosa con la central de cobro, y el código de pago electrónico 987 existente en el servidor con segundo vencimiento 10/9/2026.
Cuando se ingresa el código de pago 987 y se presiona el botón "Cobrar".
Entonces el sistema se conecta con la central, espera respuesta, recupera la información e informa "Cobro fallido, factura con 2do vencimiento".

Escenario 4: Cobro fallido por token vencido.
Dada la fecha actual 15/9/2026, el envío de token "mnb12" con vencimiento 14/9/2026 no vigente para la consulta con la central de cobro.
Cuando se ingresa el código de pago 609 y se presiona el botón "Cobrar".
Entonces el sistema falla en la conexión con la central e informa "Error de autenticación en la central de cobro.".

Escenario 5: Cobro fallido por código de pago inexistente en el sistema.
Dada la fecha actual 15/9/2026, el envío de token "ñlk900" con vencimiento 23/9/2026 vigente para la consulta con la central de cobro, la conexión exitosa con la central de cobro, y el código de pago electrónico 999 inexistente en el servidor.
Cuando se ingresa el código de pago 999 y se presiona el botón "Cobrar".
Entonces el sistema falla en la conexión con la central e informa "Código de pago inexistente en el servidor".

Escenario 6: Cobro fallido por falla de conexión con la central.
Dada la fecha actual 15/9/2026, el envío de token "aaa111" con vencimiento 23/9/2026 vigente para la consulta con la central de cobro y la conexión no exitosa con la central de cobro
Cuando se ingresa el código de pago "aaa111" y se presiona el botón "Cobrar".
Entonces el sistema falla en la conexión con la central e informa "Falla en la conexión con la central".


==ID: Registrar pago.==
Título: Como gerente quiero registrar los pagos para subirlos a la central.
Reglas de negocio:
- El envío de transacciones se realizan solo una vez.
Criterios de aceptación (registrar pago).
Escenario 1: Registro exitoso.
Dado una clave maestra "abc123" habilitada para operar en el sistema, transacciones no registradas por el sistema como enviadas, el envío de token "zzz111" vigente para la consulta a la central a la fecha de hoy 15/9/2026 con vencimiento el 25/9/2026 y una conexión con la central exitosa.
Cuando se ingresa clave maestra "abc123" y se presiona "Aceptar".
Entonces el sistema recupera las transacciones de los impuestos y servicios cobrados en la fecha actual, se conecta a la central, espera respuesta, registra las transacciones y servicios como enviadas e informa "Registro de transacciones y servicios exitoso."

Escenario 2: Registro fallido por transacciones ya enviadas.
Dado una clave maestra "mmm111" habilitada para operar en el sistema y transacciones registradas por el sistema como enviadas.
Cuando se ingresa clave maestra "mmm111" y se presiona "Aceptar".
Entonces el sistema informa "Transacciones del día ya enviadas".

Escenario 3: Registro fallido por clave maestra inexistente en el sistema.
Dado una clave maestra "bbb222" no habilitada para operar en el sistema.
Cuando se ingresa clave maestra "bbb222" y se presiona "Aceptar".
Entonces el sistema informa "Clave maestra no habilitada para operar en el sistema".

Escenario 4: Registro fallido por token vencido.
Dado una clave maestra "eee111" habilitada para operar en el sistema, transacciones no registradas por el sistema como enviadas, el envío de token "ddd222"  no vigente para la consulta a la central a la fecha de hoy 15/9/2026 con vencimiento el 14/9/2026.
Cuando se ingresa clave maestra "eee111" y se presiona "Aceptar".
Entonces el sistema recupera las transacciones de los impuestos y servicios cobrados en la fecha actual, falla en la conexión a la central e informa "Falla en la autenticación a la central, token vencido".

Escenario 5: Registro fallido por falla en la conexión con la central.
Dado una clave maestra "ggg222" habilitada para operar en el sistema, transacciones no registradas por el sistema como enviadas, el envío de token "ooo555" vigente para la consulta a la central a la fecha de hoy 15/9/2026 con vencimiento el 25/9/2026 y una conexión con la central fallida.
Cuando se ingresa clave maestra "ggg222" y se presiona "Aceptar".
Entonces el sistema recupera las transacciones de los impuestos y servicios cobrados en la fecha actual, falla en la conexión a la central e informa "Falla en la conexión con la central".

==ID: Ver estadisticas.==
Título: Como gerente quiero ver las estadísticas para realizar un analisis.
Reglas de negocio: -
Criterios de aceptación (ver estadisticas)

Escenario 1: Recepción de estadisticas exitosa.
Dada una clave maestra "aaa222" habilitada para operar en el sistema y un rango de fechas 10/10/2026 - 20/10/2026 con pagos registrados en el sistema.
Cuando se ingresa clave maestra "aaa222" y se presiona "Aceptar".
Entonces el sistema válida la clave maestra e informa los montos y la cantidad de cobros realizados agrupando por empresa.

Escenario 2: Recepción de estadisticas fallida por clave maestre inhabilitada.
Dada una clave maestra "qqq111" no habilitada para operar en el sistema.
Cuando se ingresa clave maestra "qqq111" y se presiona "Aceptar".
Entonces el sistema válida la clave maestra e informa "Clave maestra no habilitada".

Escenario 3: Recepción de estadísticas exitosa sin pagos registrados.
Dada una clave maestra "aaa222" habilitada para operar en el sistema y un rango de fechas 21/9/2026 - 25/9/2026 sin pagos registrados en el rango.
Cuando se ingresa clave maestra "aaa222" y se presiona "Aceptar".
Entonces el sistema válida la clave maestra e informa que no se registraron pagos en el rango especificado.

