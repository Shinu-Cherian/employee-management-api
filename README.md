Employee Management REST API
Project Overview

This project is a secure Employee Management REST API built using Python and Django REST Framework.
It allows a company to add, view, update, and delete employee details.
All APIs are protected using token-based authentication (JWT), so only authorized users can access them.

Features

Secure authentication using JWT

Create, Read, Update, Delete (CRUD) employee records

Email validation and uniqueness check

Filtering employees by department and role

Pagination (10 employees per page)

Proper HTTP status codes and error handling

Tested using Postman

Technology Stack

Python

Django

Django REST Framework

JWT Authentication (SimpleJWT)

SQLite (default database)

Postman (for API testing)

Project Setup (Run Locally)
1. Clone the repository
git clone <your-repository-url>
cd employee_api

2. Create virtual environment
python -m venv venv
venv\Scripts\activate

3. Install dependencies
pip install django djangorestframework djangorestframework-simplejwt

4. Run migrations
python manage.py migrate

5. Create admin user
python manage.py createsuperuser

6. Start the server
python manage.py runserver


Server runs at:

http://127.0.0.1:8000/

Authentication (JWT)
Generate Token

POST

/api/token/


Body:

{
  "username": "your_username",
  "password": "your_password"
}


Response:

{
  "refresh": "token",
  "access": "token"
}


➡️ Use the access token as a Bearer Token in Postman for all protected APIs.

API Endpoints
Create Employee

POST

/api/employees/

{
  "name": "John Doe",
  "email": "john@example.com",
  "department": "Engineering",
  "role": "Developer"
}


Response: 201 Created

List Employees

GET

/api/employees/


Supports pagination:

/api/employees/?page=2

Filter Employees
/api/employees/?search=Engineering

Retrieve Employee

GET

/api/employees/{id}/

Update Employee

PUT

/api/employees/{id}/

Delete Employee

DELETE

/api/employees/{id}/


Response: 204 No Content

Error Handling
Scenario	Status Code
Successful creation	201 Created
Invalid input	400 Bad Request
Unauthorized access	401 Unauthorized
Employee not found	404 Not Found
Successful deletion	204 No Content
Testing

APIs tested using Postman

Authentication tested with valid and invalid tokens

Duplicate email validation verified

Unauthorized access blocked successfully

Summary

This project demonstrates:

RESTful API design

Secure authentication

Clean backend structure

Proper validation and error handling

Real-world backend development practices

Author

Shinu Cherian
Python Backend Developer (Candidate)
