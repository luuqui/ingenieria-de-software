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
Título: Como empleado autenticado quiero cerrar sesión para salir del sistema.
Reglas de negocio. -

Criterios de aceptación (Cerrar sesión):
Escenario 1: Cierre exitoso.
Dado el usuario "luca@gmail.com" que se encuentra autenticado en el sistema.
Cuando se presiona "Cerrar sesión".
Entonces el sistema efectiviza el cierre de sesión y redirige al usuario a la página de inicio de sesión.