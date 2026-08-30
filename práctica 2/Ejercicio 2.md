ROL DE USUARIOS:
- Usuario
- Conserje
Historias de usuario:
- Reservar hospedaje
- Realizar check-in
- Realizar check-out

ID. Reservar hospedaje.
Título: Como usuario quiero reservar un hospedaje para hospedarme en el hotel.
Reglas de negocio:
- La fecha de ingreso debe estar dentro de los 90 días a partir de la fecha actual.
- La estadía tiene un límite de 15 días máximo.

Criterios de aceptación (Reservar hospedaje).

Escenario 1: Reserva exitosa.
Dada la fecha de ingreso 10/8/2026 que está dentro de los 90 días a partir de la fecha actual, fecha de egreso 15/8/2026 con duración de 5 días de estadía que no es superior a 15 días y cantidad de personas 4 para los cuales hay habitación disponible.
Cuando se ingresa la reserva con fecha de ingreso 10/8/2026, fecha de egreso 15/8/2026, hotel "Hotel La Plata", cantidad de personas 4 y se presiona "reservar".
Entonces el sistema registra la reserva, marca la habitación como ocupada en el rango de fechas ingresado, envía un correo electrónico con un código de reserva y un enlace para continuar con el pago.

Escenario 2: Reserva fallida por fecha de ingreso fuera de los próximos 90 días.
Dada la fecha de ingreso 7/7/2026 que no se encuentra dentro de los próximos 90 días desde la fecha actual.
Cuando se ingresa la reserva con fecha de ingreso 7/7/2026, fecha de egreso 10/7/2026, hotel "El gran hotel", cantidad de personas 3 y se presiona "reservar".
Entonces el sistema informa "La fecha de ingreso se encuentra por fuera de los próximos 90 días".

Escenario 3: Reserva fallida por estadía superior a 15 días.
Dada la fecha de ingreso 10/8/2026 que se encuentra dentro de los próximos 90 días desde la fecha actual, fecha de egreso 30/8/2026 con duración de estadía 20 que supera el limite de estadías de 15 días.
Cuando se ingresa la reserva con fecha de ingreso 10/8/2026, fecha de egreso 30/8/2026, hotel "tu hotel", cantidad de personas 2 y se presiona "reservar".
Entonces el sistema informa "La duración de la estadía se encuentra fuera del límite de 15 días".

Escenario 4: Reserva fallida por falta de disponibilidad en habitaciones.
Dada la fecha de ingreso 11/8/2026 que está dentro de los 90 días a partir de la fecha actual, fecha de egreso 14/8/2026 con duración de 3 días de estadía que no es superior a 15 días y cantidad de personas 3 para los cuales no hay habitación disponible.
Cuando se ingresa la reserva con fecha de ingreso 11/8/2026, fecha de egreso 14/8/2026, hotel "el hotel abc", cantidad de personas 1 y se presiona "reservar".
Entonces el sistema informa "No hay habitaciones disponibles".

ID. Realizar check-in,
Título. Como usuario quiero realizar el check-in para ingresar a la habitación.
Reglas de negocio:
- Solo se pueden realizar en el rango horario de 10am hasta 23:59pm.

Criterios de aceptación (Realizar check-in)
Escenario 1. Check-in exitoso.
Dado un horario actual dentro del rango 10am-23:59pm, un codigo de reserva 123 existente en el sistema y la reserva realizada para la fecha actual en la habitación 2.
Cuando se ingresa a la terminal el código 123 y presiona "Aceptar".
Entonces el sistema informa la habitación asignada, envía un mensaje a un conserje para guiar al usuario a la habitación y envía un mensaje a los botones para informar el encargo de la valijas.

Escenario 2. Check-in fallido por horario actual fuera del rango 10am - 23:59pm.
Dado un horario actual 8:30am fuera del rango 10am - 23:59pm
Cuando se ingresa a la terminal el código 234 y presiona "Aceptar".
Entonces el sistema informa "Aún no se encuentras habilitados los ingresos al hotel".

Escenario 3. Check-in fallido por código inexistente.
Dado un horario actual dentro del rango 10am-23:59pm y un código de reserva 234 inexistente en el sistema.
Cuando se ingresa a la terminal el código 234 y presiona "Aceptar".
Entonces el sistema informa "Código inexistente".

ID. Realizar check out
Título. Como conserje quiero realizar el check out para liberar una habitación.
Reglas de negocio:
- Los gastos de la habitación deben estar pagos.

Criterios de aceptación (Realizar check out)
Escenario 1: Check out exitoso.
Dado un numero de habitación 2 que está ocupada y que no tiene gastos pendientes.
Cuando se ingresa el numero de habitación 2 y presiona "Aceptar"
Entonces el sistema efectiviza el check out, marca la habitación como libre y envía un mensaje a las mucamas avisando que la habitación puede limpiarse.

Escenario 2: Check out fallido por gastos pendientes.
Dado un numero de habitación 3 que está ocupada y que tiene gastos pendientes.
Cuando se ingresa el numero de habitación 3 y presiona "Aceptar".
Entonces el sistema informa "Se deben abonar los gastos pendientes".