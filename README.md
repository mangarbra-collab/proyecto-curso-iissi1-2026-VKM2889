# MeETSII

## Miembros del grupo L2-ABS-9

1. García Díaz, Álvaro
1. García De Castro Bracho, Manuel
1. Sánchez Bracho, Juan de Dios
1. Piñero Franco, Ángel

## 1. Introducción al problema

En el entorno universitario actual, los estudiantes deben lidiar con varias aplicaciones simultáneamente para coordinar sesiones de estudio, organizar material propio y de otros, y resolver dudas colaborativas fuera de clase, entre otros inconvenientes.
Esta situación genera problemas como:

•	Desorganización del material: las dudas importantes y sus respuestas (si es que alguien se para a leerlas) quedan sepultadas bajo mensajes irrelevantes en los grupos de estudio.

•	Falta de centralización de herramientas: los estudiantes deben saltar de aplicación en aplicación para facilitar sus estudios (Google Meet, Wuolah…), consiguiendo el efecto contrario: desconcentrarse durante largas sesiones.

•	Dificultad para encontrar compañeros: un estudiante que necesita apoyo en materias que se le complican, carece de medios para encontrar grupos universitarios enfocados estrictamente en el estudio, sin caer en la tentación y las distracciones de las redes sociales (WhatsApp, Instagram…).

<img width="886" height="382" alt="image" src="https://github.com/user-attachments/assets/0f88ecc1-358a-4883-ae00-8d736e8fde5d" />

Las expectativas de los usuarios (mayormente universitarios) hacia esta plataforma se concentran en disponer de un entorno centralizado que reúna los recursos necesarios para descubrir grupos de estudio, organizar quedadas con ellos y ordenar el material de cada asignatura; todo ello sin salir del entorno y evitando cualquier distracción.

El objetivo de nuestro proyecto es sencillo: crear una aplicación web que centralice el material necesario para el estudiantado, proporcionando una herramienta rápida, eficiente, social y orientada al aprendizaje común.

## 2. Glosario de términos

•	Biografía: Breve descripción ubicada en el perfil del estudiante, donde detalla qué estudia y las asignaturas que lleva en ese instante, su disponibilidad de quedadas en general, su contacto (redes sociales o teléfono) y sus objetivos.

•	Grupo de Estudio: Conjunto de estudiantes virtual cerrado, dentro de la propia web, y centrado en una materia específica; donde los miembros colaboran y comparten su material.

•	Privacidad del Grupo: Configuración que define qué tipo de acceso al grupo de estudio se desea: si el acceso a un grupo es libre (Público), donde cualquiera puede unirse libremente; o si se requiere la aprobación manual de una solicitud (Privado).

•	Quedada: Encuentro programado con fecha, hora, lugar y duración estimada (ej. Reservar una sala de estudio en el CRAI, X día a X hora); diseñado para el estudio colectivo, que puede tener una ubicación física o virtual en función de cómo se indique.

•	Sala Virtual: Entorno de videoconferencia integrado, con máximo número de participantes definido, donde los miembros de un grupo pueden conectarse en tiempo real vía chat, voz o audio.

•	Tablón de Preguntas: Pequeño foro interno de un grupo de estudio estructurado mediante hilos de conversación, donde los estudiantes publican sus dudas concretas que pueden ser marcadas como resueltas por quien pertenezca al mismo.
  

## 3. Visión general del sistema

### 3.1. Requisitos generales

- Gestión de usuarios y perfiles:
  1. Como administrador quiero poseer control de todos los usuarios existentes en la aplicación para asegurar el correcto uso de la aplicación por parte de los usuarios.
  2. Como estudiante quiero gestionar mi propio perfil para identificarme en la aplicación.
- Gestión de grupos:
  - Como administrador quiero consultar y modificar todos los grupos existentes en la aplicación para asegurar el correcto funcionamiento de éstos.
  2. Como estudiante quiero acceder a grupos para usar los servicios que proporciona(tablón de preguntas, salas y quedadas).
- Tablón de preguntas:
  1. Como estudiante quiero participar en el tablón para resolver mis dudas o las de otros estudiantes.
- Salas y quedadas:
  1. Como estudiante quiero organizar salas y quedadas para poner en común ideas con otros estudiantes.

### 3.2. Usuarios del sistema

El sistema por tanto tendrá sólo dos tipos de usuarios, con sus permisos:
1. Estudiante:
- Creación de grupos de estudio privados y públicos
- Acceso a grupos privados si el usuario tiene el código de unión
- Publicación de material y preguntas en el tablón
- Creación de quedadas para estudiar dentro de un grupo
- Permiso de unión de quedadas si se está dentro de un grupo
 
