## ** User stories queries **

1. Historia de usuario: HU_001

Como usuario

Dado que voy a ingresar al sistema de gestión de proyectos

Cuando necesite registrarme en el sistema

Entonces podré ingresar los datos de registro (Incluyendo elegir el rol al que aspiro)

- Query:

    mutation Register($input: RegisterInput!) {
      register(input: $input) {
        _id
      }
    }

- Body:

    {
      "input": {
        "email": "",
        "documentId": 0,
        "name": "",
        "lastName": "",
        "roleormato como **negrita** o *cursiva* de una manera muy sencilla.": "ADMIN",
        "password": ""
      }
    }


2. Historia de usuario: HU_002

Como usuario autorizado

Dado que voy a ingresar al sistema de gestión de proyectos

Cuando necesite autenticarme en el sistema

Entonces podré ingresar mi correo y contraseña para ser validados

- Query:

    query Query($email: String!, $password: String!) {
      login(email: $email, password: $password)
    }

- Body:

    {
      "email": "",
      "password": ""
    }

- Header:

Se obtiene un valor de login, que irá al Header en la sección de Authorization

3. Historia de usuario: HU_003

Como usuario

Dado que ingresé al sistema de gestión de proyectos

Cuando necesite actualizar la información personal

Entonces podré ingresar los datos que deseo actualizar

- Query:

    mutation UpdateUser($input: UpdateInput!) {
      updateUser(input: $input) {
        name
      }
    }

- Body:

    {
      "input": {
        "email": "",
        "documentId": 0,
        "name": "",
        "lastName": "",
        "role": "ADMIN",
        "password": ""
      }
    }

4. Historia de usuario: HU_004

Como administrador

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera ver la lista de los usuarios registrados en la plataforma (Tanto autorizados como no autorizados)

Entonces podré ver la información de los usuarios registrados en la plataforma

- Query:

    query AllUsers {
      allUsers {
        _id
        email
        documentId
        name
        lastName
        fullName
        role
        status
      }
    }

5. Historia de usuario: HU_005

Como administrador

Dado que estoy viendo la lista de los usuarios registrados en la plataforma

Cuando requiera aceptar un usuario en la plataforma

Entonces podré cambiar el estado del usuario

- Query:

    mutation UpdateUserStatus($input: UpdateUserStatusInput!) {
      updateUserStatus(input: $input) {
        status
      }
    }

- Body:

    {
      "input": {
        "email":"",
        "status":"AUTHORIZED"
      }
    }

6. Historia de usuario: HU_006

Como administrador 

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera ver la lista de proyectos registrados en la plataforma

Entonces podré ver la lista de los proyectos registrados en la plataforma

- Query:

    query AllProjects {
      allProjects {
        _id
        name
        generalObjective
        specificObjectives
        budget
        startDate
        endDate
        leader_id
        status
        phase
        leader {
          name
        }
      }
    }


7. Historia de usuario: HU_007

Como administrador

Dado que estoy viendo la lista de los proyectos registrados en la plataforma

Cuando requiera aprobar la creación de un proyecto

Entonces podré  actualizar el estado del  proyecto

- Query:

    mutation UpdateProjectPhase($input: UpdateProjectPhaseInput!) {
      updateProjectPhase(input: $input) {
        phase
      }
    }

- Body:

    {
      "input": {
        "name": "",
        "phase": "IN_PROGRESS"
      }
    }

8. Historia de usuario: HU_008

Como administrador

Dado que estoy viendo la lista de los proyectos registrados en la plataforma

Cuando requiera activar o inactivar un proyecto

Entonces podré  actualizar el estado del  proyecto

- Query:

    mutation UpdateProjectStatus($input: UpdateProjectStatusInput!) {
      updateProjectStatus(input: $input) {
        status
      }
    }

- Body:

    {
      "input": {
        "name":"",
        "status":"INACTIVE"
      }
    }

9. Historia de usuario: HU_009

Como administrador

Dado que estoy viendo la lista de los proyectos registrados en la plataforma

Cuando requiera cambiar la fase de un proyecto de “En desarrollo” a “Terminado”

Entonces podré  actualizar la fase del  proyecto.

- Query:

    mutation UpdateProjectPhase($input: UpdateProjectPhaseInput!) {
      updateProjectPhase(input: $input) {
        phase
      }
    }

- Body:

    {
      "input": {
        "name": "",
        "phase": "ENDED"
      }
    }

10. Historia de usuario: HU_010

Como líder

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera ver la lista de los estudiantes registrados en la plataforma (Tanto autorizados como no autorizados)

Entonces podré ver la información de los estudiantes registrados en la plataforma

- Query:

    query AllStudents {
      allStudents {
        name
      }
    }

11. Historia de usuario: HU_011

Como líder

Dado que que estoy viendo la lista de los estudiantes registrados en la plataforma

Cuando requiera aceptar un estudiante en la plataforma

Entonces podré cambiar el estado del estudiante de “Pendiente” a “Autorizado”

- Query:

    mutation UpdateUserStatus($input: UpdateUserStatusInput!) {
      updateUserStatus(input: $input) {
        status
      }
    }

- Body:

    {
      "input": {
        "email": "student4@mail.com",
        "status": "AUTHORIZED"
      }
    }

12. Historia de usuario: HU_012

Como líder

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera liderar un nuevo proyemcto

Entonces podré crear un nuevo proyecto

