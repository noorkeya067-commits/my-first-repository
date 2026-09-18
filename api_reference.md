\# API Reference: Create a New Task



\## Endpoint



\*\*Method:\*\* `POST`



\*\*Path:\*\* `/api/v1/projects/{projectId}/tasks`



\## Description



This endpoint creates a new task inside a specified project in a project management application. The user must be authenticated and have permission to create tasks in the project.



A task requires a title, an assignee, a due date, and a priority level. The description is optional.



\## Path Parameters



| Name        | Data Type | Required | Description                                                  |

| ----------- | --------- | -------- | ------------------------------------------------------------ |

| `projectId` | string    | Yes      | The unique ID of the project where the task will be created. |



\## Query Parameters



This endpoint does not use query parameters.



\## Request Body



The request body must be sent as JSON.



| Name          | Data Type              | Required | Description                                                              |

| ------------- | ---------------------- | -------- | ------------------------------------------------------------------------ |

| `title`       | string                 | Yes      | The name or title of the task.                                           |

| `description` | string                 | No       | Additional information about the task.                                   |

| `assigneeId`  | string                 | Yes      | The unique ID of the user assigned to the task.                          |

| `dueDate`     | string (ISO 8601 date) | Yes      | The date when the task should be completed.                              |

| `priority`    | string                 | Yes      | The priority of the task. Allowed values are `low`, `medium`, or `high`. |



\## Request Headers



| Header          | Required | Description                                                  |

| --------------- | -------- | ------------------------------------------------------------ |

| `Authorization` | Yes      | Contains the authentication token. Format: `Bearer <token>`. |

| `Content-Type`  | Yes      | Indicates that the request body is JSON.                     |

| `Accept`        | Yes      | Indicates that the client expects a JSON response.           |



\## Example Request



```http

POST /api/v1/projects/proj-1001/tasks HTTP/1.1

Host: api.example.com

Authorization: Bearer eyJhbGciOiJIUzI1NiIs...

Content-Type: application/json

Accept: application/json

```



\### Example Request Body



```json

{

&#x20; "title": "Prepare project presentation",

&#x20; "description": "Create the presentation slides and review them with the project team.",

&#x20; "assigneeId": "user-2045",

&#x20; "dueDate": "2026-10-15",

&#x20; "priority": "high"

}

```



\## Response Codes



| HTTP Status                 | Meaning                 | Description                                                                                       |

| --------------------------- | ----------------------- | ------------------------------------------------------------------------------------------------- |

| `201 Created`               | Task created            | The task was successfully created.                                                                |

| `400 Bad Request`           | Invalid request         | One or more request fields are missing or incorrectly formatted.                                  |

| `401 Unauthorized`          | Authentication required | The authentication token is missing or invalid.                                                   |

| `403 Forbidden`             | Access denied           | The user is authenticated but does not have permission to create a task in the project.           |

| `404 Not Found`             | Resource not found      | The specified project or assignee user does not exist.                                            |

| `409 Conflict`              | Conflict                | The request conflicts with the current state of the project.                                      |

| `422 Unprocessable Entity`  | Validation error        | The request format is valid, but one or more values fail validation, such as an invalid priority. |

| `500 Internal Server Error` | Server error            | An unexpected problem occurred on the server.                                                     |



\## Example Successful Response



\*\*HTTP Status:\*\* `201 Created`



```json

{

&#x20; "id": "task-7890",

&#x20; "projectId": "proj-1001",

&#x20; "title": "Prepare project presentation",

&#x20; "description": "Create the presentation slides and review them with the project team.",

&#x20; "assigneeId": "user-2045",

&#x20; "dueDate": "2026-10-15",

&#x20; "priority": "high",

&#x20; "status": "pending",

&#x20; "createdAt": "2026-09-18T09:30:00Z",

&#x20; "createdBy": "user-1020"

}

```



\## Response Field Descriptions



| Name          | Data Type | Description                                        |

| ------------- | --------- | -------------------------------------------------- |

| `id`          | string    | Unique ID assigned to the newly created task.      |

| `projectId`   | string    | ID of the project containing the task.             |

| `title`       | string    | Title of the created task.                         |

| `description` | string    | Description supplied when the task was created.    |

| `assigneeId`  | string    | ID of the user assigned to the task.               |

| `dueDate`     | string    | Task due date.                                     |

| `priority`    | string    | Task priority: `low`, `medium`, or `high`.         |

| `status`      | string    | Current status of the task.                        |

| `createdAt`   | string    | Date and time when the task was created.           |

| `createdBy`   | string    | ID of the authenticated user who created the task. |



