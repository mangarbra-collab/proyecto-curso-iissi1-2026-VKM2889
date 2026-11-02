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
- Creación y unión de grupos de estudio públicos y privados (mediante código o solicitud)
- Publicación y consulta de material, preguntas y respuestas en el tablón
- Creación, búsqueda y asistencia a quedadas para estudiar dentro de un grupo
- Gestión exclusiva de los datos de su propio perfil
 
2. Administrador:
- No participa en actividades de estudio, sino que vela por el cumplimiento de la normativa de la plataforma.
- Consulta del registro global de usuarios y capacidad de vetar/suspender cuentas infractorias.
- Acceso a todos los grupos (incluyendo los privados) por fines de moderación y capacidad para clausurarlos.
- Permisos de moderación para eliminar publicaciones, quedadas, preguntas y respuestas en tablones si no son apropiadas.
- Permisos de moderación para consultar el panel de métricas de la plataforma.



     

## 4. Catálogo de requisitos

### 4.1. Requisitos funcionales

#### R.F.01. Registro de datos

Como estudiante, quiero crear una cuenta para acceder a los servicios de la aplicación.

**Prueba de aceptación**
- Crear una cuenta de estudiante con datos válidos y verificar el alta en el sistema.
- Intentar crear una cuenta de administrador desde el formulario público (debe fallar).


#### R.F.02. Gestión de Perfil

Como estudiante, quiero editar mis datos personales y académicos por si son erróneos o han cambiado.

**Prueba de aceptación**
- Editar la titulación y la disponibilidad en el perfil y verificar que se guarden los datos.
- Intentar dejar el campo obligatorio de correo electrónico vacío (debe fallar).


#### R.F.03. Administración y veto de Usuarios (Administrador)

Como Administrador, quiero editar datos de otras cuentas de estudiantes o incluso vetar para mantener la plataforma moderada.

**Prueba de aceptación**
- Vetar un estudiante infractor (cambiar el estado) y verificar que no puede iniciar sesión.
- Vetar un grupo que incumpla la normativa y verificar que está bloqueado.


#### R.F.04. Creación de grupos

Como estudiante, quiero crear grupos de estudio indicando si son públicos o privados para organizar espacios de estudio a medida.

**Prueba de aceptación**
- Crear un grupo público y verificar que aparece en las búsquedas como abierto.
- Crear un grupo privado y verificar que se genera un código de unión y exige verificación.
- Verificar que el grupo se inicia respetando los límites de la RN01 y la configuración de la RN05.


#### R.F.05. Búsqueda de grupos y solicitud de unión

Como estudiante, quiero buscar grupos públicos por materia o nombre y solicitar mi ingreso para encontrar compañeros con mis mismos intereses.

**Prueba de aceptación**
- Buscar un grupo por una materia o nombre existente y verificar que aparece en los resultados.
- Unirse a un grupo de la lista verificando que cumple el límite de miembros de la RN01.


#### R.F.06. Acceso a grupos privados

Como estudiante, quiero acceder a grupos de estudio privados introduciendo un código de unión para unirme a grupos exclusivos.

**Prueba de aceptación**
- Introducir un código de unión válido y verificar que se guarda la solicitud de unión pendiente según la RN05.
- Intentar acceder con un código erróneo o inventado (debe fallar).


#### R.F.07. Búsqueda y gestión de miembros

Como creador del grupo o Administrador, quiero expulsar miembros de un grupo, buscándolos por su nombre de usuario, para mantener un entorno de estudio adecuado y moderado.

**Prueba de aceptación**
- Buscar a un miembro por su nombre de usuario y verificar que se muestra su perfil.
- Expulsar a un miembro siendo el creador del grupo o Administrador, y verificar que pierde el acceso.
- Intentar expulsar a un miembro siendo un estudiante sin permisos del creador del grupo ni de Administrador (debe fallar).


#### R.F.08. Publicar material de estudio

Como miembro de un grupo, quiero publicar material en el tablón de preguntas para compartir apuntes y recursos con mis compañeros.

**Prueba de aceptación**
- Subir un archivo o enlace válido y verificar que queda publicado en el tablón del grupo.
- Intentar publicar material en el tablón de un grupo al que no se pertenece (debe fallar).


#### R.F.09. Publicar pregunta

Como miembro de un grupo, quiero publicar una duda con título y descripción en el tablón de preguntas para que otros compañeros puedan ayudarme a resolverla.

