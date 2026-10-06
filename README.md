# University Research Opportunity Portal

Web application for faculty to post, view, update and manage research opportunities.


## Tech Stack
- Backend: Node.js, Express
- Database: MySQL
- Frontend: HTML, JavaScript, Bootstrap 5 (served by the backend)

## Project Structure
```
backend/    Express REST API
frontend/   index.html, app.js
database/   schema.sql
postman/    Postman collection
```

## Setup
1. Install Node.js (v18+) and MySQL.
2. Create the database and table:
   ```
   mysql -u root -p < database/schema.sql
   ```
3. Configure environment:
   ```
   cd backend
   cp .env.example .env
   ```
   Edit `.env` and set your MySQL password.
4. Install dependencies and start:
   ```
   npm install
   npm start
   ```
5. Open http://localhost:3000 (frontend). API base: http://localhost:3000/api/opportunities

## API Endpoints
| Method | Endpoint | Description | Success |
|---|---|---|---|
| POST | /api/opportunities | Create | 201 |
| GET | /api/opportunities | List all | 200 |
| GET | /api/opportunities/:id | Get one | 200 |
| PUT | /api/opportunities/:id | Update (partial fields allowed) | 200 |
| DELETE | /api/opportunities/:id | Delete | 200 |

Errors: 400 (invalid/missing data or bad ID), 404 (not found), 500 (server error).

## Testing
Import `postman/Research_Portal.postman_collection.json` into Postman and run the requests in order.
