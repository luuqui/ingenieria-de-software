id: solicitar credito
titulo: como cliente quiero solicitar un credito para pagar un auto.
reglas de negocio:
- El dni corresponde a un cliente del banco
- El credito solicitado no debe superar los $400.000
criterios de aceptacion (pedir credito)

escenario 1: solicitud exitosa
Dado un dni 111 registrado en el sistema como cliente del banco y un monto solicitado de $300.000 que no supera los $400.000
Cuando se ingresa dni 111, nombre "luca", apellido "xx", mail "xx", tipo de credito "xx", monto $300.000 y se presiona "Solicitar"
Entonces el sistema almacena la solicitud e imprime un numero de comprobante.

escenario 2: solicitud fallida por dni no correspondiente a un cliente del banco.
Dado un dni 222 no registrado en el sistema como cliente del banco.
Cuando se ingresa dni 222, nombre "luca", apellido "xx", mail "xx", tipo de credito "xx", monto $100.000 y se presiona "Solicitar".
Entonces el sistema envía un correo electronico al mail ingresado con un instructivo para hacerse cliente del banco e informa "El dni no corresponde a un cliente del banco".

escenario 3: solicitud fallida por monto superior a lo permitido.
Dado un dni 444 registrado en el sistema como cliente del banco y un monto solicitado de $500.000.
Cuando se ingresa dni 444, nombre "luca", apellido "xx", mail "xx", tipo de credito "xx", monto $500.000 y se presiona "Solicitar".
Entonces el sistema informa "El monto solicitado excede el límite permitido".

---------------

id: consultar tramite
titulo: como cliente quiero consultar el estado de un tramite para saber si fue aprobado.
reglas de negocio:
- Al ingresar 3 veces un código inexistente, el sistema bloque la ip del cliente por 24 horas.
criterios de aceptacion (consultar tramite)

escenario 1: consulta exitosa.
Dado un codigo de comprobante 222 válido y una direccion ip "333.333" con 1 intento de ingreso de codigo fallido registrado en las ultimas 24hs
Cuando se ingresa codigo de comprobante 222 y se presiona "Consultar".
Entonces el sistema informa el estado del tramite.

escenario 2: consulta fallida por comprobante no valido y alcanzar el limite de intentos.
Dado un codigo de comprobante 111 no valido y una direccion ip "111.111" con 2 intentos de ingreso de codigo fallido registrado en las ultimas 24hs
Cuando se ingresa codigo de comprobante 111 y se presiona "Consultar".
Entonces el sistema registra el código de comprobante invalido y bloquea la ip del cliente e informa "Usted ha excedido el número de consultas inválidas".

escenario 3: consulta fallida por comprobante no valido.
Dado un codigo de comprobante 333 no valido y una direccion ip "222.222" con 1 intento de ingreso de codigo fallido registrado en las ultimas 24hs.
Cuando se ingresa codigo de comprobante 333 y se presiona "Consultar"
Entonces el sistema registra el intento fallido e informa "Trámite inexistente".

escenario 4: consulta fallida por ip bloqueada.
Dado un codigo de comprobante 444 valido y una direccion ip "555.555" sin intentos disponibles por bloqueo de ip
Cuando se ingresa codigo de comprobante 444 y se presiona "Consultar"
Entonces el sistema informa "Sistema bloqueado".

------------------------

id: pedir listado
titulo: como gerente del banco quiero pedir un listado de creditos para hacer un analisis.
reglas de negocio: -
criterios de aceptacion (pedir listado)

escenario 1: pedido exitoso
Dado un rango de fechas 24/8/2026 al 24/9/2026 válido y con creditos aprobados en ese rango
Cuando se ingresa fecha de inicio 24/8/2026, fecha final 24/9/2026 y se presiona "Pedir"
Entonces el sistema informa un listado con los créditos aprobados en el rango ingresado.

escenario 2: pedido fallido por rango invalido
Dado un rango de fechas 24/9/2026 al 24/5/20250 inválido
Cuando se ingresa fecha de inicio 24/9/2026, fecha final 24/9/2026 y se presiona "Pedir"
Entonces el sistema informa "Las fechas ingresadas no son válidas".

escenario 3: pedido en un rango sin créditos aprobados
Dado un rango de fechas 23/7/2026 al 10/8/2026 sin creditos aprobados en ese rango
Cuando se ingresa fecha de inicio 23/7/2026, fecha final 10/8/2026 y se presiona "Pedir"
Entonces el sistema informa "No hay créditos aprobados en las fechas ingresadas".