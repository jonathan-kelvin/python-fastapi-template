## Introduction
This app structure is a base for the construction of application REST APIs

The responsibility of applications built in this manner is to focus on the business logic of the web service by centering around the following topics:
- Models (aka Entities) - Using Sqlalchemy's base class provide an ORM with the application database. Entity models defined here are to support the transactional work - typically CRUD operations.
- Repositories - Using an `async session` from SQLAlchemy, this layer helps to manage the *dumb* operations between the application code, and the database.
- Services - The service layer is the orchestration layer, it should contain most of the business logic.
- Routers (aka Controllers) - Controllers basically help navigate data flows into and out of endpoints. As far as possible, they should be kept light-weight. Common activities include authentication, input parameter, and basic data validation.
- Schemas - These are data classes that focus on keeping data flows in/out of endpoints strongly-typed. These will provide a good basis for the Swagger documentation.

The above are just very high-level views of the components of the application. There are still many engineering considerations excluded - e.g. API versioning, async operations, handling N + 1 database queries, relationship mapping, etc.

## Requirements
Requires:
- Python >= 3.11
- Anaconda / miniconda to create virtual environments

## Dependencies
Packages used:
- FastAPI - Backend framework
- SQLAlchemy - Object Relational Mapping (ORM)
- Pydantic - API validation
- Swagger - Documentation
- Pytest - Testing
- Black - Code formatting
