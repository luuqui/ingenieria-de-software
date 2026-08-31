Roles
- Cliente (Usuario no registrado)
- Usuario
Historias de usuario
- Registrar usuario
- Iniciar sesión
- Cerrar sesión
- Seleccionar bebida

ID. Registrar usuario
Título. Como cliente quiero registrarme para comprar bebidas.
Reglas de negocio: 
- Mail debe ser unívoco
- Edad mayor a 18 años

Criterios de aceptación (Registrar usuario)
Escenario 1: Registro exitoso.
Dado el mail "luca@gmail.com" que no se encuentra registrado en el sistema y la edad 23 es superior a 18
Cuando se ingresa nombre "Luca", apellido "Ferreyra", usuario "luca@gmail.com" y edad 23 y, se presiona "Registrarse".
Entonces el sistema genera una contraseña que es enviada al email, efectiviza el registro e informa "Registro exitoso".

Escenario 2: Registro fallido por existencia del mail en el sistema.
Dado el usuario "facu@gmail.com" que ya se encuentra en el sistema
Cuando se ingresa nombre "Facundo", apellido "Gerli", usuario "facu@gmail.com" y edad 22 y, se presiona "Registrarse"
Entonces el sistema informa "El mail ya existe en el sistema".

Escenario 3: Registro fallido por edad insuficiente.
Dado el usuario "juan@gmail.com" que no se encuentra en el sistema y una edad de 17 menor a 18
Cuando se ingresa nombre "Juan", apellido "unApe", usuario "juan@gmail.com" y edad 22 y, se presiona "Registrarse"
Entonces el sistema informa el texto de la ley que impide la venta de bebidas alcohólicas a menores.

ID. Iniciar Sesión
Título. Como usuario quiero iniciar sesión para ingresar a la pagina.
Reglas de usuario: -
Criterios de aceptación (Iniciar sesión)
Escenario 1: Inicio de sesión exitoso.
Dado el usuario "luca@gmail.com" ya existente en el sistema y la contraseña "123" coincidente con el mismo
Cuando se ingresa el usuario "luca@gmail.com", contraseña "123" y, se presiona "Ingresar"
Entonces el sistema efectiviza el inicio de sesión y redirige a la pagina principal mostrando las bebidas alcohólicas.

Escenario 2: Inicio de sesión fallido por usuario inexistente.
Dado el usuario "alguien@gmail.com" inexistente en el sistema
Cuando se ingresa usuario "alguien@gmail.com" y contraseña "234" y, se presiona "Ingresar"
Entonces el sistema informa "Datos incorrectos".

Escenario 3: Inicio de sesión fallido por contraseña incorrecta.
Dado el usuario "otro@gmail.com" existente en el sistema y la contraseña "456" no coincidente con el usuario
Cuando se ingresa nombre de usuario "otro@gmail.com" y contraseña "456" y, se presiona "Ingresar"
Entonces el sistema informa "Datos incorrectos".

ID. Cerrar sesión.
Título. Como usuario quiero cerrar sesión para salir del sistema.
Reglas de negocio: -
Criterios de aceptación (Cerrar sesión)
Escenario 1: Cierre de sesión exitoso.
Dado el usuario "luca@gmail.com" con la sesión abierta
Cuando se presiona "Cerrar sesión"
Entonces el sistema cierra la sesión del usuario y redirige a la pagina de inicio de sesión.

ID. Seleccionar bebida.
Título. Como usuario quiero seleccionar bebidas para conocer monto final.
Reglas de negocio:
- Usuarios premium tienen 20% de descuento
- Compras con monto superior a los $4500 tienen 10% de descuento
- Usuarios premium con montos de compra superior a $4500 tienen descuento del 30%.
Criterios de aceptación (Seleccionar bebida)
Escenario 1: Selección exitosa sin descuentos.
Dado el usuario "luca@gmail.com" no premium, una compra de "Cerveza" con valor $2000 inferior a $4500 y stock disponible de la bebida "Cerveza"
Cuando se selecciona la bebida "Cerveza" con monto total $2000 y se presiona "Aceptar"
Entonces el sistema informa en pantalla el monto total.

Escenario 2: Selección exitosa con descuento del 20%.
Dado el usuario "juan@gmail.com" que es premium, una compra de "Gancia" con valor $1000 inferior a $4500 y hay stock disponible de la bebida "Gancia"
Cuando se selecciona la bebida "Gancia" con monto total $1000 y se presiona "Aceptar"
Entonces el sistema informa en pantalla el monto total y el monto total con 20% de descuento aplicado.

Escenario 3: Selección exitosa con descuento del 10%
Dado el usuario "tomi@gmail.com" que no es premium, una compra de "Fernet" con valor $5000 y hay stock disponible de la bebida "Fernet"
Cuando se selecciona la bebida "Fernet" con monto total $5000 y se presiona "Aceptar".
Entonces el sistema informa en pantalla el monto total y el monto total con 10% de descuento aplicado.

Escenario 4: Selección exitosa con descuento del 30%
Dado el usuario "facu@gmail.com" que es premium, una compra de "Whiskey" con valor $6000 y hay stock disponible de la bebida "Whiskey".
Cuando se selecciona la bebida "Whiskey" con monto total $6000 y se presiona "Aceptar".
Entonces el sistema informa en pantalla el monto total y el monto total con 30% de descuento aplicado.

Escenario 5: Selección fallida por falta de stock
Dado el usuario "fer@gmail.com" que es premium, una compra de "Vino" con valor $3000 y no hay stock disponible de la bebida "Vino".
Cuando se selecciona la bebida "Vino" con monto total $3000 y se presiona "Aceptar"
Entonces el sistema informa "Sin stock de la bebida seleccionada".