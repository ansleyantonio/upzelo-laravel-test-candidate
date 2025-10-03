# Laravel 11 Senior Developer Technical Test

Welcome to the Upzelo Laravel technical assessment! This test is designed to evaluate your Laravel 11 knowledge and should take approximately **45 minutes** to complete.

## Test Overview

You will build a simple **Task Management API** that demonstrates your understanding of:
- Laravel 11 features and best practices
- RESTful API design
- Database relationships and migrations
- Request validation
- API Resources

## Requirements

### 1. Database Schema
Create the following entities with proper relationships:

**Users Table** (already exists - you can extend it)
- id, name, email, email_verified_at, password, created_at, updated_at

**Projects Table**
- id, name, description, user_id (foreign key), created_at, updated_at

**Tasks Table**
- id, title, description, status (enum: pending, in_progress, completed), priority (enum: low, medium, high), project_id (foreign key), assigned_to (foreign key to users), due_date, created_at, updated_at

### 2. API Endpoints
Implement the following RESTful API endpoints:

#### Projects
- `GET /api/projects` - List all projects with their task counts
- `POST /api/projects` - Create a new project
- `GET /api/projects/{id}` - Show a specific project with its tasks

#### Tasks
- `GET /api/tasks` - List all tasks with filtering by status
- `POST /api/tasks` - Create a new task
- `PUT /api/tasks/{id}` - Update task status only

### 3. Requirements & Features

#### Request Validation
- Implement proper form request validation for all POST/PUT endpoints
- Include appropriate validation rules and custom error messages

#### API Resources
- Use Laravel API Resources to format JSON responses consistently
- Include related data where appropriate (e.g., project with tasks, task with assigned user)

#### Query Features
- Tasks endpoint should support filtering by `status` query parameter
- Projects endpoint should include task counts for each project

#### Business Logic
- A project can have multiple tasks
- A task belongs to one project and can be assigned to one user
- Add a simple method to calculate project completion percentage (already implemented in model)

### 4. Testing (Optional - Bonus Points)
If you have extra time, consider writing tests for:
- Creating a project
- Creating a task and assigning it to a project
- Updating task status

## Technical Requirements

- Use Laravel 11 features where applicable
- Follow PSR-12 coding standards
- Use proper HTTP status codes
- Implement proper error handling
- Use Eloquent relationships efficiently
- Follow Laravel naming conventions

## Getting Started

1. Fork this repository
2. Clone your fork locally
3. Run `composer install`
4. Copy `.env.example` to `.env` and configure your database
5. Run `php artisan key:generate`
6. Run `php artisan migrate`
7. Implement the required features
8. Run `php artisan test` to ensure your tests pass
9. Create a Pull Request with your solution

## Database Setup

The project is already configured to use SQLite for simplicity. The database file is located at `database/database.sqlite`.

## Evaluation Criteria

You will be evaluated on:

### Code Quality (25%)
- Clean, readable, and well-organized code
- Proper use of Laravel conventions and best practices
- Appropriate use of Laravel 11 features

### Functionality (35%)
- All required endpoints work correctly
- Proper request validation
- Correct HTTP status codes and responses
- Business logic implementation

### Database Design (20%)
- Proper relationships and foreign keys
- Efficient migrations
- Use of Eloquent features

### Testing (20%)
- Comprehensive feature tests
- Tests cover the main functionality
- Tests are well-written and meaningful

## Bonus Points (Optional)

If you finish early, consider implementing:
- **Feature tests** for your API endpoints (bonus points available)
- Additional CRUD operations (UPDATE/DELETE for projects)
- Priority filtering for tasks
- API documentation using Laravel's built-in tools

## Submission

1. Ensure all tests pass: `php artisan test`
2. Commit your changes with clear, descriptive commit messages
3. Create a Pull Request to this repository
4. Include any additional setup instructions in your PR description

## Time Limit

This test should take approximately **45 minutes**. Focus on core functionality first, then add polish if time permits.

## Questions?

If you have any questions about the requirements, feel free to ask in your PR or reach out to the hiring team.

Good luck! 🚀
