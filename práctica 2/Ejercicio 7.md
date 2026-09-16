==ID: Realizar transferencia.==
Título: Como usuario quiero realizar una transferencia para concretar una venta.
Reglas de negocio:
- La patente ingresada no debe tener deudas.
- Vendedor y comprador deben ser mayores de 18 años.
Criterios de aceptación (realizar transferencia).

Escenario 1: Transferencia exitosa.
Dada una patente "aaa111" sin deudas registradas y transferencia no registrada en el sistema , un dni 11.278.000 coincidente al comprador de 25 años y un dni 11.234.567 coincidente al vendedor de 30 años.
Cuando se ingresa la patente "aaa111", dni del vendedor 11.234.567 y dni del comprador 11.278.000 y, se presiona "Aceptar".
Entonces el sistema registra la transferencia como iniciada y envía al mail del comprador un código para que realice el pago.

Escenario 2: Transferencia fallida por patente con deudas.
Dada una patente "bbb111" con deudas registradas.
Cuando se ingresa la patente "bbb111", dni del vendedor 11.234.567 y dni del comprador 11.278.000 y, se presiona "Aceptar".
Entonces el sistema informa "Patente con deudas registradas".

Escenario 3: Transferencia fallida por vendedor menor de 18 años.
Dada una patente "ccc111" sin deudas registradas y transferencia no registrada en el sistema, un dni 10.000.000 coincidente al comprador de 20 años y un dni 9.000.000 coincidente al vendedor de 17 años.
Cuando se ingresa la patente "ccc111", dni del vendedor 9.000.000 y dni del comprador 10.000.000 y, se presiona "Aceptar".
Entonces el sistema informa "Vendedor menor de 18 años".

Escenario 4: Transferencia fallida por comprador menor de 18 años.
Dada una patente "zzz111" sin deudas registradas y transferencia no registrada en el sistema, un dni 8.000.000 coincidente al comprador de 16 años y un dni 12.000.000 coincidente al vendedor de 20 años.
Cuando se ingresa la patente "zzz111", dni del vendedor 12.000.000 y dni del comprador 8.000.000 y, se presiona "Aceptar".
Entonces el sistema informa "Comprador menor de 18 años".

Escenario 5: Transferencia fallida por patente con transferencia ya iniciada.
Dada una patente "aaa111" sin deudas registradas y con una transferencia registrada en el sistema.
Cuando se ingresa la patente "aaa111", dni del vendedor 13.000.000 y dni del comprador 14.000.000 y, se presiona "Aceptar".
Entonces el sistema informa "Patente con transferencia ya iniciada".

==ID: Consultar transferencia.==
Título: Como usuario quiero consultar una transferencia para saber si se realizó con éxito.
Reglas de negocio:
- Se permiten solo hasta 3 consultas por mes.
Criterios de aceptación (consultar transferencia).

Escenario 1: Consulta exitosa.
Dado un usuario con mail "luca@gmail.com" con 2 consultas registradas en el sistema en el mes y una patente "aaa111" registrada en el sistema.
Cuando se ingresa la patente "aaa111" y se presiona "Consultar".
Entonces el sistema informa el estado de la transferencia.

Escenario 2: Consulta fallida por limite de consultas superado.
Dado un usuario con mail "juan@gmail.com" con 3 consultas registradas en el sistema en el mes.
Cuando se ingresa la patente "zzz111" y se presiona "Consultar".
Entonces el sistema informa "Limite de consultas alcanzado".

Escenario 3: Consulta fallida por patente no registrada en el sistema.
Dado un usuario con mail "facundo@gmail.com" con 1 consulta registrada en el sistema en el mes y una patente "bbb111" no registrada en el sistema.
Cuando se ingresa la patente "bbb111" y se presiona "Consultar".
Entonces el sistema informa "Patente no registrada en el sistema".
