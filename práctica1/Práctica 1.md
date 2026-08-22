## **Obtención de los requerimientos.**
### **Parte I Definiciones**

#### **1) Definir brevemente que es un requerimiento**

Un Requerimiento (o requisito) es una característica del sistema o una descripción de algo que el sistema es capaz de hacer con el objeto de satisfacer el propósito del sistema.
#### 2) **Defina requerimientos funcionales y no funcionales**

| **Criterio**   | **Requerimientos Funcionales (RF)**                                                  | **Requerimientos No Funcionales (RNF)**                                                   |
| -------------- | ------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------- |
| **Definición** | Definen **qué** debe hacer el sistema (comportamiento, funciones y servicios).       | Definen **cómo** debe ser o comportarse el sistema (calidad, rendimiento, restricciones). |
| **Enfoque**    | Acciones directas, entradas y salidas de información, procesamiento de datos.        | Atributos de calidad, seguridad, usabilidad, arquitectura y restricciones técnicas.       |
| **Alcance**    | Específicos para funciones o módulos puntuales del sistema.                          | Suelen ser globales y afectar al sistema completo.                                        |
| **Ejemplo**    | "El sistema debe permitir al usuario registrarse utilizando su correo y contraseña." | "El tiempo de respuesta del inicio de sesión no debe superar los 2 segundos."             |
#### 3) **Defina que es un stakeholder.**

El término stakeholder se utiliza para referirse a cualquier persona o grupo que se verá afectado por el sistema, directa o indirectamente.
Entre los stakeholders se encuentran: Usuarios finales, ingenieros, gerentes y expertos del dominio.

#### 4) **Defina las fuentes más importantes para la obtención de información**

Documentación: Información previa en soporte físico o digital sobre el negocio o las reglas actuales.
Stakeholders.
Especificaciones de sistemas similares: Software actual (legacy) o soluciones del mercado/competencia.

![[Pasted image 20260822131544.png|391]]

#### 5) **Indique los puntos de vista (de manera genérica) que se pueden reconocer en un proyecto de software.**

- Punto de vista de los interactuadores: representan a las personas u otros sistemas que interactúan directamente con el sistema. Pueden influir en los requerimientos del sistema de algún modo.
- Punto de vista indirecto: representan a los stakeholders que no utilizan el sistema ellos mismos pero que influyen en los requerimientos de algún modo.
- Punto de vista del dominio: representan las características y restricciones del dominio que influyen en los requerimientos del sistema.
#### 6) **Enumere tres problemas de comunicación que pueden existir en la elicitación de requisitos.**

Limitaciones cognitivas (del desarrollador) -> No conocer el dominio del problema.
Conducta humana -> Conflictos y ambigüedades en los roles de los participantes.
Técnicos -> Complejidad del dominio del problema.

### **Parte II Problemas**

#### **a) Indicar para cada problema quienes podrían ser los Stakeholders, los puntos de vista y las fuentes de información.**

##### **1.**

Stakeholders.
Alumnos; Jefe de Trabajos Prácticos; Profesor a cargo de la materia; Oficina de alumnos, Responsables de privacidad/legales, Administradores de IT de la universidad.

Puntos de vista. 
- Interactuadores: Alumnos de la catedra Ing. De software 1; JTP (autoriza la sesión); profesor (consulta/emite los listados)
- Indirectos: Oficina de alumnos (provee los datos); Autoridades/Área Legal de la facu. 
- Dominio: Reglamentación de privacidad de datos de la facultad

Fuentes de información.
Los stakeholders mencionados: Entrevistas y encuestas a éstos.
Documentación: Reglamentaciones vigentes sobre privacidad de datos en la universidad.
Sistemas: Siu guarani (se extraen los datos).

##### **2.**

Stakeholders.
Pacientes; enfermeros; médicos; director de la clínica; empleados administrativos.

Puntos de vista.
- Interactuadores: Empleados, enfermeros, médicos, director de la clínica.
- Indirectos: Paciente (provee los datos); representantes legales de la clínica (dan información sobre las normativas); ministerio de salud.
- Dominio: Normativas impuestas por el ministerio de salud de PBA.