**Prueba de aceptación**
- Publicar una pregunta con título y cuerpo válidos y verificar que aparece listada en el tablón del grupo.
- Intentar publicar una pregunta sin título ni cuerpo (debe fallar).


#### R.F.10. Responder pregunta y marcarla como resuelta

Como miembro de un grupo, quiero responder a las preguntas del tablón, y si soy el autor de la pregunta, quiero cambiar el estado de mi duda a "resuelta" cuando quede aclarada.

**Prueba de aceptación**
- Subir una respuesta en una pregunta abierta y verificar que se añade al hilo de la conversación correspondiente.
- Marcar una pregunta propia como resuelta y verificar que el estado cambia a `true`.
- Intentar marcar como resuelta la pregunta de otro estudiante sin ser Administrador (debe fallar).


#### R.F.11. Búsqueda, creación y unión de salas virtuales

Como miembro de un grupo, quiero consultar si hay una videollamada en curso, unirme (o abrir) una sala de videoconferencia nueva asociada al grupo para estudiar con mis compañeros en directo.

**Prueba de aceptación**
- Abrir una nueva sala virtual dentro del grupo si no hay una activa, y unirse a ella siendo miembro del grupo.
- Consultar la sección de salas virtuales del grupo y verificar si aparece listada una activa con sus miembros participantes.
- Intentar abrir una segunda sala virtual cuando ya hay una activa incumpliendo la RN04 (debe fallar).


#### R.F.12. Organizar quedada

Como miembro de un grupo, quiero programar una quedada especificando fecha, hora y ubicación (física o virtual) para coordinar sesiones de estudio conjuntas.

**Prueba de aceptación**
- Crear una quedada con fecha, hora y ubicación física válidas y verificar que se publica.
- Intentar crear una quedada con una fecha u hora en el pasado (debe fallar).


#### R.F.13. Búsqueda de quedada y confirmación de asistencia

Como miembro de un grupo, quiero buscar una quedada programada en ese mismo grupo y marcar mi asistencia para que los organizadores sepan cuánta gente acudirá.

**Prueba de aceptación**
- Filtrar la lista de quedadas programadas del grupo por fecha y verificar que se muestran los eventos filtrados.
- Confirmar o cancelar la asistencia a una quedada activa cumpliendo la pertenencia exigida en la RN02.


#### R.F.14. Moderación de tablones (Administrador)

Como Administrador, quiero poder eliminar publicaciones o preguntas de cualquier tablón para mantener la plataforma libre de contenido inapropiado.

**Prueba de aceptación**
- Eliminar una pregunta o una publicación de material inapropiado siendo Administrador cumpliendo la RN03 y verificar su borrado.
- Intentar eliminar una publicación ajena con cuenta de estudiante (debe fallar).


#### R.F.15. Moderación de quedadas (Administrador)

Como Administrador, quiero poder consultar la lista de las quedadas programadas de cualquier grupo y eliminar aquellas que incumplan las normas.

**Prueba de aceptación**
- Eliminar una quedada activa fraudulenta siendo Administrador y verificar su borrado del grupo.
- Consultar el listado de quedadas programadas de cualquier grupo, incluso siendo privado, con permisos de Administrador.


#### R.F.16. Búsqueda de datos de Perfil

Como estudiante, quiero ver los datos académicos y de disponibilidad de mi perfil y de otros estudiantes de mi grupo.

**Prueba de aceptación**
- Acceder al perfil de un estudiante y verificar que se muestran sus redes sociales, su carrera y sus horarios de estudio.
- Intentar visualizar datos privados de un usuario (debe fallar).


#### R.F.17. Consulta y filtrado de material de estudio

Como miembro de un grupo, quiero consultar y buscar el material publicado en el tablón por otros compañeros para descargar apuntes.

**Prueba de aceptación**
- Buscar un archivo o enlace válido en el tablón por su título y acceder al recurso correspondiente.
- Intentar consultar material en el tablón de un grupo al que no se pertenece (debe fallar).


#### R.F.18. Consultas de preguntas y respuestas del tablón

Como miembro de un grupo, quiero consultar las preguntas del tablón (filtrando por "resueltas" o "pendientes") y resolver mi duda sin repetir hilos.

**Prueba de aceptación**
- Filtrar las preguntas del tablón por "resueltas" y verificar que solo aparecen listadas aquellas con estado `true` y sus respuestas.
- Intentar consultar una pregunta eliminada o de un grupo ajeno privado (debe fallar).


