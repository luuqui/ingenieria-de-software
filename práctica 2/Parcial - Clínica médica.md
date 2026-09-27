Solicitar un turno
Ver turnos

id: Solicitar un turno
titulo: como paciente quiero solicitar un turno para revisarme.
reglas de negocio:
- solo está permitido un turno de especialidad por semana.
- los pacientes deben ser mayor a 18 años.

criterios de aceptacion (solicitar un turno):

Escenario 1: Solicitud exitosa.
Dado el mail "luca@gmail.com" con 20 años de edad mayor a 18 que no presenta turnos solicitados en la semana del 21/9/2026 al 27/9/2026 para la especialidad kinesiología y el médico de Kinesiología "Juan Pérez" que presenta 1 turno disponible el día 23/9/2026 hora 9:00am.
Cuando se selecciona especialidad "Kinesiología", médico "Juan Pérez", día 23/9/2026, hora 9:00 am y se presiona "Solicitar".
Entonces el sistema registra el turno, marca al médico como ocupado en el día y hora seleccionado e informa "Solicitud exitosa".

Escenario 2: Solicitud fallida por turno ya registrado.
Dado el mail "juan@gmail.com" que presenta un turno solicitado en la semana del 19/9/2026 al 25/9/2026 para la especialidad dermatología.
Cuando se selecciona especialidad "Dermatología", médico "Ignacio Martinez", día 23/9/2026, hora 18:00pm y se presiona "Solicitar".
Entonces el sistema informa "Ya se encuentra registrado un turno en la semana del día seleccionado".

Escenario 3: Solicitud fallida por menor a 18 años.
Dado el mail "pablo@gmail.com" de 17 años de edad menor a 18 años.
Cuando se selecciona especialidad "Pediatría", médico "Alberto Ferreyra", día 18/8/2026, hora 14:00 pm y se presiona "Solicitar".
Entonces el sistema informa "Se debe ser mayor a 18 años para solicitar un turno".

Escenario 4: Solicitud fallida por error en el turno.
Dado el médico de gastroenterología "Diego Fernandez" que no presenta turnos disponibles el día 18/9/2026 hora 15:00pm.
Cuando se selecciona especialidad "Gastroenterología", médico "Diego Fernandez", día 18/9/2026, hora 15:00pm y se presiona "Solicitar".
Entonces el sistema informa "Solicitud de turno no disponible".

Escenario 5: Solicitud fallida por especialidad de medico incorrecta.
Dado el medico oculista "Anibal Moreno".
Cuando se selecciona especialidad "kinesiología", médico "Anibal Moreno", día 19/9/2026, hora 7:00pm y se presiona "Solicitar".
Entonces el sistema informa "Error en la especialidad del médico".


id: solicitar listado de turnos
título: como médico quiero ver mis turnos para recordarlos.
reglas de negocio:
- solo se puede ingresar fechas del corriente año.
criterios de aceptación (ver turnos)
escenario 1: solicitud de listado exitosa con turnos.
Dado el mail "luca@gmail.com", la fecha 21/7/2026 correspondiente al corriente año con turnos activos en la fecha misma.
Cuando se ingresa la fecha 21/7/2026 y se presiona "Listar".
Entonces el sistema informa un listado con los turnos correspondientes a la fecha.

escenario 2: solicitud de listado sin turnos.
Dado el mail "juan@gmail.com", la fecha 25/9/2026 correspondiente al corriente año sin turnos activos en la fecha misma.
Cuando se ingresa la fecha 25/9/2026 y se presiona "Listar".
Entonces el sistema informa "No hay turnos disponibles para la fecha".

escenario 3: solicitud fallida por fecha de otro año.
Dada la fecha 2/5/2027 no correspondiente al corriente año.
Cuando se ingresa fecha 2/5/2026 y se presiona "Listar".
Entonces el sistema informa "Año no correspondiente al actual".