- Query:

    mutation NewProject($input: NewProjectInput!) {
      newProject(input: $input) {
        name
      }
    }

- Body:

    {
      "input": {
        "name":"",
        "generalObjective":"",
        "specificObjectives":[],
        "budget":0
        "startDate": "MM/DD/AAAA HH:MM",
        "endDate": "MM/DD/AAAA HH:MM"
      }
    }

13. Historia de usuario: HU_013

Como líder

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera ver los proyectos que lidero (Tanto los que están en estado “Activo” como “Inactivo”).

Entonces sólo podré listar los proyectos que tengo a cargo

- Query:

    query LeaderProjects {
      leaderProjects {
        name
      }
    }

14. Historia de usuario: HU_014

Como líder

Dado que estoy viendo la lista de los proyectos que he registrado en la plataforma

Cuando requiera actualizar los datos de uno de los proyectos que lidero y que está en estado “Activo”

Entonces podré editar la información relacionada al proyecto cuya información necesito actualizar (Solamente puede actualizar: Nombre del proyecto, los objetivos generales, específicos y el presupuesto)

- Query:

    mutation UpdateProject($input: UpdateProjectInput!) {
      updateProject(input: $input) {
        _id
      }
    }

- Body:

    {
      "input": {
        "_id": "",
        "name": "",
        "generalObjective": "",
        "specificObjectives": [],
        "budget": 0
      }
    }

15. Historia de usuario: HU_015

Como líder

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera revisar las solicitudes pendientes por aceptar o rechazar de estudiantes de inscripción a mis proyectos

Entonces podré listar las solicitudes realizadas por los estudiantes.

- Query:

    query LeaderEnrollments {
      leaderEnrollments {
        project {
          _id
        }
        student {
          _id
        }
        status
      }

16. Historia de usuario: HU_016

Como líder

Dado que estoy viendo la lista de solicitudes de inscripción a los proyectos que lidero

Cuando requiera cambiar el estado a la solicitudes

Entonces podré aceptar o rechazar sus inscripciones

- Query:

    mutation UpdateEnrollmentStatus($input: UpdateEnrollmentStatusInput!) {
      updateEnrollmentStatus(input: $input) {
        _id
      }
    }

- Body:

    {
      "input": {
        "_id":"",
        "status": ""
      }
    }

17. Historia de usuario: HU_017

Como líder

Dado que estoy viendo la lista de los proyectos que he registrado en la plataforma

Cuando necesite realizar una revisión a uno de mis proyectos

Entonces podré listar la información relacionada al proyecto que deseo revisar (Incluyendo los avances).

- Query:

    query LeaderProject($id: ID!) {
      leaderProject(_id: $id) {
        _id
      }
    }

- Body:

    {
      "id": ""
    }

18. Historia de usuario: HU_018

Como líder

Dado que estoy viendo la lista de los avances registrados en uno de los proyectos que lidero

Cuando necesite agregar observaciones a un avance en uno de mis proyectos

Entonces podré actualizar el campo de observaciones del avance seleccionado.

- Query:

    mutation UpdateAdvanceComments($input: UpdateAdvanceCommentsInput!) {
      updateAdvanceComments(input: $input) {
        comments
      }
    }

- Body:

    {
      "input": {
        "_id": "",
        "comments": ""
      }
    }

19. Historia de usuario: HU_019

Como estudiante

Dado que ingresé al sistema de gestión de proyectos

Cuando requiera ver la lista de proyectos registrados en la plataforma

Entonces podré ver la lista de los proyectos registrados en la plataforma

- Query:

    query AllProjects {
      allProjects {
        name
      }
    }

20. Historia de usuario: HU_020

Como estudiante

Dado que estoy viendo la lista de los proyectos registrados en la plataforma

Cuando requiera inscribirme en un proyecto

Entonces podré generar una solicitud de inscripción al proyecto

- Query:

    mutation NewEnrollment($projectId: ID!) {
      newEnrollment(project_id: $projectId) {
        _id
      }
    }

- Body:

    {
      "projectId": ""
    }

21. Historia de usuario: HU_021

Como estudiante

Dado que mi inscripción a un proyecto fue aceptada

Cuando requiera listar los avances de un proyecto en el que estoy inscrito

Entonces podré ver la lista de los avances del proyecto registrados

- Query:

    query StudentProjectAdvances($projectId: ID!) {
      studentProjectAdvances(projectID: $projectId) {
        _id
      }
    }

- Body:

    {
      "projectId": ""
    }

22. Historia de usuario: HU_022

Como estudiante

Dado que estoy viendo la lista de proyectos

Cuando requiera registrar avances a un proyecto en el que estoy inscrito (Y este se encuentra en estado activo)

Entonces podré ingresar la descripción de mi avance en el proyecto

- Query:

    mutation NewAdvance($input: NewAdvanceInput!) {
      newAdvance(input: $input) {
        _id
      }
    }

- Body:

    {
      "input": {
        "projectID":"",
        "advance": ""
      }
    }

23. Historia de usuario: HU_023

Como estudiante

Dado estoy viendo la lista de avances de un proyecto

Cuando requiera actualizar la información de un avance

Entonces podré modificar la descripción del avance

- Query:

    mutation UpdateAdvanceAdvance($input: UpdateAdvanceAdvanceInput!) {
      updateAdvanceAdvance(input: $input) {
        _id
      }
    }

- Body:

    {
      "input": {
        "_id": "",
        "advance": ""
      }
    }
