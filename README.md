# Job Hunt Sync

Job Hunt Sync is a web application that helps users find, apply for, and manage job opportunities, while enabling employers to post and manage job listings. The platform is designed for both job seekers and employers, providing a seamless and secure experience.

> [!TIP]
> **Test User Credentials:**
> - **Email**: `tahmid@engineer.com`
> - **Password**: `Abc@123456`
> 
> **Test Admin Credentials:**
> - **Email**: `admin@job-hunt-sync.web.app`
> - **Password**: `Admin@123456`

## Features

* **Authentication** – Firebase-based user login, registration, and password reset
* **Job Listings** – Browse, search, and view detailed job postings
* **Apply & Manage Applications** – Apply for jobs, view application status, and edit applications
* **Admin Dashboard** – Post, edit, and manage jobs, users, and applications
* **User Dashboard** – View and update profile, track applications, save jobs
* **Contact & Feedback** – Contact form for user messages
* **Dark Mode Support** – Toggle between light and dark themes
* **Role-Based Access** – Admin and user route protection
* **Responsive Design** – Fully mobile-friendly with modern UI

## Tech Stack

| Category       | Tools                               |
| -------------- | ----------------------------------- |
| Frontend       | React                               |
| Styling        | Tailwind CSS, daisyUI               |
| HTTP Client    | Axios                               |
| Backend        | Express, MongoDB                    |
| Auth & Hosting | Firebase (Auth + Hosting), JWT      |
| Deployment     | Vercel                              |

## Routing Overview

| Route                        | Description                                 |
| ---------------------------- | ------------------------------------------- |
| `/`                          | Home page                                   |
| `/about-us`                  | About the platform                          |
| `/contact-us`                | Contact form                                |
| `/login`                     | Login page                                  |
| `/register`                  | Registration page                           |
| `/forget-password`           | Reset password                              |
| `/my-profile`                | View your profile *(protected)*             |
| `/dashboard`                 | User/Admin dashboard *(protected)*          |
| `/dashboard/manage-jobs`     | Admin: Manage all jobs *(admin only)*       |
| `/dashboard/add-job`         | Admin: Add new job *(admin only)*           |
| `/dashboard/manage-users`    | Admin: Manage users *(admin only)*          |
| `/dashboard/manage-apps`     | Admin: Manage applications *(admin only)*   |
| `/dashboard/my-applications` | User: View your applications *(protected)*  |
| `/dashboard/saved-jobs`      | User: Saved jobs *(protected)*              |
| `/jobs`                      | Browse all jobs                             |
| `/jobs/:id`                  | Job details                                 |
| `/apply/:id`                 | Apply for a job *(protected)*               |
| `/*`                         | 404 Not Found page                          |

## Installation

1. **Clone the repository**

	```bash
	git clone https://github.com/tahmid-sarker/Job-Hunt-Sync.git
	```

2. **Navigate to the client directory and install dependencies**:

   ```bash
   cd Job-Hunt-Sync/client
   npm install
   ```

3. **Navigate to the server directory and install dependencies**:

   ```bash
   cd ../server
   npm install
   ```

4. **Setup Environment Variables**

	**Client (`client/.env`)**:

	```
	VITE_API_KEY=yourFirebaseApiKey
	VITE_AUTH_DOMAIN=yourFirebaseAuthDomain
	VITE_PROJECT_ID=yourFirebaseProjectId
	VITE_STORAGE_BUCKET=yourFirebaseStorageBucket
	VITE_MESSAGING_SENDER_ID=yourFirebaseMessagingSenderId
	VITE_APP_ID=yourFirebaseAppId
	VITE_API_URL=yourBackendApiUrl
	```

	**Server (`server/.env`)**:

	```
	DB_USER=yourMongoDBUser
	DB_USER=yourMongoDBPassword
	JWT_ACCESS_SECRET=yourJWTSecretKey
    FIREBASE_ADMIN_KEYS=yourFirebaseAdminCredentialsJSON
	```

5. **Run the backend server**:

   ```bash
   node index.js
   ```

6. **Run the frontend development server** (in a new terminal at `client` folder):

   ```bash
   npm run dev
   ```

7. Open `http://localhost:5173` in your browser to view the project.

## Project Structure

```
client/
└── src/
	 ├── assets/
	 ├── components/
	 │   ├── auth/
	 │   │   ├── ForgetPassword.jsx
	 │   │   ├── Login.jsx
	 │   │   └── Register.jsx
	 │   └── shared/
	 │       ├── DarkModeToggler.jsx
	 │       └── DynamicTitle.jsx
	 ├── config/
	 │   └── firebase.config.js
	 ├── context/
	 │   ├── AuthContext.jsx
	 │   ├── AuthProvider.jsx
	 │   ├── ThemeContext.jsx
	 │   └── ThemeProvider.jsx
	 ├── hooks/
	 │   └── useAuth.jsx
	 ├── layout/
	 │   ├── DashboardLayout.jsx
	 │   ├── Footer.jsx
	 │   ├── Header.jsx
	 │   └── MainLayout.jsx
	 ├── pages/
	 │   ├── AboutUs.jsx
	 │   ├── ContactUs.jsx
	 │   ├── Error.jsx
	 │   ├── MyProfile.jsx
	 │   ├── Dashboard/
	 │   │   ├── Admin/
	 │   │   │   ├── AddJob.jsx
	 │   │   │   ├── ContactMessages.jsx
	 │   │   │   ├── EditJob.jsx
	 │   │   │   ├── ManageApplications.jsx
	 │   │   │   ├── ManageJobs.jsx
	 │   │   │   └── ManageUsers.jsx
	 │   │   └── User/
	 │   │       ├── ApplicationDetails.jsx
	 │   │       ├── EditApplication.jsx
	 │   │       ├── MyApplications.jsx
	 │   │       ├── SavedJobs.jsx
	 │   │       └── UpdateProfile.jsx
	 │   ├── Home/
	 │   │   ├── FeaturedJobs.jsx
	 │   │   ├── Hero.jsx
	 │   │   ├── Home.jsx
	 │   │   ├── HowItWorks.jsx
	 │   │   └── Testimonials.jsx
	 │   └── Jobs/
	 │       ├── Apply.jsx
	 │       ├── JobDetails.jsx
	 │       └── Jobs.jsx
	 ├── routes/
	 │   ├── AdminRoutes.jsx
	 │   ├── PrivateRoutes.jsx
	 │   ├── Router.jsx
	 │   └── UserRoutes.jsx
	 ├── index.css
	 ├── main.jsx
	 └── index.html

server/
└── index.js
```

## Credits

This project was developed by [Md. Tahmid Sarker Mahi](https://tahmid-sarker.github.io).