# JSON Server Mock API

A lightweight mock API server using JSON Server to provide fake data for frontend development and testing.

## Description

This project uses [JSON Server](https://github.com/typicode/json-server) to create a full fake REST API with zero coding. It's perfect for prototyping and mocking backend services during frontend development.

## Features

- Full REST API with zero coding
- Runs on port 4000
- Supports GET, POST, PUT, PATCH, and DELETE operations
- Data persistence using db.json file
- Cross-origin resource sharing (CORS) enabled

## Prerequisites

- Node.js (v12 or higher)
- npm (Node Package Manager)

## Installation

1. Clone the repository:
``` bash
git clone https://github.com/CodeArtisanRiz/json-server.git
npm install
npm run serve-json
```
- The server will start running at http://localhost:4000
## API Endpoints
### Employees 

- Get all employees

```
GET http://localhost:4000/employees
```
- Filter employees by department
```
GET http://localhost:4000/employees?department=IT
```

- Get employee by ID
```
GET http://localhost:4000/employees/1
```
```
{
  "id": 1,
  "uid": "UID001",
  "name": "Employee 1",
  "photo": "https://loremflickr.com/640/480",
  "mobile": "123-456-7890",
  "department": "HR"
}
```
## Available Filters
You can filter the employees using various query parameters:

- By Department: /employees?department=IT
- By ID: /employees?id=1
- By UID: /employees?uid=UID001
- Search by Name: /employees?name_like=Employee
## Contributing
Feel free to submit issues and enhancement requests.