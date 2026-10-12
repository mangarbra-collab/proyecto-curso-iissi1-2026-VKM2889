# Título Proyecto

## Miembros del grupo L2-ABS-9 (sustituir)

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

- Términos específicos del dominio del problema, ordenados alfabéticamente. Se valorará la presencia de información multimedia.

  

## 3. Visión general del sistema

### 3.1. Requisitos generales

### 3.2. Usuarios del sistema

El sistema por tanto tendrá sólo dos tipos de usuarios, con sus permisos:
1. Usuario:
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

#### R.F.01. Título requisito funcional

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- Se debe aplicar la regla de negocio R.N.XX.
- ...

#### 4.1.1. Requisitos de información

##### R.I.01. Título requisito de información

Como [tipo de usuario]
quiero [servicio]
para [razón]

**Prueba de aceptación**
- Descripción de la primera comprobación a realizar
- Descripción de la segunda comprobación a realizar
- ...

#### 4.1.2. Reglas de negocio

##### R.N.01. Título regla negocio

Descripción de la regla de negocio.

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