2. Administrador:
- Implementa todas las funcionalidades contenidas en el tipo de usuario "Estudiante"
- Acceso a todos los grupos (incluyendo los privados) por fines de moderación
- Permisos para eliminar publicaciones/preguntas en tablones si no son apropiados
- Permisos para eliminar quedadas de un grupo si no son apropiadas



     

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Registro de datos

Como estudiante, quiero crear una cuenta para acceder a los servicios de la aplicación

**Prueba de aceptación**
- Crear una cuenta de estudiante siendo estudiante
- Crear una cuenta de administrador siendo estudiante (debe fallar)

 
#### R.F.02. Gestión de Perfil

Como estudiante, quiero editar mis datos por si son erróneos o han cambiado

**Prueba de aceptación**
- Editar la carrera al cambiar de carrera
- Confirmar la edición de la biografía al editarla desde un perfil de estudiante/administrador


#### R.F.03. Administración de Usuarios

Como Administrador, quiero editar datos de otras cuentas de estudiantes o incluso vetar para moderar de manera más sencilla

**Prueba de aceptación**
- Vetar un estudiante y ver si se veta
- Editar datos (carrera, bio, grupos, etc.) de un estudiante y ver si se editan
- Vetar un grupo y ver si se veta


#### R.F.04. Creación de grupos

Como estudiante, quiero crear grupos de estudio indicando si son públicos o privados para organizar espacios de estudio a medida.

**Prueba de aceptación**
- Crear un grupo público y verificar que aparece en las búsquedas
- Crear un grupo privado y verificar que se genera un código de unión y no aparece accesible públicamente
- Debe cumplir la RN01
- Debe cumplir la RN05


#### R.F.05 Búsqueda de grupos

Como estudiante, quiero buscar grupos por materia o nombre y solicitar mi ingreso para encontrar compañeros con mis mismos intereses.

**Prueba de aceptación**
- Buscar un grupo por una materia o nombre existente y verificar que aparece en los resultados
- Al unirse, debe de cumplir la RN01


#### R.F.06. Acceso a grupos privados

Como estudiante, quiero acceder a grupos de estudio privados introduciendo un código de unión para unirme a grupos exclusivos de mis compañeros.

**Prueba de aceptación**
- Introducir un código de unión válido y verificar el ingreso al grupo privado
- Intentar acceder con un código erróneo o inventado (debe fallar)


#### R.F.07. Gestión de miembros

Como creador del grupo o Administrador, quiero expulsar miembros de un grupo para mantener un entorno de estudio adecuado y moderado.

**Prueba de aceptación**
- Expulsar a un miembro siendo el creador del grupo y verificar que pierde el acceso
- Expulsar a un miembro siendo Administrador y verificar que pierde el acceso
- Intentar expulsar a un miembro siendo un estudiante normal del grupo (debe fallar)


#### R.F.08. Publicar material de estudio

Como miembro de un grupo, quiero publicar material en el tablón para compartir apuntes y recursos con mis compañeros.

**Prueba de aceptación**
- Subir un archivo o enlace válido y verificar que aparece publicado en el tablón del grupo
- Intentar publicar material en el tablón de un grupo al que no se pertenece (debe fallar)


#### R.F.09. Publicar pregunta

Como miembro de un grupo, quiero publicar una duda en el tablón de preguntas para que otros compañeros puedan ayudarme a resolverla.

**Prueba de aceptación**
- Publicar una pregunta con texto válido y verificar que aparece listada en el tablón del grupo
- Intentar publicar una pregunta sin texto (debe fallar)
- Cumplir la RN03 al eliminar una pregunta siendo administrador


#### R.F.10. Marcar pregunta resuelta

Como autor de la pregunta, quiero cambiar el estado de mi duda a "resuelta" para que los demás sepan que ya no necesito ayuda.

**Prueba de aceptación**
- Marcar una pregunta propia como resuelta y verificar que el estado cambia a `true`
- Intentar marcar como resuelta la pregunta de otro estudiante sin ser Administrador (debe fallar)


#### R.F.11. Crear y unirse a sala virtual

Como miembro de un grupo, quiero abrir o unirme a una sala de videoconferencia asociada al grupo para estudiar en directo con mis compañeros.

