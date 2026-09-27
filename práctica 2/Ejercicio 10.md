id: registrarse
titulo: como persona quiero registrarme para solicitar un turno
reglas de negocio
- Solo pueden registrarse personas de 18 años o más.
criterios de aceptacion (registrarse)

escenario 1: registro exitoso
Dado un mail "xx" no registrado en el sistema y una edad 20 mayor a 18
Cuando se ingresa nombre "xx", apellido "xx", mail "xx", edad "xx", domicilio "xx" y se presiona "Registrarse"
Entonces el sistema genera una contraseña que es enviada al correo ingresado e informa "Registro exitoso".

escenario 2: registro fallido por persona menor de edad
Dado un mail "xx" no registrado en el sistema y una edad 17 menor a 18
Cuando se ingresa nombre "xx", apellido "xx", mail "xx", edad "xx", domicilio "xx" y se presiona "Registrarse"
Entonces el sistema informa "Debe ser mayor a 18 años"

escenario 3: registro fallido por mail registrado en el sistema
Dado un mail "xx" registrado en el sistema
Cuando se ingresa nombre "xx", apellido "xx", mail "xx", edad "xx", domicilio "xx" y se presiona "Registrarse"
Entonces el sistema informa "Usuario ya registrado en el sistema"

------------

id: iniciar sesion
titulo: como usuario quiero iniciar sesion para solicitar un turno
reglas de negocio
- Al fallar 3 veces en el inicio de sesión se bloquea la cuenta.
criterios de aceptacion (iniciar sesion)

escenario 1: inicio exitoso
Dado un mail "xx" registrado en el sistema, una contraseña "xx" coincidente con el mail "xx" en el sistema y 1 intento fallido registrado en el sistema para iniciar sesión.
Cuando se ingresa mail "xx", contraseña "xx" y se presiona "Iniciar sesión".
Entonces el sistema abre la sesión y redirige al usuario a la pagina principal.

escenario 2: inicio fallido por contraseña erronea con bloqueo de cuenta.
Dado un mail "xx" registrado en el sistema, una contraseña "xx" no coincidente con el mail "xx" en el sistema y 2 intentos fallidos registrados en el sistema para iniciar sesión.
Cuando se ingresa mail "xx", contraseña "xx" y se presiona "Iniciar sesión".
Entonces el sistema registra 1 intento fallido en el sistema, bloquea la cuenta e informa "Datos incorrectos. Cuenta bloqueada".

escenario 3: inicio fallido por contraseña erronea con intentos disponibles.
Dado un mail "xx" registrado en el sistema, una contraseña "xx" no coincidente con el mail "xx" en el sistema y 1 intento fallido registrado en el sistema para iniciar sesión.
Cuando se ingresa mail "xx", contraseña "xx" y se presiona "Iniciar sesión".
Entonces el sistema registra 1 intento fallido en el sistema e informa "Datos incorrectos".

escenario 4: inicio fallido por bloqueo de cuenta
Dado un mail "xx" con bloqueo de cuenta registrado en el sistema.
Cuando se ingresa mail "xx", contraseña "xx" y se presiona "Iniciar sesión".
Entonces el sistema informa "Cuenta ingresada bloqueada".

escenario 5: inicio fallido por mail no registrado en el sistema
Dado un mail "xx" no registrado en el sistema.
Cuando se ingresa mail "xx", contraseña "xx" y se presiona "Iniciar sesión".
Entones el sistema informa "Datos incorrectos".

-------------

id: cerrar sesión
titulo: como usuario quiero cerrar sesión para salir del sistema.
reglas de negocio: -
criterios de aceptacion (cerrar sesion)

escenario 1: cierre de sesion exitoso
Dado un mail "xx" con la sesión iniciada en el sistema.
Cuando se presiona "Cerrar sesión".
Entonces el sistema cierra la sesión del sistema y redirige a la pagina de inicio de sesión.

----------------------

id: solicitar turno
titulo: como usuario quiero solicitar un turno para ir a jugar.
reglas de negocio:
- Los turnos solicitados no puede ser mayores a 2 días desde el día que se solicitó.
criterios de aceptacion (solicitar turno)

escenario 1: solicitud exitosa.
Dada la fecha actual 26/9/2026, la cancha "Nadal" que se encuentra libre en la fecha 27/9/2026, hora 17:00pm siendo menor a 2 días desde el día que se solicita.
Cuando se ingresa cancha "Nadal", fecha 27/9/2026, hora 17:00pm y se presiona "Solicitar"
Entonces el sistema registra la cancha como ocupada en la fecha y hora ingresada e informa "Su turno ha sido registrado con éxito".

escenario 2: solicitud fallida por cancha ocupada.
Dada la fecha actual 26/9/2026, la cancha "Federer" que se encuentra ocupada en la fecha 27/9/2026, hora 13:00pm.
Cuando se ingresa cancha "Federer", fecha "27/9/2026", hora 13:00pm y se presiona "Solicitar".
Entonces el sistema informa "Cancha ocupada, por favor seleccione otro día y horario".

escenario 3: solicitud fallida por fecha ingresada mayor a 2 días desde el día actual.
Dada la fecha actual 26/9/2026, la cancha "Sinner" que se encuentra libre en la fecha 30/9/2026, hora 13:00pm siendo mayor a 2 días desde el día que se solicita.
Cuando se ingresa cancha "Sinner", fecha "27/9/2026", hora 13:00pm y se presiona "Solicitar".
Entonces el sistema informa "Los turnos solicitados solo pueden ser mayor a 2 días desde la fecha actual".

