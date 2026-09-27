------------------------------------------------------
id: iniciar sesion
titulo: como encargado de mobiliario quiero iniciar sesion para acceder al sistema.
reglas de negocio: -
criterios de aceptacion(iniciar sesion)

escenario 1: inicio exitoso.
Dado un mail "luca@gmail.com" existente en el sistema y una contraseña 123 coincidente con el mail en el sistema.
Cuando se ingresa mail "luca@gmail.com", contraseña 123 y se presiona "Ingresar"
Entonces el sistema inicia la sesion del usuario y redirige a la pagina principal.

escenario 2: inicio fallido por mail inexistente.
Dado un mail "juan@gmail.com" no existente en el sistema.
Cuando se ingresa mail "juan@gmail.com", contraseña 321 y se presiona "Ingresar".
Entonces el sistema informa "Los datos ingresados son incorrectos"

escenario 3: inicio fallido por contraseña no coincidente.
Dado un mail "facundo@gmail.com" registrado en el sistema y una contraseña 222 no coincidente en el sistema con el mail "facundo@gmail.com"
Cuando se ingresa mail "facundo@gmail.com", contraseña 222 y se presiona "Ingresar"
Entonces el sistema informa "Los datos ingresados son incorrectos".

----------------------------

id: cerrar sesion
título: como encargado del mobiliario quiero cerrar sesion para salir del sistema.
reglas de negocio: -
criterios de aceptacion (cerrar sesion)

escenario 1: cierre exitoso.
Dado el mail "luca@gmail.com" autenticado en el sistema.
Cuando se presiona "Cerrar sesión"
Entonces el sistema cierra la sesión y redirige a la pagina de inicio de sesión.

----------------------

id: Cargar mobiliario.
Título: Como encargado de mobiliario quiero cargar un mueble para publicarlo.
Reglas de negocio:
- Códigos de inventario univocos.
Criterios de aceptacion(cargar mobiliario)

Escenario 1: Carga exitosa.
Dado un código de inventario 111 no cargado en el sistema.
Cuando se ingresa código de inventario 111, tipo de mueble "armario", fecha de creación 12/10/2010, fecha de ultimo mantenimiento 15/7/2023, estado "libre", precio 50000 y se presiona "Cargar".
Entonces el sistema carga el mueble en el sistema e informa "Carga exitosa".

Escenario 2: Carga fallida por código repetido.
Dado un código de inventario 222 existente en el sistema.
Cuando se ingresa código de inventario 222, tipo de mueble "cama", fecha de creacion 10/10/2023, fecha de ultimo mantenimiento "17/5/2025", estado "libre", precio $500 y se presiona "Cargar".
Entonces el sistema informa "Ya existe un código igual en el sistema".

----------------------------------------

id: Reservar alquiler
titulo: Como cliente quiero reservar un alquiler para usarlo en un cumpleaños.
reglas de negocio:
- Debe tener mínimo 3 muebles
criterios de aceptación (reservar alquiler)

escenario 1: reserva exitosa.
Dado que se incluyó mobiliario "silla" con cantidad 3 en estado "libre" para la fecha 28/6/2026
Cuando se ingresa fecha 28/6/2026, lugar del evento "casa", mobiliario "silla" cantidad 3 y se presiona "Reservar"
Entonces el sistema marca la reserva como pendiente de pago, actualiza el stock mobiliario en el sistema y redirige al cliente a la pagina de pago.

escenario 2: reserva fallida por falta en cantidad muebles.
Dado que se incluyó un mobiliario "mesa" con cantidad 1 en estado "libre" para la fecha 27/8/2026
Cuando se ingresa fecha 27/8/2026, lugar del evento "sede del estadio x", mobiliario "mesa" con cantidad 1 y se presiona "Reservar"
Entonces el sistema informa "Cantidad mínima de muebles para una reserva es 3"

escenario 3: reserva fallida por mobiliario con falta de stock.
Dado que se incluyó un mobiliario "banquetas" sin stock en estado "libre" para la fecha 24/9/2026
Cuando se ingresa fecha "24/9/2026", lugar del evento "colegio x", mobiliario "banquetas" cantidad 4 y se presiona "Reservar".
Entonces el sistema "Falta de stock en el mobiliario".

-------------------------

id: Realizar pago
título: Como cliente quiero realizar el pago para obtener mi mobiliario.
reglas de negocio: 
- Se debe abonar el 20% del total del alquiler.
- El pago se debe realizar con una tarjeta de crédito.
criterios de aceptacion (realizar pago)

escenario 1: pago exitoso.
Dada una tarjeta de credito 1111 2222 3333 4444 válida y con fondos suficientes para realizar el pago del 20% del total del alquiler, y la conexión con el servidor del banco exitosa
Cuando se ingresa el numero de la tarjeta de credito 1111 2222 3333 4444 y se presiona "Pagar"
Entonces el sistema se conecta al servidor del banco, espera respuesta, recibe la confirmación del pago e informa un numero de reserva unico que será utilizado por el cliente para efectivizar el alquiler.

escenario 2: pago fallido por tarjeta inválida.
Dada una tarjeta de crédito 3333 4444 5555 6666 invalida y la conexion con el servidor del banco exitosa
Cuando se ingresa el numero de tarjeta de credito 3333 4444 5555 6666 y se presiona "Pagar"
Entonces el sistema se conecta al servidor del banco, espera respuesta, recibe error por caso de tarjeta de crédito invalida e informa "La tarjeta de crédito no es valida".

escenario 3: pago fallido por falta de saldo.
Dada una tarjeta de credito 111 válida sin fondos y la conexion con el servidor del banco exitosa.
Cuando se ingresa el nro de tarjeta de credito 111 y se presiona "Pagar"
Entonces el sistema se conecta con el servidor del banco, espera respuesta, recibe error por falta de saldo e informa "Falta de saldo en la tarjeta".

escenario 4: pago fallido por error en la conexion
Dado una conexion con el banco fallida
Cuando se ingresa el nro de tarjeta 222 y se presiona "Pagar"
Entonces el sistema se conecta con el servidor del banco, espera respuesta, recibe error en conexion con el servidor e informa "Error en la conexion con el servidor del banco"