**Prueba de aceptación**
- Abrir una nueva sala virtual dentro del grupo y verificar que el resto de miembros puede verla
- Unirse a una sala virtual activa siendo miembro del grupo
- Intentar unirse a la sala virtual de un grupo ajeno (debe fallar)
- Debe cumplir la RN04


#### R.F.12. Organizar quedada

Como miembro de un grupo, quiero programar una quedada especificando fecha, hora y ubicación (física o virtual) para coordinar sesiones de estudio conjuntas.

**Prueba de aceptación**
- Crear una quedada con fecha, hora y ubicación física válidas y verificar que se publica
- Crear una quedada introduciendo un enlace virtual en lugar de ubicación física y verificar su creación
- Intentar crear una quedada con una fecha u hora en el pasado (debe fallar)


#### R.F.13. Confirmación de asistencia

Como miembro de un grupo, quiero marcar mi asistencia a una quedada programada para que los organizadores sepan cuánta gente acudirá.

**Prueba de aceptación**
- Marcar asistencia a una quedada activa y verificar que el usuario aparece en la lista de asistentes
- Desmarcar la asistencia a una quedada previamente confirmada y verificar que se elimina de la lista
- Debe cumplir la RN02


#### R.F.14. Moderación de tablones (Administrador)

Como Administrador, quiero poder eliminar publicaciones o preguntas de cualquier tablón para mantener la plataforma libre de contenido inapropiado.

**Prueba de aceptación**
- Eliminar una publicación de material inapropiado siendo Administrador y verificar su borrado
- Eliminar una pregunta inapropiada siendo Administrador y verificar su borrado
- Intentar eliminar una publicación ajena siendo un estudiante normal (debe fallar)


#### R.F.15. Moderación de quedadas (Administrador)

Como Administrador, quiero poder consultar los datos de las quedadas y eliminar quedadas programadas en cualquier grupo para evitar actividades que incumplan las normas.

**Prueba de aceptación**
- Eliminar una quedada activa de un grupo ajeno siendo Administrador y verificar su borrado
- Acceder a un grupo privado sin ser miembro (usando privilegios de Admin) y eliminar una quedada

#### R.F.16. Unión a grupos

Como estudiante, quiero solicitar mi ingreso para encontrar compañeros con mis mismos intereses.
- Solicitar el ingreso a un grupo público desde los resultados y verificar que se añade al usuario
- Al unirse, debe de cumplir la RN01

TODO los 10 requisitos funcionales de consulta
  
#### 4.1.1. Requisitos de información
#### R.I.01. Información del perfil de Estudiante

Como Estudiante quiero ver la información personal y académica de mi perfil para que otros compañeros puedan ver mis datos a la hora de formar grupos de estudios.

Prueba de aceptación
- Comprobar que al acceder a la información personal del estudiante en la aplicación no hay ningún error en los datos.

#### R.I.02. Información de los Grupos de estudio

Como Estudiante quiero ver los datos completos de un Grupo de estudio para evaluar si encaja con mis necesidades antes de unirme.

Prueba de aceptación
- Al entrar a un grupo en la aplicación se comprobará que está toda la información. 

#### R.I.03. Información del Tablón de Preguntas

Como Estudiante quiero poder visualizar todas las preguntas en dicho tablón para comprobar si mi duda se ha resuelto o si las dudas de los demás también me sirven a mi.

Prueba de aceptación
- Al acceder al tablón se comprobará si las preguntas están en orden cronológico.
- Se comprobará si al subir una pregunta al tablón, es vista por los demás estudiantes.

#### R.I.04. Información de las Quedadas

Como Estudiante quiero consultar la información de una Quedada para poder organizarme.

Prueba de aceptación
- Veremos si la fecha y la hora se muestran en el formato correcto.
- Comprobar que el enlace o ubicación es visible solo para los estudiantes que tienen permiso para asistir a la quedada y además si el enlace es funcional y lleva adecuadamente al lugar que debe.

#### R.I.05. Información de la Sala 

Como Estudiante quiero poder unirme y participar en distintas salas y poder ver lo que pasa en ellas en tiempo real.

Prueba de aceptación
- Entramos en una sala como estudiante y se probará el funcionamiento correcto del sonido de la sala.
- Se probará si al entrar varias personas en la sala el funcionamiento de esta es correcto.

#### R.I.06. Listado e información de Usuarios

Como Administrador quiero regular el registro completo de Usuarios del sistema para así poder moderar la plataforma y gestionar posibles incidencias.

Prueba de aceptación
- Comprobaremos que se puede acceder desde los permisos de administrador a la lista de todos los usuarios de la aplicación.
- Nos fijaremos si dicha tabla solo puede ser accedida con permisos de administrador para proteger la privacidad de cada Estudiante.

