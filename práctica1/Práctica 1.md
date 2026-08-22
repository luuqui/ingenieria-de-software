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

## **Entrevistas**