Fuentes de Información.
Stakeholders mencionados: entrevistas a ellos y cuestionarios.
Documentación: Normativas del ministerio.
Sistemas: Ficheros/historias clínicas físicas actuales de la clínica y software de gestión médica similar utilizado en el mercado.

#### **b) Habiendo resuelto los problemas presentados, ¿por qué considera que los requerimientos de los distintos stakeholders podrían entrar en conflicto?**

Suelen entrar en conflicto porque **cada actor tiene objetivos, prioridades, necesidades y responsabilidades diferentes** que muchas veces compiten entre sí por recursos, usabilidad, seguridad o costo.

En el **sistema biométrico**, los _alumnos_ buscan rapidez para marcar asistencia e irse a clase, mientras que el _JTP_ y el _Profesor_ priorizan el control estricto para evitar fraudes, exigiendo pasos de validación o autorizaciones previas que pueden demorar el proceso.
[^1]

[^1]: usabilidad vs seguridad/control

En la **clínica**, los _médicos y enfermeros_ quieren interfaces simples con pocos clics para no perder tiempo con el paciente; en cambio, el _Director_ y el _Ministerio de Salud_ exigen cargar una gran cantidad de datos obligatorios para cumplir con la legalidad de la historia clínica.[^2]

[^2]: facilidad de operacion vs rigurosidad normativa

## **Entrevistas**.

### **Parte I Definiciones.**

#### **1. Describa qué tipo de información puede obtenerse en una entrevista.**

Opiniones -> Expresiones sobre lo que las personas prefieren.
Objetivos -> Propósitos, metas y necesidades a resolver.
Procedimientos informales -> Acciones prácticas que no aparecen en los manuales.
Sentimientos -> Estados de ánimo, frustraciones y niveles de satisfacción.
#### **2. Enumere y describa brevemente las etapas de la preparación de una entrevista.**

- 1. Leer los antecedentes: Poner atención en el lenguaje. Buscar un vocabulario en común. Imprescindible para poder entender al entrevistado.
- 2. Establecer los objetivos de la entrevista: Usando los antecedentes. Los directivos suelen proporcionar una visión general, mientras que los futuros usuarios una más detallada.
- 3. Seleccionar los entrevistados: Se debe minimizar el número de entrevistas. Los entrevistados deben conocer con antelación el objetivo de la entrevista y las preguntas que se le van a hacer.
- 4. Planificación de la entrevista y preparación del entrevistado: Establecer fecha, hora, lugar y duración de cada entrevista de acuerdo con el entrevistado.
- 5. Selección del tipo de preguntas a usar y su estructura.

#### 3. **Enumere y describa brevemente qué tipos de preguntas puede contener una entrevista. Detalle ventajas y desventajas de cada una.**

| **Tipo de Pregunta** | **Descripción y Ejemplo**                                                                                                                                                     | **Ventajas**                                                                                                                                                                                                       | **Desventajas**                                                                                                                                                                                             |
| -------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Abiertas**         | Permiten al entrevistado responder libremente sin restricciones de formato o longitud.<br><br>  <br>  <br><br>_Ejemplo:_ ¿Qué opinión tiene del sistema actual?               | • Revelan nuevas líneas de investigación no previstas.<br><br>  <br><br>• Mantiene el interés y permite la espontaneidad.<br><br>  <br><br>• Aportan contexto valioso sobre el problema.                           | • Pueden generar mucha información irrelevante.<br><br>  <br><br>• Es fácil perder el control de la entrevista y del tiempo.<br><br>  <br><br>• Da la impresión de falta de preparación u objetivos claros. |
| **Cerradas**         | Exigen respuestas concretas, directas, cortas o elegidas dentro de un conjunto limitado de opciones.<br><br>  <br>  <br><br>_Ejemplo:_ ¿Quién recibe este informe?            | • Ahorran tiempo significativamente.<br><br>  <br><br>• Facilita mantener el control de la reunión.<br><br>  <br><br>• Permite obtener datos precisos y estructurados.                                             | • Pueden aburrir o limitar al entrevistado.<br><br>  <br><br>• No aportan detalles, matices ni explicaciones de fondo.                                                                                      |
| **Sondeo**           | Se utilizan a continuación de una respuesta abierta o cerrada para profundizar en un aspecto específico.<br><br>  <br>  <br><br>_Ejemplo:_ ¿Podría dar más detalles sobre...? | • Permite aclarar respuestas ambiguas o incompletas.<br><br>  <br><br>• Demuestra interés activo en el discurso del entrevistado.<br><br>  <br><br>• Obtiene el nivel de detalle necesario para la especificación. | • Si se abusa, puede sentirse como un interrogatorio.<br><br>  <br><br>• Requiere mucha agilidad y preparación en tiempo real por parte del entrevistador.                                                  |

