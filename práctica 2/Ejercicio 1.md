ROL DE USUARIOS:
- Encargado.
- Cliente.
HISTORIAS DE USUARIO:
- Iniciar sesión.
- Cerrar sesión.
- Registrar mueble.
- Reservar alquiler.
- Pagar con tarjeta.

ID. Iniciar Sesión
Título. Como encargado quiero iniciar sesión para ingresar al sistema.
Reglas de negocio. -

Criterios de aceptación (Iniciar sesión).
Escenario 1: Inicio de sesión exitoso.
Dado que el nombre de usuario "luca@gmail.com" se encuentra registrado en el sistema y la contraseña "1234" coincide con la del usuario
Cuando se ingrese el nombre de usuario "luca@gmail.com" y la contraseña "1234" y, se presiona "Iniciar sesión"
Entonces el sistema abre la sesión del usuario y se redirige a la página principal.

Escenario 2: Inicio de sesión fallido por usuario inexistente.
Dado que el nombre de usuario "lucas@gmail.com" no se encuentra registrado en el sistema.
Cuando se ingresa el nombre de usuario "lucas@gmail.com" y la contraseña "1234", y se presiona "Iniciar sesión"
Entonces el sistema informa "Datos incorrectos".

Escenario 3: Inicio de sesión fallido por contraseña incorrecta.
Dado que el nombre de usuario "luca@gmail.com" se encuentra registrado en el sistema y la contraseña "234" no coincide con el usuario.
Cuando se ingresa el nombre de usuario "luca@gmail.com" y la contraseña "234", y se presiona "Iniciar sesión"
Entonces el sistema informa "Datos incorrectos".

ID. Cerrar sesión.
Título. Como encargado quiero cerrar sesión para salir del sistema.
Reglas de negocio: -

Criterios de aceptación (Cerrar sesión).
Escenario 1: Cierre de sesión exitoso.
Dado el usuario "luca@gmail.com" con la sesión abierta.
Cuando se presiona "Cerrar sesión".
Entonces el sistema cierra la sesión y redirige a la pantalla de inicio de sesión.

ID. Registrar mueble.
Título. Como encargado quiero registrar un mueble para darlo de alta en el sistema.
Reglas de negocio.
- El código de inventario debe ser unívoco. 

Criterios de aceptación (Registrar mueble).
Escenario 1: Registro de mueble exitoso.
Dado el mueble "cama" con código 444 donde no se encuentra en el sistema.
Cuando se ingresa código 444, tipo de mueble "cama", fecha de creación 10/10/2025
, fecha de ultimo mantenimiento 2/3/2026, estado "libre" y precio "100" y, se presiona "Registrar".
Entonces el sistema registra el mueble e informa "Registro exitoso del mueble".

Escenario 2: Registro fallido porque el mueble ya está registrado.
Dado el mueble "Estante" con código 111 que se encuentra registrado en el sistema.
Cuando se ingresa el código 111, tipo de mueble "Estante", fecha de creación 2/2/2024,
fecha de ultimo mantenimiento 5/10/2025, estado "libre" y precio 200 y, se presiona "Registrar".
Entonces el sistema informa "El mueble ya se encuentra registrado".

ID. Reservar alquiler.
Título. Como usuario quiero reservar un alquiler para un evento.
Reglas de negocio.
- La reserva debe tener mínimo 3 muebles.

Criterios de aceptación (Reservar alquiler)
Escenario 1: Reserva exitosa.
Dado los muebles "silla", "mesa", "cama" y "escritorio" que tienen stock, la cantidad de muebles 4 es mayor a 3, se encuentran disponibles y las condiciones de pago son las adecuadas.
Cuando se ingresa fecha 29/8/2026, lugar del evento "casita feliz", cantidad de días 1, nombre del mobiliario "Luca" y cantidad 4, y se presiona "Aceptar".
Entonces el sistema redirige al usuario al pago de reserva con tarjeta de crédito, espera respuesta, lleva a cabo la reserva y actualiza el stock disponible de muebles.

Escenario 2: Reserva fallida por falta en la cantidad de muebles.
Dado los muebles "silla" y "mesa" que tienen stock, la cantidad de muebles 2 es menor a 3.
Cuando se ingresa la reserva con fecha 4/7/2026, lugar del evento "La Plata", cantidad de días 1, nombre del mobiliario "Facundo" y cantidad 2, y se presiona "Aceptar".
Entonces el sistema informa "La cantidad de muebles es inválida".

Escenario 3: Reserva fallida por falta de stock en muebles.
Dados los muebles "silla", "cama", "mesa" y "escritorio", y no hay stock de muebles.
Cuando se ingresa la reserva con fecha 2/5/2026, lugar del evento "La Plata", cantidad de días 1, nombre del mobiliario "Juan" y cantidad 4, y se presiona "Aceptar".
Entonces el sistema informa "Falta de stock en muebles requeridos".

Escenario 4: Reserva fallida por error en el pago.
Dado que se incluyeron 3 muebles, hay stock de los mismos y las condiciones no son las adecuadas para un pago exitoso.
Cuando se ingresa la reserva con fecha 7/9/2026, lugar del evento "La Plata", cantidad de días 1, nombre del mobiliario "Isaías" y cantidad 3, y se presiona "Aceptar".
Entonces el sistema redirige al usuario al pago con tarjeta de crédito, espera respuesta e informa "Hubo error en el pago por lo que no se pudo llevar a cabo la reserva".

ID. Pagar con tarjeta
Título. Como usuario quiero pagar con tarjeta para realizar una reserva.
Reglas de negocio:
- Se debe abonar el 20% del pago del alquiler.
- Solo se aceptan números correspondientes a tarjetas de crédito.

Criterios de aceptación (Pagar con tarjeta).
Escenario 1: Pago exitoso.
Dado que la conexión con el banco es exitosa, el número 1234 corresponde a una tarjeta de crédito válida y la tarjeta tiene saldo suficiente para abonar el 20% del pago.
Cuando se ingresa el numero de tarjeta 1234 y se presiona "Pagar".
Entonces el sistema registra el pago y retorna un resultado exitoso.

Escenario 2: Pago fallido por falla de conexión con el servidor.
Dado que no se pudo establecer conexión con el servidor del banco.
Cuando se intenta realizar el pago.
Entonces el sistema informa "No se pudo establecer la conexión con el servidor".

Escenario 3: Pago fallido por número de tarjeta inexistente.
Dado que la conexión con el banco es exitosa y el numero 234 no corresponde a una tarjeta de crédito válida.
Cuando se ingresa el numero de tarjeta 234 y se presiona "Pagar"
Entonces el sistema informa "El número no corresponde a una tarjeta de crédito existente".

Escenario 4: Pago fallido por saldo insuficiente.
Dado que la conexión con el banco es exitosa, el numero 456 corresponde a una tarjeta de crédito existe y no posee un saldo suficiente para pagar el 20% de la reserva.
Cuando se ingresa el numero de tarjeta 456 y se presiona "Pagar".
Entonces el sistema informa "Saldo de tarjeta insuficiente".