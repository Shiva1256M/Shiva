# Job Portal & Recruitment Management System

A React + JSON Server JobFinder capstone with user/admin login, job browsing, applications, tracking, editing and removal.

## Features

### User
- Browse and search jobs
- Save jobs
- User login/logout
- Apply for jobs
- My Applications page
- Track application status
- Edit application details
- Withdraw/remove an application
- Candidate dashboard showing only the logged-in user's applications

### Admin
- Separate admin login
- Admin application management dashboard
- View all applications
- Search/filter applications
- Update application status:
  - Applied
  - Under Review
  - Shortlisted
  - Rejected
  - Hired
- Remove applications
- View basic job/user counts

## Technologies

- React
- JavaScript
- Tailwind CSS
- Axios
- React Hook Form
- React Router
- JSON Server
- Vite

## Installation

Open the `job-portal` folder in VS Code.

```bash
npm install
```

## Run JSON Server

Terminal 1:

```bash
npm run server
```

JSON Server runs at:

```text
http://localhost:3001
```

## Run React

Terminal 2:

```bash
npm run dev
```

Vite normally runs at:

```text
http://localhost:5173
```

## Demo Login Accounts

### User
```text
Email: candidate@example.com
Password: demo123
```

### Admin
```text
Email: admin@example.com
Password: admin123
```

## Routes

```text
/                  Home
/jobs              Jobs
/jobs/:id          Job details
/apply/:id         Apply for a job
/saved-jobs        Saved jobs
/login             User/Admin login
/applications      Logged-in user's applications
/dashboard         Candidate dashboard
/admin             Admin application management
```

## API Endpoints

```text
GET     /jobs
GET     /jobs/:id
GET     /users
GET     /applications
POST    /applications
PATCH   /applications/:id
DELETE  /applications/:id
```

## Important Note

This project uses JSON Server as a local/demo backend. Passwords are stored in `db.json`, so this login system is intended for a capstone/demo project and is **not production authentication**.

For a real production application, authentication should be handled by a secure backend with hashed passwords, sessions/JWT, authorization, and protected APIs.


## Application visibility fix

New applications are saved with the logged-in user's `userId`. The User Dashboard and My Applications page fetch the complete applications collection and then filter by `userId`, which keeps application tracking reliable across JSON Server versions.

The Admin Panel always loads the complete applications collection, so every submitted application is visible to the admin.