#### 4. **Enumere y describa brevemente qué tipo de estructuras y organización existen para el armado de una entrevista.**

Tipos de estructuras.
Estructuradas(Cerradas) -> El encuestador tiene un conjunto específico de preguntas para hacerle al entrevistado. Se dirige al usuario sobre un requerimiento puntual. No permite adquirir un amplio conocimiento del dominio.

No estructuradas(Abiertas) -> El encuestador lleva a un tema en general. Sin preparación de preguntas específicas. Iniciar con preguntas que no dependen del contexto, para conocer el problema, la gente involucrada, etc.

Tipos de organizaciones.

![[Pasted image 20260822155541.png|519]]

![[Pasted image 20260822161839.png|357]]

![[Pasted image 20260822161857.png|358]]

![[Pasted image 20260822161930.png|360]]


#### 5. **Analice un formato de la planilla adecuado al momento de armar una entrevista.**

Al momento de planificar y armar la entrevista (guión/planilla previa), la plantilla debe contemplar los siguientes apartados clave:

1. **Datos de cabecera e identificación del entrevistado:**
    - **Nombre y cargo / rol:** Para seleccionar al entrevistado según el requerimiento a analizar y armar las preguntas acorde a sus características, fortalezas y motivaciones.
    - **Fecha, hora, lugar y duración estimada:** Permite fijar un horario de trabajo respectivo y coordinar un espacio privado o sala de reuniones.
2. **Objetivo y alcance de la entrevista:**
    - **Definición clara del propósito:** Definir explícitamente qué requerimiento o problemática se busca abordar (por ejemplo, obtener una visión general con directivos o detallada con usuarios).
3. **Glosario / Vocabulario común:**
    - Espacio destinado a identificar los antecedentes y la jerga propia del dominio/negocio para facilitar la comprensión fluida durante la charla.
4. **Diseño de las preguntas (Guión de Entrevista):**
    - **Estructura lógica definida:** La plantilla debe especificar qué organización o formato de flujo de preguntas se utilizará:
        - _Piramidal (Inductiva):_ Inicia con preguntas cerradas y va abriendo hacia preguntas abiertas.
        - _Embudo (Deductiva):_ Inicia con preguntas abiertas y se va cerrando hacia detalles puntuales.
        - _Diamante:_ Inicia con preguntas cerradas, pasa a abiertas y concluye con cerradas.
    - **Tipos de preguntas redactadas:**
        - _Preguntas Abiertas:_ Para explorar sensaciones, opiniones o nuevas líneas de indagación.
        - _Preguntas Cerradas:_ Para recolectar datos puntuales y precisos.
        - _Preguntas de Sondeo:_ Espacios/pautas pensadas para pedir ejemplos o mayores detalles.
    - **Reglas de redacción en la plantilla:** Redactadas en lenguaje claro, conciso, evitando preguntas sesgadas, amenazantes, con juicio de opinión o demasiado largas y complejas.

#### 6. **Analice un formato de la planilla adecuado al momento de terminar una entrevista.**

Al momento de finalizar la sesión y realizar el cierre/seguimiento, la planilla de registro o acta de la entrevista debe incluir las siguientes secciones clave:

1. **Sección de Cierre In situ (Durante la entrevista):**
    - **Conclusión y resumen verbal expresado:** Un apartado con los puntos principales resumidos brevemente antes de finalizar para validar la comprensión, ganar la confianza del entrevistado y verificar que se cumplió con el tiempo pactado.
    - **Agradecimiento y registro formal:** Confirmar que se agradeció la atención y el tiempo brindado.
2. **Registro de Notas de Campo (Respuestas verbales y no verbales):**
    - **Respuestas obtenidas:** Registro claro de los hechos, procedimientos informales, opiniones y sentimientos expresados.
    - **Observaciones del lenguaje corporal:** Notas sobre expresiones faciales, postura y gestos del entrevistado percibidos durante la charla.
