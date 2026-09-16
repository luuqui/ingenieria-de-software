Roles
- Empleado
- Administrativo
Historias de usuario
- Registrarse
- Iniciar sesión
- Cerrar sesión
- Solicitar licencia
- Consultar licencia

Id: Registrarse.
Título: Como empleado de la PBA quiero registrarme en el sistema para pedir una licencia.
Id: Registrarse
Reglas de negocio: -

Criterios de aceptación (Registrarse):
Escenario 1: Registro exitoso.
Dado el CUIL "1234" no registrado en el sistema y el mail "luca@gmail.com" que no se encuentra registrado en el sistema.
Cuando se ingresa CUIL "1234", mail "luca@gmail.com", contraseña "abc" y, se presiona "Aceptar".
Entonces el sistema informa "Registro exitoso" y efectiviza el registro.

Escenario 2: Registro fallido por CUIL registrado en el sistema.
Dado el CUIL "4321" registrado en el sistema.
Cuando se ingresa CUIL "4321", mail "juan@gmail.com", contraseña "zxc" y se presiona "Aceptar".
Entonces el sistema informa "El CUIL ya se encuentra registrado en el sistema".

Escenario 3: Registro fallido por mail registrado en el sistema.
Dado el CUIL "456" no registrado en el sistema y el mail "luca@gmail.com" que se encuentra registrado en el sistema.
Cuando se ingresa CUIL "456", mail "luca@gmail.com", contraseña "mnb" y se presiona "Aceptar".
Entonces el sistema informa "El mail ya se encuentra registrado en el sistema".


//preguntas:
se utiliza contraseña? 
En el dado, se pone "dado un usuario autenticado o dado un usuario?"

Id: Iniciar sesión.
Título: Como empleado quiero iniciar sesión para acceder al sistema.
Reglas de negocio: -

Criterios de aceptación (Iniciar sesión):
Escenario 1: Inicio de sesión exitoso.
Dado un mail "luca@gmail.com" registrado en el sistema, un CUIL "1234" registrado en el sistema y la contraseña "abc" coincidente con el mail ingresado.
Cuando se ingresa mail "luca@gmail.com", CUIL "1234", contraseña "abc" y se presiona "Iniciar sesión".
Entonces el sistema informa "Sesión aceptada", redirige a la pagina principal y efectiviza la autenticación.

Escenario 2: Inicio de sesión fallido por mail no registrado en el sistema.
Dado un mail "pablo@gmail.com" no registrado en el sistema.
Cuando se ingresa mail "pablo@gmail.com", CUIL "890", contraseña "mnb" y se presiona "Iniciar sesión".
Entonces el sistema informa "Datos incorrectos".

Escenario 3: Inicio de sesión fallido por CUIL no registrado en el sistema.
Dado un mail "jose@gmail.com" registrado en el sistema y un CUIL "456" no registrado en el sistema.
Cuando se ingresa mail "jose@gmail.com", CUIL "456" y contraseña "vbn" y, se presiona "Iniciar sesión".
Entonces el sistema informa "CUIL ingresado no registrado en el sistema".
//aca se especifica cuil no registrado en el sistema o se pone datos incorrectos? 

Escenario 4: Inicio de sesión fallido por contraseña incorrecta.
Dado un mail "maria@gmail.com" registrado en el sistema, un CUIL "678" registrado en el sistema y una contraseña "asd" no coincidente con el mail ingresado.
Cuando se ingresa mail "maria@gmail.com", CUIL "678", contraseña "asd" y se presiona "Iniciar Sesión".
Entonces el sistema informa "Datos incorrectos".

Id: Cerrar sesión.
Título: Como usuario autenticado quiero cerrar sesión para salir del sistema.
Reglas de negocio. -

Criterios de aceptación (Cerrar sesión):
Escenario 1: Cierre exitoso.
Dado el usuario "luca@gmail.com" que se encuentra autenticado en el sistema.
Cuando se presiona "Cerrar sesión".
Entonces el sistema efectiviza el cierre de sesión y redirige al usuario a la página de inicio de sesión.

Id: Solicitar licencia.
Título: Como usuario del sistema quiero solicitar una licencia para descansar.
Reglas de negocio:
- Solicitudes permitidas a usuarios con más de 1 mes de antigüedad.
- El usuario solo puede solicitar una licencia como máximo por vez.
Criterios de aceptación (Solicitar licencia):

Escenario 1: Solicitud exitosa.
Dado un usuario autenticado en el sistema "luca@gmail.com" con 10 meses de antigüedad y sin licencias activas en el sistema.
Cuando se ingresa tipo de licencia "presencial", fecha de inicio de reposo "10/10/2026", matrícula de médico personal 456, diagnóstico "un diagnostico...", personal o familiar "personal" y se presiona "Solicitar".
Entonces el sistema genera un código de licencia, lo envía al mail del usuario con la confirmación y los días otorgados y, informa "Solicitud generada con éxito".

Escenario 2: Solicitud fallida por falta de antiguedad.
Dado un usuario autenticado en el sistema "juan@gmail.com" con 10 días de antiguedad.
Cuando se ingresa tipo de licencia "presencial", fecha de inicio de reposo "20/10/2026", matrícula de médico personal 123, diagnóstico "un diagnostico...", personal o familiar "personal" y se presiona "Solicitar".
Entonces el sistema informa "Debe poseer más de 1 mes de antiguedad para solicitar licencias".

Escenario 3: Solicitud fallida por solicitudes existentes en el sistema.
Dado un usuario autenticado en el sistema "pablo@gmail.com" con una licencia activa en el sistema.
Cuando se ingresa tipo de licencia "presencial", fecha de inicio de reposo "7/7/2026", matrícula de médico personal 980, diagnóstico "un diagnostico...", personal o familiar "personal" y se presiona "Solicitar".
Entonces el sistema informa "Usted ya posee una licencia activa."

ID: Consultar licencia.
Título: Como administrador quiero consultar licencias para realizar una estadística.
Reglas de negocio:
- Se podrá imprimir un informe por mes para cada empleado.
Criterios de aceptación(Consultar licencia).

Escenario 1: Consulta exitosa.
Dado el CUIL 999 perteneciente a un empleado del sistema, que no tiene un informe impreso en el mes
Cuando se ingresa el CUIL 999, rango de fechas "10/10/2026"  - "25/10/2026" y se presiona "Consultar"
Entonces el sistema imprime el informe de las licencias solicitadas.

Escenario 2: Sin licencias exitoso.

Escenario 3: Consulta fallida por informe ya impreso en el mes.
Dado el CUIL 111 perteneciente a un empleado del sistema, que tiene un informe impreso en el mes.
Cuando se ingresa el CUIL 111, rango de fechas "8/8/2025" - "10/10/2025" y se presiona "Consultar"
Entonces el sistema informa "Limite de informes impresos por mes superado.".

Escenario 4: Consulta fallida por CUIL inexistente en el sistema.
Dado el CUIL 777 no perteneciente un empleado del sistema.
Cuando se ingresa el CUIL 777, rango de fechas "10/10/2026" - "20/10/2026" y se presiona "Consultar"
Entonces el sistema informa "CUIL inexistente en el sistema".