#### R.F.19. Consulta global de usuarios registrados (Administrador)

Como Administrador, quiero buscar y consultar el listado completo de usuarios registrados en el sistema para inspeccionar cuentas y gestionar incidencias.

**Prueba de aceptación**
- Consultar la lista completa de Usuarios del sistema filtrando por "activo" o "vetado" desde una cuenta de Administrador.
- Intentar acceder al listado global de Usuarios desde una cuenta de estudiante (debe fallar).


#### R.F.20. Consulta global de estadísticas de la plataforma (Administrador)

Como Administrador, quiero consultar las métricas de la plataforma (total de usuarios, total de grupos activos, total de quedadas…) para estudiar el rendimiento de la plataforma.

**Prueba de aceptación**
- Acceder al panel de estadísticas como Administrador y verificar que se muestran los datos y contadores actualizados en tiempo real.
- Intentar acceder al panel de métricas desde una cuenta de estudiante (debe fallar).

  
### 4.1.1. Requisitos de información

#### R.I.01. Información del perfil de Estudiante (Hereda de Usuario)

Como Estudiante, quiero ver la información personal y académica de mi perfil para que otros compañeros puedan ver mis datos a la hora de formar grupos de estudio.

**Los atributos de este requisito son:**
- `carrera`: Grado o titulación universitaria que cursa.
- `biografia`: Breve descripción del estudiante.
- `disponibilidad`: Horarios o días disponibles para estudiar/quedadas.
- `objetivos`: Metas académicas actuales.
- `contacto`: Redes sociales o teléfono de contacto.

**Prueba de aceptación**
- Comprobar que al acceder a la información personal del estudiante en la aplicación se visualizan correctamente su carrera, biografía, disponibilidad, objetivos y contacto sin ningún error en los datos.


#### R.I.02. Información de los Grupos de estudio

Como Estudiante, quiero ver los datos completos de un Grupo de estudio para evaluar si encaja con mis necesidades antes de unirme.

**Los atributos de este requisito son:**
- `nombre`: Nombre descriptivo del grupo de estudio.
- `materia`: Asignatura o temática específica sobre la que trata.
- `descripcion`: Detalle del propósito u objetivos del grupo.
- `esPrivado`: Configuración de acceso (Booleano: Público / Privado).
- `codigoUnion`: Clave alfanumérica requerida para grupos privados.
- `minMiembros`: Número mínimo de integrantes permitidos (mínimo 2).
- `maxMiembros`: Número máximo de integrantes permitidos (máximo 20).
- `fechaCreacion`: Fecha y hora en la que se constituyó el grupo.

**Prueba de aceptación**
- Al entrar a la ficha de un grupo en la aplicación se comprobará que se muestra toda su información descriptiva, privacidad y límites de miembros.


#### R.I.03. Información del Tablón de Preguntas

Como Estudiante, quiero poder visualizar todas las preguntas en dicho tablón para comprobar si mi duda se ha resuelto o si las dudas de los demás también me sirven a mí.

**Los atributos de este requisito son:**
- `listaPublicaciones`: Colección ordenada cronológicamente de publicaciones e hilos.
- `totalPreguntas`: Contador de dudas publicadas.
- `totalResueltas`: Contador de dudas que ya tienen solución.

**Prueba de aceptación**
- Al acceder al tablón se comprobará si las preguntas están en orden cronológico y los contadores actualizados.
- Se comprobará si al subir una pregunta al tablón, es vista por los demás estudiantes del grupo.


#### R.I.04. Información de las Quedadas

Como Estudiante, quiero consultar la información de una Quedada para poder organizarme.

**Los atributos de este requisito son:**
- `titulo`: Nombre o motivo de la quedada.
- `fechaHora`: Fecha y hora programadas para el inicio.
- `duracionEstimada`: Tiempo previsto para la sesión de estudio.
- `esVirtual`: Modalidad (Booleano: Presencial / Online).
- `ubicacionOEnlace`: Lugar físico si es presencial (ej. Sala del CRAI) o enlace si es virtual.
- `listaAsistentes`: Nómina de estudiantes que han confirmado asistencia.

**Prueba de aceptación**
- Veremos si la fecha, la hora y la duración estimada se muestran en el formato correcto.
- Comprobar que el enlace o ubicación y la lista de asistentes son visibles solo para los estudiantes que pertenecen al grupo y que el enlace es funcional.


#### R.I.05. Información de la Sala