3. **Sección de Seguimiento (Post-entrevista):**
    - **Plan de elaboración de minuta / resumen formal:** Plantilla o espacio borrador para redactar un resumen completo de lo conversado.
    - **Mecanismo de validación:** Registro para el envío del resumen al entrevistado con el fin de permitirle aclarar, corregir o agregar cualquier punto que no se haya comprendido adecuadamente.

### **Parte II Situaciones**

##### **Situación 1**

a. Sus subordinados me dijeron que la empresa no anda bien. ¿Es cierto?

Provoca una actitud defensiva, ya que transmite un tono acusatorio; Uso ambiguo y poco profesional, "no anda bien" es informal; Se menciona lo que sus subordinados expresan, esto puede generar conflictos internos, además que la palabra "subordinado" es innecesaria, ya que no lo son.
<<Desde su perspectiva como gerente, ¿Cuáles considera que son los principales desafíos o áreas de mejora que enfrenta actualmente el área de ventas?>>

b. Soy nuevo en esto. ¿Qué he dejado afuera? 

Falta de preparación y profesionalismo, rompe la confianza.
<<Considerando los puntos que hemos abordado sobre el sector, ¿hay algún otro aspecto clave o proceso específico de ventas que considere importante sumar a este análisis?>>

c. ¿Estará usted de acuerdo con los demás gerentes de ventas, respecto a que computarizar las ventas mensuales y luego realizar un análisis de la tendencia tendría usted grandes mejoras? 

Pregunta sesgada. Presiona al entrevistado a estar de acuerdo con la opinión de sus pares o del entrevistador mismo, condicionando la respuesta. Además, es confusa y con una sintaxis poco clara.
«¿Qué impacto o beneficios esperaría obtener en la gestión del sector si se automatizara el registro de ventas mensuales y el análisis de tendencias?»

d. ¿No habrá una mejor manera de hacer proyecciones de sus ventas, que ese procedimiento anticuado que usted utiliza?

Juicio de valor y términos peyorativos.
«¿Cómo llevan a cabo actualmente el proceso de proyección de ventas y qué limitaciones o dificultades identifican en dicho método?»

### **Parte III Problemas**

#### **Problema 1.**

##### **PLANILLA DE PLANIFICACIÓN DE ENTREVISTA (ANTES Y DURANTE)**
##### **1. Datos de Cabecera e Identificación**

- **Proyecto:** Sistema de Vehículo Compartido (_Carpooling_).
- **Entrevistado:** Patrocinador del Proyecto / _Product Owner_ (o Usuario Representante / Chofer frecuente).
- **Entrevistador:** Analista de Sistemas.
- **Fecha y Hora:** [Fecha] a las [Hora].
- **Lugar / Medio:** Sala de Reuniones / Videoconferencia.
- **Duración estimada:** 45 - 60 minutos.
##### **2. Objetivo y Alcance**

- **Objetivo General:** Relevar y especificar los requerimientos funcionales y no funcionales para la plataforma de viajes compartidos, comprendiendo las dinámicas de publicación, postulación, selección de pasajeros y división de costos.
- **Alcance:** Proceso completo desde el registro de usuarios, publicación de viajes, postulación, aprobación/selección de pasajeros, comunicación en la app y cálculo/reparto de costos.
##### **3. Glosario y Vocabulario del Dominio**

- **Chofer / Conductor:** Usuario que publica una ruta disponible en su vehículo.
- **Pasajero / Acompañante:** Usuario que busca un viaje existente e intenta sumarse a él.
- **Postulación:** Solicitud enviada por un pasajero al chofer para sumarse a un viaje.
- **Asiento / Cupo:** Lugar disponible dentro del vehículo.
##### **4. Guión de Entrevista**

##### **A. Apertura e Introducción (5 min)**

- Presentación del analista y del objetivo de la reunión.
- Confirmación del tiempo disponible.
- Breve explicación de la dinámica de trabajo y solicitud de consentimiento para tomar notas.
##### **B. Cuerpo de la Entrevista (35 min)**

