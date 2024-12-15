# Employee Management System

![Screenshot 2024-12-15 171648](https://github.com/user-attachments/assets/b93233de-996b-4826-9036-7acfd64a48b4)
![Screenshot 2024-12-15 171718](https://github.com/user-attachments/assets/bbf65f03-b4ef-432b-96f0-f1040a306316)
![Screenshot 2024-12-15 171741](https://github.com/user-attachments/assets/64ec9b6a-a55f-4657-a7d2-bf800817f482)
![Screenshot 2024-12-15 171800](https://github.com/user-attachments/assets/737ad427-e449-488b-90d7-6bc5d9dc1b6f)
![Screenshot 2024-12-15 171822](https://github.com/user-attachments/assets/1d8ab5f9-2c53-47d1-b228-fea4276fd499)
![Screenshot 2024-12-15 171852](https://github.com/user-attachments/assets/f11e371f-74af-4d3b-97b3-ad6ccfc41dc3)

## Project Overview

This Employee Management System is a full-stack application built with a .NET 8 API backend and an Angular frontend. It provides CRUD (Create, Read, Update, Delete) operations for managing employee data.

## Table of Contents

- [Employee Management System](#employee-management-system)
	- [Project Overview](#project-overview)
	- [Table of Contents](#table-of-contents)
	- [Project Structure](#project-structure)
		- [Backend (.NET 8 API)](#backend-net-8-api)
		- [Frontend (Angular)](#frontend-angular)
	- [Technology Stack](#technology-stack)
	- [Design Decisions](#design-decisions)
	- [Challenges Faced](#challenges-faced)
	- [Setup and Installation](#setup-and-installation)
	- [Usage](#usage)
	- [API Endpoints](#api-endpoints)
	- [Future Improvements](#future-improvements)

## Project Structure

The project is divided into two main parts:

### Backend (.NET 8 API)

```sh
EmployeeManagementAPI/
├── CQRS
│   ├── Commands
│   │   └── CreateEmployeeCommand.cs
│   └── Handlers
│       └── CreateEmployeeHandler.cs
├── Controllers/
│   └── EmployeesController.cs
├── Models/
│   └── Employee.cs
├── Data/
│   └── EmployeeDbContext.cs
├── Properties
│   └── launchSettings.json
├── appsettings.json
└── Program.cs
```

### Frontend (Angular)

```sh
employee-management-system/
├── src/
│   ├── app/
│   │   ├── components/
│   │   │   ├── employee-list/
│   │   │   ├── employee-detail/
│   │   │   └── employee-form/
│   │   ├── services/
│   │   │   └── employee.service.ts
│   │   ├── models/
│   │   │   └── employee.model.ts
│   │   ├── app.component.ts
│   │   ├── app.component.html
│   │   ├── app.component.css
│   │   └── app.routes.ts
│   ├── index.html
│   ├── main.server.ts
│   ├── main.ts
│   └── styles.css
├── angular.json
├── package.json
└── tsconfig.json
```

## Technology Stack

- Backend:
  - .NET 8
  - Entity Framework Core
  - SQLite Database
- Frontend:
  - Angular 15+
  - TypeScript
  - RxJS

## Design Decisions

1. **Standalone Components**: We used Angular's standalone components to reduce the need for NgModules and simplify the application structure.

2. **Service-based Architecture**: The EmployeeService acts as an intermediary between the components and the API, promoting separation of concerns.

3. **Reactive Programming**: We utilized RxJS Observables for handling asynchronous operations, making the code more maintainable and easier to reason about.

4. **Routing**: Angular Router was implemented to create a single-page application experience, allowing for seamless navigation between views.

5. **REST API**: The backend follows RESTful principles, providing a clear and consistent interface for CRUD operations.

## Challenges Faced

1. **HttpClient Injection**: Initially, we faced issues with injecting the HttpClient into our services and components. This was resolved by properly providing the HttpClientModule in the AppComponent and using provideHttpClient() in the main.ts file.

2. **Standalone Components Setup**: Transitioning to standalone components required careful management of imports and providers, which was a learning curve but ultimately led to a more streamlined application structure.

3. **Cross-Origin Resource Sharing (CORS)**: Ensuring proper CORS configuration on the backend to allow requests from the Angular frontend.

## Setup and Installation

1. Clone the repository
2. Backend Setup:
   - Navigate to the EmployeeManagementAPI directory
   - Run `dotnet restore`
   - Run `dotnet run`
3. Frontend Setup:
   - Navigate to the employee-management-system directory
   - Run `npm install`
   - Run `ng serve`

## Usage

Once both the backend and frontend are running, navigate to `http://localhost:4200` in your web browser. From there, you can:

- View the list of employees
- Add a new employee
- Edit existing employee details
- Delete an employee

## API Endpoints

- GET /api/employees - Retrieve all employees
- GET /api/employees/{id} - Retrieve a specific employee
- POST /api/employees - Create a new employee
- PUT /api/employees/{id} - Update an existing employee
- DELETE /api/employees/{id} - Delete an employee

## Future Improvements

1. Implement authentication and authorization
2. Add pagination for the employee list
3. Implement sorting and filtering options
4. Add unit and integration tests
5. Improve error handling and user feedback
6. Enhance the UI/UX design