Como Estudiante, quiero consultar los datos de las salas virtuales activas en mi grupo y ver lo que pasa en ellas en tiempo real.

**Los atributos de este requisito son:**
- `nombre`: Nombre o título de la sesión en directo.
- `activa`: Estado de la transmisión (Booleano: En emisión / Inactiva).
- `participantesConectados`: Lista o número actual de usuarios conectados en tiempo real.

**Prueba de aceptación**
- Consultar una sala como estudiante del grupo y comprobar que muestra correctamente su nombre y su estado (`activa`).
- Se probará si al entrar varias personas en la sala el listado o contador de `participantesConectados` se actualiza en tiempo real.


#### R.I.06. Listado e información de Usuarios

Como Administrador, quiero consultar el registro completo de Usuarios del sistema para así poder moderar la plataforma y gestionar posibles incidencias.

**Los atributos de este requisito son:**
- `nombre`: Nombre completo.
- `email`: Dirección de correo electrónico.
- `esAdministrador`: Tipo de privilegios (Estudiante / Administrador).
- `fechaRegistro`: Fecha de alta en el sistema.
- `esVetado`: Estado de moderación del usuario (Activo / Vetado).
- `gruposPertenecientes`: Lista de identificadores de grupos donde está inscrito.

**Prueba de aceptación**
- Comprobaremos que se puede acceder desde los permisos de administrador a la lista con los atributos de todos los usuarios de la aplicación.
- Nos fijaremos en que dicha tabla solo pueda ser accedida con permisos de administrador para proteger la privacidad de cada Estudiante (debe fallar para estudiantes).


#### R.I.07. Información de Administrador (Hereda de Usuario)

Como Administrador, quiero consultar la información de las estadísticas de la plataforma para evaluar el uso y el éxito de la aplicación.

**Los atributos de este requisito son:**
- `totalUsuarios`: Número total de usuarios registrados en la plataforma.
- `totalGrupos`: Número global de grupos creados (públicos y privados).
- `totalQuedadas`: Total de quedadas programadas en la plataforma.
- `totalPublicaciones`: Número de materiales y preguntas subidos.
- `usuariosVetados`: Cantidad de cuentas restringidas/bloqueadas.
- `gruposVetados`: Cantidad de grupos moderados/bloqueados.

**Prueba de aceptación**
- Se comprobará que al entrar al panel con los permisos de un Administrador se visualizan sin errores todos los contadores estadísticos de usuarios, grupos, quedadas y publicaciones.


#### R.I.08. Información de Publicación

Como Estudiante, quiero poder tener acceso a los datos de las publicaciones creadas y a la fecha de creación de las mismas para poder orientarme a la hora de buscar en el tablón.

**Los atributos de este requisito son:**
- `autor`: Estudiante que ha creado la publicación.
- `contenido`: Texto descriptivo, archivo adjunto o cuerpo del mensaje.
- `fechaCreacion`: Marca de tiempo exacta (fecha y hora) de creación.

**Prueba de aceptación**
- Se comprobará que al consultar una publicación en el tablón se muestran su autor, contenido y fecha de creación de forma correcta.
- Se comprobará que la información deja de mostrarse tras la eliminación de la publicación.


#### R.I.09. Información de Pregunta (Hereda de Publicación)

Como Estudiante, quiero visualizar dentro de las Preguntas del tablón su título identificativo y saber si ya figura como resuelta por el autor.

**Los atributos de este requisito son:**
- `titulo`: Encabezado o enunciado breve de la duda (además de los heredados de Publicación).
- `estaResuelta`: Estado de la duda (Booleano: Resuelta / Pendiente).

**Prueba de aceptación**
- Se comprobará que al consultar una pregunta de un estudiante su título y atributos heredados se vean de forma correcta.
- Se hará una prueba en la que se marque como resuelta una pregunta y aparezca reflejado el estado `estaResuelta = true`.


#### R.I.10. Información de Respuesta (Hereda de Publicación)

Como Estudiante, quiero visualizar dentro de las Publicaciones las Respuestas asociadas a las Preguntas de los demás estudiantes en el Tablón de Preguntas.

**Los atributos de este requisito son:**
- *(Hereda `autor`, `contenido` y `fechaCreacion` de Publicación)*.

**Prueba de aceptación**
- Se realizará una prueba en la que un estudiante responda a una pregunta y se compruebe que el contenido y la fecha de la respuesta son visualizados de forma correcta por todos los estudiantes que forman el grupo.


