Historias de usuario:
- Registrarse.
- Iniciar sesión.
- Inscribir al concurso
- Imprimir listado


==ID: Registrarse.==
Título: Como docente quiero registrarme al sistema para inscribirme a un concurso.
Reglas de negocio:
- Mail debe ser unívoco.
- Dni permitidos aquellos menores a 55millones y mayores a 12millones.
Criterios de aceptación (registrarse).

Escenario 1: Registro exitoso.
Dado un mail "juan@gmail.com" no registrado en el sistema y DNI 30.000.000 menor a 50 millones y mayor a 12 millones.
Cuando se ingresa dni 30.000.000, nombre "Juan", apellido "Gonzales", mail "juan@gmail.com" y se presiona "Registrar".
Entonces el sistema envía a la casilla del mail ingresado una contraseña asignada automáticamente e informa "Registro exitoso".

Escenario 2: Registro fallido por mail existente en el sistema.
Dado un mail "fede@gmail.com" registrado en el sistema.
Cuando se ingresa dni 40.000.000, nombre "Federico", apellido "Fernandez", mail "fede@gmail.com" y se presiona "Registrar".
Entonces el sistema informa "Nombre de usuario ya registrado en el sistema".

Escenario 3: Registro fallido por DNI mayor a 55 millones.
Dado un mail "jose@gmail.com" no registrado en el sistema y DNI 60.000.000 mayor a 60 millones.
Cuando se ingresa DNI 60.000.000, nombre "Jose", apellido "Aguirre", mail "jose@gmail.com" y se presiona "Registrar".
Entonces el sistema informa "DNI mayor a 50 millones".

Escenario 4: Registro fallido por DNI menor a 12 millones.
Dado un mail "luna@gmail.com" no registrado en el sistema y DNI 10.000.000 menor a 12 millones.
Cuando se ingresa DNI 10.000.000, nombre "Luna", apellido "Ferreyra", mail "luna@gmail.com" y se presiona "Registrar".
Entonces el sistema informa "DNI menor a 12 millones"

==ID: Iniciar sesión.==
Título: Como docente quiero iniciar sesión para ingresar al sistema.
Reglas de negocio: -
Criterios de aceptación (iniciar sesión).
Escenario 1: Inicio exitoso.
Dado un mail "fede@gmail.com" registrado en el sistema, contraseña "abc123" coincidente en el sistema.
Cuando se ingresa mail "fede@gmail.com", contraseña "abc123" y se presiona "Ingresar".
Entonces el sistema abre la sesión del usuario y redirige a la página principal.

Escenario 2: Inicio fallido por mail no registrado en el sistema.
Dado un mail "manu@gmail.com" no registrado en el sistema.
Cuando se ingresa el mail "manu@gmail.com" y contraseña "asd123", y se presiona "Ingresar".
Entonces el sistema informa "Datos incorrectos".

Escenario 3: Inicio fallido por contraseña no coincidente.
Dado un mail "luca@gmail.com" registrado en el sistema y contraseña "mnb123" no coincidente en el sistema.
Cuando se ingresa mail "luca@gmail.com" y contraseña "mnb123", y se presiona "Iniciar sesión".
Entonces el sistema informa "Datos incorrectos".

==ID: Cerrar sesión.==
Título: Como docente quiero cerrar sesión para salir del sistema.
Reglas de negocio: -
Criterios de aceptación (cerrar sesión).
Escenario 1: Cierre exitoso.
Dado el usuario "marce@gmail.com" autenticado en el sistema.
Cuando se presiona "Cerrar sesión".
Entonces el sistema cierra la sesión del usuario y redirige a la página de inicio de sesión.

==ID: Inscribir a un concurso.==
Título: Como docente quiero inscribirme a un concurso para dar clases.
Reglas de negocio:
- No se podrá estar inscripto a más de 3 concursos.
Criterios de aceptación (inscribir a un concurso).

Escenario 1: Inscripción exitosa.
Dado el docente con mail "luca@gmail.com" con 1 concurso registrado en el sistema.
Cuando seleccione la materia "Inglés" y se presione "Aceptar".
Entonces el sistema realiza la inscripción, informa "Inscripción aceptada" e imprime un comprobante.

Escenario 2: Inscripción fallida por limite superado.
Dado el docente con mail "juan@gmail.com" con 3 concursos registrados en el sistema.
Cuando seleccione la materia "Matemática" y presione "Aceptar"
Entonces el sistema informa "Limite de concursos alcanzado".

==ID: Imprimir listado.==
Título: Como jefe de área de concursos quiero imprimir un listado para enviar un listado al secretario administrativo.
Reglas de negocio: -
Criterios de aceptación (imprimir listado).

Escenario 1: Impresión exitosa.
Dado una materia "Matemática" que cuenta con inscriptos.
Cuando se presiona "Imprimir".
Entonces el sistema realiza una impresión con todos los inscriptos de la materia.

Escenario 2: Impresión fallida por falta de inscriptos.
Dado la materia "Inglés" que no cuenta con inscriptos.
Cuando se presiona "Imprimir".
Entonces el sistema informa "La materia no cuenta con inscriptos".