_(Estructura seleccionada: **Estructura en Diamante** — Comienza con preguntas cerradas de contexto, se abre a la indagación de procesos y visiones, y se cierra con especificaciones técnicas o de reglas de negocio)._
##### **Bloque 1: Perfiles y Gestión de Usuarios (Preguntas Cerradas y de Contexto)**

1. ¿Qué tipos de usuarios interactuarán con la plataforma? ¿Un usuario puede ser chofer y pasajero según la ocasión?
2. ¿Qué datos mínimos requerirá la plataforma para registrar y validar la identidad de un usuario?
3. Para los usuarios que actúen como choferes, ¿se les solicitará documentación adicional (licencia de conducir, seguro, cédula del vehículo)?
##### **Bloque 2: Publicación y Búsqueda de Viajes (Preguntas Abiertas)**

4. ¿Cómo se imagina el proceso completo mediante el cual un chofer publica un viaje? _(Pedir detalles de: origen, destino, fechas, horarios, puntos intermedios, cantidad de cupos)._
5. ¿De qué manera los pasajeros buscarán o filtrarán los viajes disponibles en la plataforma?
6. ¿Qué ocurre si un viaje publicado sufre modificaciones de horario o cancelaciones por parte del chofer?
##### **Bloque 3: Postulación, Selección y Comunicación (Preguntas de Sondeo / Detalle)**

7. ¿Cómo es el flujo desde que un pasajero encuentra un viaje hasta que queda confirmado en él?
8. ¿El chofer elegirá a los acompañantes manualmente o existirá alguna opción de aprobación automática?
9. ¿Qué criterios o información tendrá en cuenta el chofer para aceptar o rechazar a un postulante? _(Ej.: reputación/calificaciones, perfiles, comentarios)._
10. ¿Se dispondrá de algún canal de comunicación interna (como chat o mensajería) entre el chofer y los postulantes antes de confirmar el viaje?
##### **Bloque 4: Reparto de Costos y Aspectos del Dominio (Preguntas Abiertas y Cerradas)**

11. ¿Cómo se calculará y dividirá el costo del viaje entre los participantes para cumplir el objetivo de abaratar costos?
12. ¿El pago o compensación se gestionará dentro de la aplicación (pasarela de pagos) o se coordinará de manera externa/efectivo entre los usuarios?
13. ¿Existirá un sistema de calificación y reseñas una vez finalizado el trayecto? ¿Cómo funcionará?
##### **Bloque 5: Requerimientos No Funcionales y Restricciones (Preguntas Cerradas de Detalle)**

14. ¿En qué plataformas (Android, iOS, Web) debe funcionar prioritariamente la aplicación?
15. ¿Qué nivel de disponibilidad y tiempos de respuesta se esperan para la gestión de postulaciones en tiempo real?
##### **SECCIÓN DE CIERRE Y SEGUIMIENTO (POST-ENTREVISTA)**

##### **1. Cierre In situ (5 min)**

- **Resumen verbal:** Recapitulación de los puntos más relevantes conversados (mecanismos de publicación, aprobación manual por parte del chofer, cálculo de costos y soporte de calificaciones).
- **Validación preliminar:** Confirmación con el entrevistado de que la visión comprendida es la correcta.
- **Agradecimiento:** Cierre formal agradeciendo el tiempo aportado.
##### **2. Plan de Registro de Notas y Observaciones de Campo**

- **Registro de hechos y opiniones:** Documentación detallada de las respuestas verbales relativas a reglas de negocio (ej. límites de cupos, formas de cobro).
- **Notas de lenguaje corporal y actitud:** Registro de dudas, entusiasmo o reticencias manifestadas durante la entrevista frente a ciertas funcionalidades (ej. preocupación por la seguridad de los usuarios o cobros por la app).
##### **3. Plan de Seguimiento y Validación**

- **Redacción de Minuta:** Elaboración de la minuta formal de requerimientos obtenidos dentro de las 24 horas posteriores a la entrevista.
- **Mecanismo de Confirmación:** Envío de la minuta vía correo electrónico al entrevistado para su revisión, solicitando correcciones, adiciones o la aprobación definitiva de los requerimientos explicitados.

## **Cuestionarios**

### **PARTE I: DEFINICIONES**