### 4.1.2. Reglas de negocio

#### R.N.01. Límites de tamaño en grupos

El número de estudiantes unidos a un Grupo no puede superar su valor `maxMiembros` ni ser inferior a `minMiembros` (mínimo 2, máximo 20).

**Prueba de aceptación**
- El estudiante probará a meterse en un grupo con 20 estudiantes ya incluidos (debe fallar).
- El estudiante probará a meterse en un grupo con 15 estudiantes ya incluidos (debe funcionar).


#### R.N.02. Gestión de Quedadas

Solo los estudiantes pertenecientes a un Grupo pueden crear, visualizar o unirse a una Quedada vinculada a dicho grupo.

**Prueba de aceptación**
- Un estudiante miembro intentará crear o unirse a una Quedada vinculada a su grupo (debe funcionar).
- Un estudiante intentará visualizar una Quedada vinculada a un grupo al que no pertenece (debe fallar).


#### R.N.03. Eliminación de Preguntas en Tablón

Solo el Estudiante que ha hecho una pregunta o un Administrador pueden eliminar dicho post del Tablón de Preguntas.

**Prueba de aceptación**
- Un estudiante que no ha creado la pregunta intentará eliminarla (debe fallar).
- El estudiante que ha creado la pregunta o un Administrador intentará eliminarla (debe funcionar).


#### R.N.04. Coexistencia de Salas

Un Grupo solo puede tener activa una Sala de estudio virtual al mismo tiempo.

**Prueba de aceptación**
- Se intentará crear una nueva Sala cuando en el Grupo ya hay una activa existente (debe fallar).
- Se intentará crear una nueva Sala cuando en el Grupo no hay ninguna activa (debe funcionar).


#### R.N.05. Aprobación en Grupos Privados

Si un Grupo es marcado como `esPrivado = true`, hará falta introducir el `codigoUnion` para acceder al grupo de estudio y se comprobará si es correcto.

**Prueba de aceptación**
- Se comprobará que al ser `esPrivado = true`, el sistema exija al estudiante introducir un código de unión válido para incluirlo en el grupo (y falle si es incorrecto).
- Se comprobará que al ser `esPrivado = false`, el estudiante sea incluido directamente en el grupo sin pedir código.

#### R.N.06. Restricción a grupos de los estudiantes vetados

Si un Usuario es marcado como `esVetado = true` no podrá acceder a ningún grupo de estudio.

**Prueba de aceptación**
- Se comprobará que al ser `esVetado = true`, el sistema le restringirá al usuario acceder a cualquier grupo de estudio.
- Se comprobará que al ser `esVetado = false`, el sistema le permitirá al usuario acceder a los grupos de estudio a los que pertenece.

### 4.2. Mapa de historias de usuario (opcional)

### 4.3. Requisitos no funcionales (opcional)

**R.N.F. 01. Título requisito no funcional**
Como [tipo de usuario]
quiero [servicio]
para [razón]

-- fin entregable 1 --

## 5. Modelo conceptual

### 5.1. Diagramas de clases UML
<img width="1102" height="981" alt="image" src="https://github.com/user-attachments/assets/533d9d75-7059-465a-9a37-fb25edf0ef49" />




Restricciones:
- R1: Todos los Id tienen que ser únicos (IdUsuario, IdSala, IdGrupo, etc).
- R2: El email del estudiante debe terminar en "@alum.us.es".
- R3: La fecha de la creación del usuario debe ser menor o igual a la fecha actual { fechaRegistro <= currentTime() }
- R4: La fecha de la quedada debe ser posterior a la fecha de creación del grupo { quedada.fechaHora > grupo.fechaCreacion }
- R5: La duración estimada de la quedada debe ser positiva{ duracionEstimada > 0 }
- R6: La fecha de creación de la publicación debe ser mayor que la fecha de la creación del grupo { publicacion.fechaCreacion > grupo.fechaCreacion }


### 5.2. Escenarios de prueba

#### Escenario 1: Creación de un grupo público, quedada presencial y duda en el tablón

**Descripción textual:**
Álvaro y Ángel son dos estudiantes de Ingeniería del Software registrados en la plataforma, con su correo `@alum.us.es`. Álvaro crea un grupo de estudio público llamado "Repaso IISSI-1" para la asignatura de IISSI. 1, y Ángel se une al grupo (cumpliendo el mínimo de 2 miembros de la RN-01). 

