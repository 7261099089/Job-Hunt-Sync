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

| Route                                 | Description                                         |
| -------------------------------------- | --------------------------------------------------- |
| `/`                                   | Home page                                           |
| `/about-us`                           | About Us                                            |
| `/contact-us`                         | Contact Us                                          |
| `/jobs`                               | All Jobs                                            |
| `/my-profile`                         | My Profile *(protected)*                            |
| `/jobs/:id`                           | Job Details *(protected)*                           |
| `/jobs/:id/apply`                     | Apply for Job *(protected)*                         |
| `/dashboard/update-profile`           | User: Update Profile *(user only)*                  |
| `/dashboard/my-applications`          | User: My Applications *(user only)*                 |
| `/dashboard/application-details/:id`  | User: Application Details *(user only)*             |
| `/dashboard/my-applications/edit/:id` | User: Edit Application *(user only)*                |
| `/dashboard/saved-jobs`               | User: Saved Jobs *(user only)*                      |
| `/dashboard/manage-users`             | Admin: Manage Users *(admin only)*                  |
| `/dashboard/manage-applications`      | Admin: Manage Applications *(admin only)*           |
| `/dashboard/add-job`                  | Admin: Add Job *(admin only)*                       |
| `/dashboard/manage-jobs`              | Admin: Manage Jobs *(admin only)*                   |
| `/dashboard/manage-jobs/edit/:id`     | Admin: Edit Job *(admin only)*                      |
| `/dashboard/contact-messages`         | Admin: Contact Messages *(admin only)*              |
| `/*`                                  | Error/404                                           |

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