#### R.I.07. Información de Administrador

Como Administrador quiero consultar la información de las estadísticas de la plataforma para evaluar el uso y el éxito de la aplicación.

Prueba de aceptación
- Se comprobará que al entrar con los permisos de un Administrador se puede gestionar todo en la aplicación como la creación y destrucción de grupos.
  
#### R.I.08. Información de Publicación

Como Estudiante quiero poder tener acceso a las publicaciones creadas y a la fecha de creación de las mismas para poder orientarme a la hora de buscar en el tablón de preguntas.

Prueba de aceptación
- Se comprobará la creación y eliminación de una publicación en el tablón de preguntas.
- Se comprobará que la información de la publicación es correcta.

#### R.I.09. Información de Pregunta

Como Estudiante quiero dentro de las Publicaciones poder poner un título a mi pregunta y saber si está resuelta por otro estudiante dentro del grupo.

Prueba de aceptación
- Se comprobará la publicación de una pregunta de un estudiante en la que el título se vea de forma correcta.
- Se hará una prueba en la que se responda una pregunta y aparezca como respondida.
  
#### R.I.10. Información de Respuesta

Como Estudiante quiero dentro de las Publicaciones poder responder a las Preguntas de los demás estudiantes en el Tablón de Preguntas

Prueba de aceptación
- Se realizará una prueba en la que un estudiante responda a una pregunta y esta sea visualizada de forma correcta por todos los estudiantes que forman el grupo.

  PONER ATRIBUTOS DE LOS REQUISITOS DE INFORMACIÓN
#### 4.1.2. Reglas de negocio

##### R.N.01. Límites de tamaño en grupos

El número de estudiantes unidos a un Grupo no puede superar su valor maxMiembros ni ser inferior a minMiembros (mínimo 2, máximo 20).

##### R.N.02. Gestión de Quedadas

Solo los estudiantes pertenecientes a un Grupo pueden crear o unirse a una Quedada vinculada a dicho grupo.

##### R.N.03. Eliminación de Preguntas en Tablón

Solo el Estudiante que ha hecho una pregunta o un Admin pueden eliminar un post del TablónPreguntas.

##### R.N.04. Coexistencia de Salas

Un Grupo solo puede tener activa una Sala de estudio virtual al mismo tiempo.

##### R.N.05. Aprobación en Grupos Privados

Si un Grupo es marcado como esPrivado = true, la solicitud de ingreso de un nuevo Estudiante debe ser aprobada explícitamente por el creador del grupo o un Admin.


### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML

- con restricciones.

### 5.2. Escenarios de prueba

- con descripción textual y diagrama de objetos UML.

## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:------|:-----------|:-----------|:-----------|:-----------|
| RI-1  | X          | X          | X          | X          |
| RI-2  |            | X          |            | X          |
| RF-1  |            | X          |            | X          |
| RF-2  | X          |            | X          | X          |
| RN-1  |            | X          |            |            |
| RN-2  | X          | X          | X          |            |
| ...   |            |            |            |            |

-- fin entregable 2 --

## 7. Modelo relacional en 3FN

- Relaciones obtenidas al aplicar la transformación del modelo conceptual.

### 7.1.  Justificación de la estrategia de transformación de jerarquías

- si se identificaron jerarquías en el MC.


### 8. Matriz de trazabilidad MC/SQL (opcional):

- Restricciones sobre el MC / Elementos del modelo tecnológico (SQL) (Triggers, checks, etc.)
- Incluir Reglas de negocio — Constraints/Triggers en las matrices de trazabilidad para el entregable 3

|       | EntidadX   | AsociaciónX  | RestricciónX  | Entidad2 ...   | 
|:-------|:-------|:-------|:-------|:-------|
| TABLA-1 |        |        |        |        |
| TABLA-2 |        |        |        |        |
| TABLA-3 |        |        |        |        |
| TABLA-4 |        |        |        |        |
| TRIG-1 |        |        |        |        |
| TRIG-2 | X      | X      |        | X      |
| TRIG-3 |        | X      |        | X      |
| TRIG-4 |        |        | X      |        |
| CONST-1 |        |        |        |        |
| CONST-2 | X      | X      |        | X      |
| CONST-3 |        | X      |        | X      |
| CONST-4 |        |        | X      |        |

Se consideran todo tipo de constraints declarativas (aquellas definidas durante el CREATE TABLE).
-- fin entregable 3 --

## Referencias


