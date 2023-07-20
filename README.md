# Todo-APP-mvc

# Todo-APP

## Table Of Content
- [Frameworks and Language Used](#frameworks-and-language-used)
- [Data Flow](#data-flow)
    - [Controller](#controller)
    - [Services](#services)
    - [Repository](#repository)
    - [BeanFactory](#beanfactory)
    - [Database Design](#database-design)
- [Data Structure Used](#data-structure-used)
- [Project Summary](#project-summary)
- [Getting Started](#getting-started)
- [Testing Endpoints](#testing-endpoints)
- [License](#license)

## Frameworks and Language Used
- Java 17
- Spring Boot

## Data Flow

### Controller
The controller handles incoming HTTP requests and delegates them to the appropriate service methods. It exposes the following endpoints:

- `GET /todos`: Retrieve all todos.
- `GET /todo/done`: Retrieve all done todos.
- `GET /todo/undone`: Retrieve all undone todos.
- `POST /todo`: Add a new todo.
- `PUT /todo/{todoId}/{status}`: Mark a todo as done or undone based on the `todoId`.
- `DELETE /todo`: Remove a todo based on the `todoId`.

### Services
The services layer contains business logic and interacts with the TodoRepo to fetch and manipulate data. It provides the following methods:

- `getAllTodos()`: Get all todos.
- `getAllDoneTodos()`: Get all done todos.
- `getUnDoneTodos()`: Get all undone todos.
- `addTodo()`: Add a new todo.
- `updateTodoStatus()`: Update the status of a todo.
- `removeTodo()`: Remove a todo.

### Repository
The repository layer contains the TodoRepo class, which manages the list of todos. It provides the following methods:

- `getMyTodos()`: Get the list of todos.
- `add()`: Add a new todo to the list.
- `delete()`: Delete a todo from the list.

### BeanFactory
The BeanFactory class is a configuration class that creates and manages the list of todos as a Spring bean.

### Database Design
The application currently uses an in-memory list to store todos. A more robust database design can be implemented in a real-world scenario.

## Data Structure Used
- List: Used to store and manage the list of todos.

## Project Summary
This Todo-APP project is a simple web application that allows users to manage their todos. It provides endpoints to add, retrieve, update, and remove todos. The application is built using Java 17 and the Spring Boot framework.

## Getting Started
To run the Todo-APP locally, follow these steps:
1. Clone the repository from [Todo App](https://github.com/ayaan097/Todo-APP-mvc.git).
2. Build the project using Maven.
3. Run the `TodoAppApplication` class to start the application.

## Testing Endpoints
You can test the endpoints using tools like Postman or cURL. Here are some sample requests:
- `GET http://localhost:8080/todos`: Retrieve all todos.
- `POST http://localhost:8080/todo`: Add a new todo (send JSON payload with todo details).
- `PUT http://localhost:8080/todo/{todoId}/{status}`: Update the status of a todo.
- `DELETE http://localhost:8080/todo?todoId={todoId}`: Remove a todo based on the `todoId`.

## License
This project is licensed under the [MIT License](LICENSE).
