# ResumeXpert

**ResumeXpert** is a full-stack web application for building professional, ATS-friendly resumes using beautiful templates. It features user authentication, resume CRUD operations, image uploads, and PDF export, with a modern React frontend and a secure Express/MongoDB backend.

---

## Table of Contents

- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Backend Setup](#backend-setup)
  - [Frontend Setup](#frontend-setup)
- [Usage Guide](#usage-guide)
- [Code Overview](#code-overview)
  - [Backend](#backend)
  - [Frontend](#frontend)
- [API Endpoints](#api-endpoints)
- [Customization](#customization)
- [Contributing](#contributing)
- [License](#license)

---

## Features

- User registration and login (JWT-based)
- Create, edit, and delete multiple resumes
- Upload profile images and thumbnails
- Choose from multiple resume templates and color themes
- Real-time resume preview and progress tracking
- Export resumes as PDF
- Responsive, modern UI with React and Tailwind CSS

---

## Project Structure

```
ResumeXpert/
  backend/      # Express.js + MongoDB API
    config/
    controllers/
    middlewares/
    models/
    routes/
    uploads/
    server.js
    package.json
  frontend/     # React + Vite client
    src/
      assets/
      components/
      context/
      pages/
      utils/
      App.jsx
      main.jsx
      index.css
    public/
    index.html
    package.json
```

---

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- npm
- MongoDB Atlas account (for cloud DB) or local MongoDB

---

### Backend Setup

1. **Install dependencies:**
   ```bash
   cd backend
   npm install
   ```

2. **Configure environment variables:**
   - Create a `.env` file in `backend/` with your MongoDB URI and JWT secret:
     ```
     MONGO_URI=your_mongodb_connection_string
     JWT_SECRET=your_jwt_secret
     ```
   - See `backend/config/db.js` for detailed MongoDB Atlas setup instructions.

3. **Start the backend server:**
   ```bash
   npm start
   ```
   - The server runs on [http://localhost:4000](http://localhost:4000) by default.

---

### Frontend Setup

1. **Install dependencies:**
   ```bash
   cd frontend
   npm install
   ```

2. **Start the frontend dev server:**
   ```bash
   npm run dev
   ```
   - The app runs on [http://localhost:5173](http://localhost:5173) by default.

3. **Configure API base URL:**
   - By default, the frontend points to the deployed backend. For local development, update `BASE_URL` in `frontend/src/utils/apiPaths.js` to `http://localhost:4000`.

---

## Usage Guide

1. **Register or log in** to your account.
2. **Create a new resume** from the dashboard.
3. **Fill in your details** (profile, contact, work experience, education, skills, projects, certifications, languages, interests).
4. **Choose a template and color theme** using the Theme Selector.
5. **Preview and download** your resume as a PDF.
6. **Manage multiple resumes** from your dashboard.

---

## Code Overview

### Backend

- **server.js**: Main entry, sets up Express, connects to MongoDB, and mounts routes.
- **config/db.js**: MongoDB connection logic and setup instructions.
- **models/User.js**: User schema (name, email, password).
- **models/Resume.js**: Resume schema (profile, contact, work, education, skills, etc.).
- **controllers/authController.js**: Handles registration, login, and profile retrieval.
- **controllers/resumeController.js**: Handles resume CRUD operations.
- **middlewares/**: Auth and file upload middleware.
- **routes/**: Auth and resume API routes.

### Frontend

- **src/pages/LandingPage.jsx**: Marketing landing page, authentication modals.
- **src/pages/Dashboard.jsx**: User dashboard, resume list, create/delete actions.
- **src/components/EditResume.jsx**: Main resume editor (multi-step, autosave, PDF export).
- **src/components/Forms.jsx**: Modular forms for each resume section.
- **src/components/ThemeSelector.jsx**: Select template and color theme.
- **src/components/TemplateOne/Two/Three.jsx**: Resume template renderers.
- **src/context/userContext.jsx**: User authentication state (React Context).
- **src/utils/apiPaths.js**: Centralized API endpoint definitions.
- **src/utils/axiosInstance.js**: Axios instance with auth and error handling.

---

## API Endpoints

**Auth:**
- `POST /api/auth/register` — Register new user
- `POST /api/auth/login` — Login
- `GET /api/auth/profile` — Get current user profile

**Resume:**
- `POST /api/resume` — Create new resume
- `GET /api/resume` — Get all resumes for user
- `GET /api/resume/:id` — Get resume by ID
- `PUT /api/resume/:id` — Update resume
- `DELETE /api/resume/:id` — Delete resume
- `POST /api/resume/:id/upload-images` — Upload images for a resume

---

## Customization

- **Add new templates:** Create a new component in `src/components/` and register it in `src/utils/data.js`.
- **Change color palettes:** Update the palette arrays in `src/utils/colors.js`.
- **Modify form fields:** Edit the schema in `backend/models/Resume.js` and update corresponding frontend forms.

---

## Contributing

1. Fork the repo and create your branch.
2. Commit your changes with clear messages.
3. Open a pull request describing your changes.

---

## License

This project is licensed under the ISC License. 