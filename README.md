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

## Sorting
You can sort the results using the `_sort` parameter:

- Sort by UID: `/employees?_sort=uid`
- Sort by name: `/employees?_sort=name`
- Sort by department: `/employees?_sort=department`

You can also specify the order:
- Ascending (default): `/employees?_sort=uid`
- Descending: `/employees?_sort=uid&_order=desc`

## Pagination
You can paginate the results using `_page` and `_limit` parameters:

- Limit results per page: `/employees?_limit=5`
- Get specific page: `/employees?_page=2&_limit=5`
- Get total count in response headers: Response includes `X-Total-Count`

Examples:
- First 5 employees: `/employees?_page=1&_limit=5`
- Next 5 employees: `/employees?_page=2&_limit=5`
- Combine with sorting: `/employees?_sort=name&_page=1&_limit=5`

## Operators and Search

### Operators
You can use various operators for advanced filtering:

- Greater than: `/employees?id_gte=2`
- Less than: `/employees?id_lte=5`
- Not equal: `/employees?department_ne=IT`
- Like: `/employees?name_like=John`
- Regular expression: `/employees?name_like=^E`

### Full-text Search
Use `q` parameter for full-text search across all fields:

- Search across all fields: `/employees?q=John`
- Combine with filters: `/employees?q=John&department=IT`
- Combine with pagination: `/employees?q=John&_page=1&_limit=5`

### Multiple Conditions
You can combine multiple conditions:

- AND condition: `/employees?department=IT&name_like=John`
- Multiple values: `/employees?department=IT&department=HR`

## Relationships
You can access related resources using the following endpoints:

### Get Departments with Employees
```
GET http://localhost:4000/departments?_embed=employees
```
```
{
  "id": 1,
  "uid": "UID001",
  "name": "Employee 1",
  "photo": "https://loremflickr.com/640/480",
  "mobile": "123-456-7890",
  "department": "HR"
},
...
```

## Contributing
Feel free to submit issues and enhancement requests.