Roles
- Usuario
- Administrador
Historias de usuario
- Solicitar kit
- Agregar elemento

Id: Solicitar kit.
Título: Como usuario solicitado quiero solicitar un kit para un trabajo académico.
Reglas de negocio:
- Duración máxima de un préstamo es 3 horas.
- Un usuario debe no tener prestamos activos para solicitar uno nuevo.

Criterios de aceptación (Solicitar kit):
Escenario 1: Solicitud exitosa.
Dado un usuario sin prestamos activos, la duración del préstamo es 2 horas siendo menor a 3 y hay stock disponible.
Cuando se ingresa tipo de kit "básico", día "martes", hora de retiro "14:30" y duración del préstamo "2" horas y, se presiona "Solicitar".
Entonces el sistema informa "Solicitud exitosa" y efectiviza el préstamo.

Escenario 2: Solicitud fallida por prestamos activos.
Dado un usuario con prestamos activos en el sistema.
Cuando se ingresa tipo de kit "básico", día "lunes", hora de retiro "14:30" y duración del préstamo "1" horas y, se presiona "Solicitar".
Entonces el sistema informa "Presenta préstamos activos en el sistema".

Escenario 3: Solicitud fallida por duración de préstamo mayor a 3 horas.
Dado un usuario sin préstamos activos en el sistema y la duración del préstamo es 4 horas siendo mayor a 3.
Cuando se ingresa tipo de kit "básico", día "jueves", hora de retiro "15:00" y duración del préstamo "4" horas y, se presiona "Solicitar".
Entonces el sistema informa "Duración máxima de préstamos es 3 horas".

Escenario 4: Solicitud fallida por falta de stock.
Dado un usuario sin préstamos activos en el sistema y la duración del préstamo es 2 horas siendo menor a 3 y no hay stock disponible del kit solicitado.
Cuando se ingresa tipo de kit "básico", día "viernes", hora de retiro "15:00" y duración del préstamo "2" horas y, se presiona "Solicitar".
Entonces el sistema informa "No hay stock disponible".

Id: Agregar elemento.
Título: Como encargado quiero agregar un nuevo elemento para formar otro kit.
Reglas de negocio:
- Número de serie de un elemento debe ser unívoco.
- Precio de compra debe ser máximo 1millon de pesos.
- Elementos no nacionales tienen impuestos adicionales del 10% sobre el precio de compra.

Criterios de aceptación (Agregar elemento nacional):
Escenario 1: Alta exitosa.
Dado un elemento que tiene número de serie "111" que no existe en el sistema, precio de compra "$100.000" siendo menor a $1.000.000 y origen de fabricación es "nacional".
Cuando se ingresa número de serie "111", tipo de elemento "cámara", precio de compra "$100.000", origen de fabricación "nacional" y fecha de alta "12/7/2026" y, se presiona "Aceptar".
Entonces el sistema informa "Elemento agregado con éxito" y efectiviza el alta en el sistema.

Criterios de aceptación (Agregar elemento internacional):
Escenario 2: Alta exitosa.
Dado un elemento que tiene número de serie "444" que no existe en el sistema, precio de compra "$400.000" siendo menor a $1.000.000 y origen de fabricación es "internacional".
Cuando se ingresa número de serie "444", tipo de elemento "cámara", precio de compra "$400.000", origen de fabricación "nacional" y fecha de alta "12/7/2026" y, se presiona "Aceptar".
Entonces el sistema agregará un impuesto del 10% calculado sobre el precio de compra, informa "Elemento agregado con éxito" y efectiviza el alta en el sistema

Escenario 3: Alta fallida por número de serie existente en el sistema.
Dado un elemento que tiene número de serie "2" que existe en el sistema.
Cuando se ingresa número de serie "2", tipo de elemento "cámara", precio de compra "$200.000", origen de fabricación "nacional" y fecha de alta "12/7/2026" y, se presiona "Aceptar".
Entonces el sistema informa "Número de serie existente en el sistema".

Escenario 4: Alta fallida por precio de compra mayor a 1millon de pesos.
Dado un elemento que tiene número de serie "3" que no existe en el sistema, precio de compra "2.000.000" siendo mayor a 1 millón y origen de fabricación "internacional".
Cuando se ingresa número de serie "3", tipo de elemento "micrófono", precio de compra "$2.000.000", origen de fabricación "nacional" y fecha de alta "12/7/2026" y, se presiona "Aceptar".
Entonces el sistema informa "Precio máximo de compra es 1 millón de pesos".