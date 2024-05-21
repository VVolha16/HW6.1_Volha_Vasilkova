# Sql Verifier: Task Creation

This API allows you to create a task

The API is available at `http://localhost:8080`

## Endpoints 

### API Authentication

**POST `/api/authenticate`**

To create a task, you need to register your API client with admin credentials:

|username |password  |
|---------|----------|
|admin    |    admin |

The request body needs to be in JSON format and include the following properties:

 - `username` - String
 - `password` - String
 - `rememberMe` - Boolean
 
 Example request:

 ```
 {
  "username": "admin",
  "password": "admin",
  "rememberMe": true
}
 ```

The response body will contain the id of access admin token. 

**Status codes**

| Status code                        | Description                                                                                                                       |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| 200 OK                             | Indicates a successful response                                                                                                   |
| 400 Bad Request                    | Indicates that the parameters provided are invalid or missing                                                                     |
| 401 Unauthorized                   | Indicates that the request has not been authenticated. Try changing the values for `username` and `password` to admin credentials |
| 500 Created Internal Service Error | Indicates that there is an Internal Service Error                                                                                 |


### Create a task

**POST `/api/tasks`**

Allows you to create a task. Requires authentication.

The request body needs to be in JSON format and include the following properties:

 - `text` - String
 - `answer` - String
 - `title` - String
 

 Example request:

 ```
POST /api/tasks
Authorization: Bearer <ADMIN ID TOKEN>
 
 {
  "text": "test_text",
  "answer": "test_answer",
  "title": "test_title"
}
 ```
 
 
 Example response:

```
 
 {
    "id": 1664,
    "text": "test_text",
    "answer": "test_answer",
    "title": "test_title"
}

```
 
 **Status codes**
 
| Status code                        | Description                                                                                                             |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| 201 Created                        | Indicates that the item has been created successfully                                                                   |
| 400 Bad Request                    | Indicates that the parameters provided are invalid or missing                                                           |
| 401 Unauthorized                   | Indicates that the request has not been authenticated. Try checking `Bearer <ADMIN ID TOKEN>` in `Authorization` header |
| 500 Created Internal Service Error | Indicates that there is an Internal Service Error                                                                       |