Dentro del grupo se genera su tablón de preguntas. Ángel publica una pregunta en el tablón porque no entiende el tema de normalización, y Álvaro le escribe una respuesta explicándolo, por lo que la duda queda marcada como resuelta. Además, para estudiar juntos antes del examen, organizan una quedada presencial de 120 minutos en el CRAI de Reina Mercedes a la que asisten los dos.

<img width="771" height="1041" alt="escenario_1_isssi1" src="https://github.com/user-attachments/assets/9a060eb7-a3be-4a6c-9382-db86b7670401" />


#### Escenario 2: Grupo privado con sala virtual activa y supervisión del administrador

**Descripción textual:**
Juan y Manuel son dos estudiantes que quieren estudiar Redes sin que entre gente externa, así que Juan crea un grupo privado llamado "Prácticas de Redes" con el código de unión `"REDES26"`. Manuel introduce ese código para entrar al grupo (cumpliendo la RN-05). 

Como cada uno está en su casa, abren una única sala virtual llamada "Sala Packet Tracer" (cumpliendo la RN-04 de una sola sala activa por grupo) y ambos se conectan a la llamada. Mientras tanto, el administrador del sistema, Carlos, consulta las estadísticas generales de la plataforma y comprueba que hay un usuario vetado (`estVetado`) que tiene restringido el acceso a cualquier grupo (cumpliendo la RN-06).

<img width="1202" height="667" alt="escenario_2_isssi1" src="https://github.com/user-attachments/assets/ab8f3280-fd9b-43cf-95b0-743f5c78cb10" />


## 6. Matrices de trazabilidad

- Matriz de trazabilidad entre los elementos del modelo conceptual y los requisitos.

| Requisito | R1 | Usuario | R2 | R3 | R4 | Estudiante | Administrador | GrupoDeEstudio | TablonDePreguntas | SalaVirtual | Quedada | R5 | R6 | Publicación | R7 | Pregunta | Respuesta |
|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|
| RF-01 | | | X | X | X | X | | | | | | | | | | | |
| RF-02 | | | X | X | X | X | | | | | | | | | | | |
| RF-03 | | | X | X | X | | X | | | | | | | | | | |
| RF-04 | | | | | | X | | X | | | | | | | | | |
| RF-05 | | | | | | X | | X | | | | | | | | | |
| RF-06 | | | | | | X | | X | | | | | | | | | |
| RF-07 | | | | | | X | X | X | | | | | | | | | |
| RF-08 | | | | | | X | | X | | | | | | X | | | |
| RF-09 | | | | | | X | | | X | | | | | | | X | |
| RF-10 | | | | | | X | | | X | | | | | | | X | |
| RF-11 | | | | | | X | | X | | X | | | | | | | |
| RF-12 | | | | | | X | | X | | | X | | | | | | |
| RF-13 | | | | | | X | | X | | | X | | | | | | |
| RF-14 | | | | | | | X | X | X | | | | | X | | X | |
| RF-15 | | | | | | | X | X | | | X | | | | | | |
| RF-16 | | X | | | | X | | | | | | | | | | | |
| RF-17 | | | | | | X | | X | | | | | | X | | | |
| RF-18 | | | | | | X | | | X | | | | | | | X | |
| RF-19 | | | | | | X | | X | | | X | | | | | | |
| RF-20 | | | | | | X | | X | | | | | | | | | |
| RN-01 | X | X | | | | X | | | | | | | | | | | |
| RN-02 | | | | | | X | | X | | | X | | | | | | |
| RN-03 | | | | | | X | X | | X | | | | | | | X | X |
| RN-04 | | | | | | X | | X | | X | | | | | | | |
| RN-05 | | | | | | X | | X | | | | | | | | | |
| RI-01 | | X | | | | | | | | | | X | | | | | |
| RI-02 | | X | | | | | | | | | | | X | | | | |
| RI-03 | | | | | | X | | X | | | | | | | X | | |
| RI-04 | | | | | | X | | X | | | X | | | | | | |
| RI-05 | | | | | | X | | | X | | | | | | | | |
| RI-06 | | | | | | X | | X | | X | | | | | | | |
| RI-07 | | X | | | | | | | | | | | | | | X | |
| RI-08 | | | | | | | | | | | | | | X | | | |
| RI-09 | | | | | | X | | | | | | | | | | X | X |
| RI-10 | | X | | | | | | | | | | | | | | X | |

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


