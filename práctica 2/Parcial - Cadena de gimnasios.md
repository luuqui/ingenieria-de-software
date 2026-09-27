id: reservar turno
titulo: como socio quiero reservar un turno para entrenar
reglas de negocio:
- Se debe tener cuota al día.
criterios de aceptación (reservar turno)

escenario 1: reserva exitosa.
Dado un mail "xx" con la cuota al día registrado en el sistema, una sede "xx" existente en el sistema, un tipo de clase "yoga" válido y, un día "martes" y hora 17:00pm coincidente con la clase ingresada.
Cuando se ingresa nombre de la sede "xx", tipo de clase "xx", dia "martes", hora 17:00pm y se presiona "Reservar"
Entonces el sistema informa "Reserva exitosa".

escenario 2: reserva fallida por cuota impaga.
Dado un mail "xx" con la cuota sin estar al día registrado en el sistema.
Cuando se ingresa nombre de la sede "xx", tipo de clase "xx", dia "martes", hora 17:00pm y se presiona "Reservar"
Entonces el sistema informa "Reserva fallida por cuota impaga".

escenario 3: reserva fallida por sede inexistente.
Dado un mail "xx" con la cuota al día registrado en el sistema y una sede "xx" no existente en el sistema.
Cuando se ingresa nombre de la sede "xx", tipo de clase "xx", dia "martes", hora 17:00pm y se presiona "Reservar".
Entonces el sistema informa "Sede ingresada inválida".

escenario 4: reserva fallida por tipo de clase inválido.
Dado un mail "xx" con la cuota al día registrado en el sistema, una sede "xx" no existente en el sistema y un tipo de clase no válido en el sistema.
Cuando se ingresa nombre de la sede "xx", tipo de clase "Beisbol", dia "martes", hora 17:00pm y se presiona "Reservar".
Entonces el sistema informa "Tipo de clase no válida".

escenario 5: Dado un mail "xx" con la cuota al día registrado en el sistema, una sede "xx" existente en el sistema, un tipo de clase "yoga" válido y, un día "lunes" y hora 14:00pm no coincidente con la clase ingresada.
Cuando se ingresa nombre de la sede "xx", tipo de clase "Beisbol", dia "lunes", hora 14:00pm y se presiona "Reservar".
Entonces el sistema informa "Día y hora no coincidente con alguna clase".

---------------------

id: cancelar un turno
titulo: como socio quiero cancelar un turno para no ir
reglas de negocio:
- Solo se puede cancelar si queda más de 1 hora para iniciar la clase.
criterios de aceptacion (cancelar un turno)

escenario 1: cancelación exitosa
Dado una fecha actual 25/9/2026 "martes", hora 15:00pm y una clase de yoga en día 25/9/2026, hora 18:00pm faltando más de 1 hora para el inicio de la clase.
Cuando se ingresa día "martes", hora 18:00pm y se presiona "Cancelar".
Entonces el sistema cancela el turno e informa "Solicitud aceptada".

escenario 2: cancelación fallida por quedar menor de 1 hora para el inicio.
Dado una fecha actual 25/9/2026 "martes", hora 15:00pm y una clase de yoga en día 25/9/2026, hora 15:30pm faltando menos de 1 hora para el inicio de la clase.
Cuando se ingresa día "martes", hora 15:30pm y se presiona "Cancelar"..
Entonces el sistema informa "Se debe pedir la cancelación con 1 hora de antelación".