**1) Información que se busca mediante cuestionarios**.A través de los cuestionarios se busca recolectar información masiva, estandarizada y cuantitativa/cualitativa sobre:

- **Posturas, opiniones y sentimientos** de los usuarios respecto a los sistemas actuales o propuestos.
- **Objetivos e intenciones** de la organización y sus empleados.
- **Comportamientos y patrones de uso** (frecuencia de uso de un módulo, tipo de datos manipulados).
- **Características de los usuarios** y del entorno de trabajo.

**2) Circunstancias apropiadas para su uso**. Su aplicación es ideal cuando:

- Las personas a entrevistar están **geográficamente dispersas** (como en una red de sucursales).
- Se necesita evaluar a un **número elevado de personas** (gran volumen de usuarios).
- Se realizan estudios exploratorios para medir el interés antes de formular un proyecto.
- Se busca **anonimato** para obtener respuestas honestas sobre problemas sensibles.
- Se requiere recopilar datos cuantitativos rápidos para complementar las entrevistas personales.

**3) Tipos de cuestionarios**

- **Cuestionarios Abiertos:** Utilizan preguntas de respuesta libre. Permiten al encuestado expresarse con sus propias palabras, lo que brinda flexibilidad y riqueza cualitativa, aunque dificulta la cuantificación y el análisis estadístico.
- **Cuestionarios Cerrados:** Utilizan preguntas con opciones de respuesta predeterminadas (opción múltiple, escalas de Likert, dicotómicas Sí/No). Facilitan el llenado rápido y el análisis estadístico masivo, aunque limitan la profundidad de la información.

### **PARTE II: SITUACIONES (SITUACIÓN 1)**

#### **Análisis de la Encabezado y Advertencia Inicial**

- **Inadecuada:** La amenaza («su cheque de pago será retenido») es altamente destructiva. Destruye el _rapport_, genera hostilidad, condiciona la honestidad de las respuestas y atenta contra la ética laboral.
- **Redacción apropiada:** _«Estimado colaborador: Con el fin de mejorar el servicio informático en las sucursales, solicitamos su valiosa colaboración respondiendo esta breve encuesta. Sus respuestas nos ayudarán a optimizar el nuevo sistema en red. Por favor, enviar antes del [Fecha].»_
#### **Análisis y Reescritura de las Preguntas**

##### **1. «En pocas palabras indique qué problemas ha tenido el actual centro de cómputo.»**

- **Inadecuada:** Es contradictoria. Pide sintetizar («en pocas palabras») una respuesta a una pregunta muy amplia y abierta. Además, está enfocada de manera negativa.
- **Redacción apropiada:** _«¿Cuáles son las tres principales dificultades que experimenta actualmente al utilizar el sistema de cómputo?»_ (o bien presentar una lista en escala Likert con problemas comunes para marcar).
##### **2. «¿Habrá alguien que piense de la misma manera que usted? Enumere sus nombres.»**

- **Inadecuada:** Es intimidante, persecutoria y fomenta el conflicto interno. Ningún usuario querrá Delatar a sus compañeros, vulnerando la confidencialidad.
- **Redacción apropiada:** _«¿Considera que los problemas mencionados afectan individualmente su trabajo o a la dinámica de todo su equipo de trabajo?»_ (Con opciones: Individual / A su equipo / A toda la sucursal).
##### **3. «¿Cuántas PC fallaron en estos últimos 6 meses?»**

- **Inadecuada:** Exige al usuario recordar un dato estadístico/técnico exacto que raramente contabiliza. Esto produce datos poco precisos o ficticios por estimación.
- **Redacción apropiada:** _«En los últimos 6 meses, ¿con qué frecuencia ha experimentado fallas en su equipo de cómputo?»_ (Opciones: Diariamente / Semanalmente / Mensualmente / Rara vez / Nunca).
##### **4. «¿Cuál es el problema más grande que enfrenta al comunicar sus problemas al centro de cómputo?»**

- **Inadecuada:** Asume como premisa que **siempre** existen problemas de comunicación con la sede (pregunta sesgada/inducida).
- **Redacción apropiada:** _«¿Cómo calificaría la comunicación y la velocidad de respuesta del centro de cómputo ante un incidente técnico?»_ (Escala de 1 a 5, con un espacio adicional para sugerencias breves).