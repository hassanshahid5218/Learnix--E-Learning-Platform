# 🎓 Learnix — Modern Learning Management System

**Learnix** is a full-stack Learning Management System (LMS) designed to provide a complete online learning experience for students while giving administrators powerful tools to manage courses, users, orders, content, notifications, and platform analytics.

The platform combines a modern **Next.js frontend** with a scalable **Node.js/Express backend**, providing authentication, course management, Stripe payments, real-time notifications, cloud media storage, Redis caching, and an admin dashboard in one complete application.

---

## 🌐 Live Demo

### 🚀 Learnix

**Live Application:**
https://learnix-frontend-lyart.vercel.app/

**Backend API:**
https://learnix-backend-gamma.vercel.app

---

# ✨ Features

## 👨‍🎓 Student Experience

* User registration and login
* Email account activation
* Secure authentication
* Google/GitHub authentication support
* User profile management
* Avatar management
* Browse available courses
* Search and explore courses
* View detailed course information
* Course enrollment
* Secure course purchasing
* Stripe payment integration
* Order confirmation emails
* Access purchased courses
* Course learning interface
* Real-time notifications
* Responsive interface across devices

---

## 📚 Course Management

Learnix provides a complete course management system.

### Course Features

* Create courses
* Edit courses
* Delete courses
* Course thumbnails
* Course categories
* Course descriptions
* Course pricing
* Course sections
* Course lectures
* Course videos
* Course resources
* Course purchase tracking
* Student enrollment

Administrators can manage the complete course lifecycle through the admin dashboard.

---

# 🛠️ Admin Dashboard

The admin dashboard provides centralized control over the platform.

### Admin Features

* Dashboard overview
* User management
* Course management
* Course creation
* Course editing
* Invoice/order management
* FAQ management
* Platform categories
* Team management
* Hero section management
* Analytics
* Notification management
* Admin profile/settings

### Analytics

The dashboard provides statistics for:

* Total users
* Course growth
* Orders
* Monthly activity
* Course purchases
* Platform performance

---

# 💳 Stripe Payment Integration

Learnix integrates **Stripe** for secure online course purchases.

### Payment Flow

```text
Student
   │
   ▼
Select Course
   │
   ▼
Checkout
   │
   ▼
Stripe Payment Intent
   │
   ▼
Payment Confirmation
   │
   ▼
Backend Verification
   │
   ▼
Create Order
   │
   ├──► Enroll Student
   │
   ├──► Update Course Purchases
   │
   ├──► Create Notification
   │
   └──► Send Confirmation Email
```

Payments are verified on the backend before the course is added to the student's account.

---

# 🔐 Authentication & Security

Learnix uses a secure authentication architecture.

### Authentication Features

* JWT-based authentication
* Access tokens
* Refresh tokens
* HTTP-only cookies
* Password hashing with bcrypt
* Protected routes
* Admin authorization
* Account activation
* Session/token management
* Redis-backed authentication data

Authentication is shared between the frontend and backend through protected API communication.

---

# 🔔 Real-Time Notifications

Learnix uses **Socket.IO** to provide real-time communication.

For example, when an important event occurs:

```text
Backend
   │
   ▼
Socket.IO
   │
   ▼
Connected Admin/User
   │
   ▼
Real-Time Notification
```

This allows notifications to appear without requiring the user to manually refresh the page.

---

# ☁️ Cloud Services

The application integrates several cloud services:

| Service         | Purpose                  |
| --------------- | ------------------------ |
| MongoDB Atlas   | Production database      |
| Cloudinary      | Image/media storage      |
| Redis           | Caching and session data |
| Stripe          | Online payments          |
| Vercel          | Application deployment   |
| SMTP/Nodemailer | Email delivery           |

---

# 🧑‍💻 Tech Stack

## Frontend

* **Next.js**
* **React**
* **TypeScript**
* **Redux Toolkit**
* **RTK Query**
* **Tailwind CSS**
* **Material UI**
* **Formik**
* **Yup**
* **Stripe.js**
* **Socket.IO Client**
* **NextAuth**

## Backend

* **Node.js**
* **Express.js**
* **TypeScript**
* **MongoDB**
* **Mongoose**
* **Redis**
* **Socket.IO**
* **JWT**
* **bcryptjs**
* **Stripe**
* **Cloudinary**
* **Nodemailer**
* **EJS**

## Development & Deployment

* Git
* GitHub
* Postman
* VS Code
* MongoDB Atlas
* Vercel

---

# 🏗️ Project Architecture

Learnix follows a full-stack client-server architecture.

```text
                         ┌─────────────────────┐
                         │      Learnix UI      │
                         │      Next.js         │
                         └──────────┬──────────┘
                                    │
                         REST API / Socket.IO
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │   Express Backend   │
                         │      Node.js        │
                         └──────────┬──────────┘
                                    │
             ┌──────────────────────┼──────────────────────┐
             │                      │                      │
             ▼                      ▼                      ▼
       ┌───────────┐          ┌───────────┐          ┌───────────┐
       │ MongoDB   │          │   Redis   │          │ Cloudinary│
       │  Atlas    │          │           │          │           │
       └───────────┘          └───────────┘          └───────────┘
                                   
                                    │
                    ┌───────────────┴───────────────┐
                    │                               │
                    ▼                               ▼
               ┌───────────┐                  ┌───────────┐
               │  Stripe   │                  │  Email    │
               │ Payments  │                  │  Service  │
               └───────────┘                  └───────────┘
```

---

# 📁 Repository Structure

The project is organized into separate frontend and backend applications:

```text
Learnix/
│
├── client/                    # Next.js frontend
│   ├── app/
│   ├── components/
│   ├── redux/
│   ├── hooks/
│   ├── utils/
│   └── ...
│
├── server/                    # Node.js backend
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── middleware/
│   ├── utils/
│   ├── mails/
│   └── ...
│
├── README.md
└── ...
```

> Folder names can be adjusted to match the exact structure of your repository.

---

# 🔄 Application Flow

A simplified Learnix workflow:

```text
                  ┌──────────────┐
                  │     User     │
                  └──────┬───────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Authentication  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Browse Courses  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Course Details  │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Stripe Checkout │
                └────────┬────────┘
                         │
                         ▼
                ┌─────────────────┐
                │ Payment Verify  │
                └────────┬────────┘
                         │
              ┌──────────┼──────────┐
              ▼          ▼          ▼
          Enrollment   Order    Notification
              │          │          │
              └──────────┼──────────┘
                         ▼
                  Access Course
```

---

# ⚙️ Getting Started

## Prerequisites

Make sure you have installed:

* Node.js
* npm
* Git
* MongoDB or MongoDB Atlas
* Redis
* Stripe account
* Cloudinary account
* SMTP/email provider

---

## 1. Clone the Repository

```bash
https://github.com/hassanshahid5218/Learnix--E-Learning-Platform/
```

```bash
cd Learnix
```

# 💻 Frontend Setup

Move into the frontend directory:

```bash
cd client
```

Install dependencies:

```bash
npm install
```

Create:

```text
.env.local
```

Add the required frontend environment variables.

Example:

```env
NEXT_PUBLIC_SERVER_URI=http://localhost:8000
NEXT_PUBLIC_SOCKET_SERVER_URI=http://localhost:8000
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
```

Start the development server:

```bash
npm run dev
```

Frontend:

```text
http://localhost:3000
```

---

# 🖥️ Backend Setup

Open another terminal:

```bash
cd server
```

Install dependencies:

```bash
npm install
```

Create:

```text
.env
```

Example:

```env
PORT=8000

DB_URL=your_mongodb_connection_string

ORIGIN=http://localhost:3000

ACCESS_TOKEN=your_access_token_secret
REFRESH_TOKEN=your_refresh_token_secret

REDIS_URL=your_redis_connection_string

CLOUD_NAME=your_cloudinary_cloud_name
CLOUD_API_KEY=your_cloudinary_api_key
CLOUD_SECRET_KEY=your_cloudinary_secret

STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key

SMTP_HOST=your_smtp_host
SMTP_PORT=your_smtp_port
SMTP_MAIL=your_email
SMTP_PASSWORD=your_email_password
```

Start the backend:

```bash
npm run dev
```

Backend:

```text
http://localhost:8000
```

Test the backend:

```text
http://localhost:8000/test
```

Expected response:

```json
{
  "success": true,
  "message": "API is working"
}
```

---

# 🔑 Environment Variables

Make sure these files are included in `.gitignore`:

```text
.env
.env.local
.env.production
.env.development
```

For production, configure environment variables directly in your deployment platform.

---

# 🚀 Deployment

The Learnix application is deployed using **Vercel**.

### Frontend

The Next.js frontend is deployed as a Vercel application.

### Backend

The Node.js/Express backend is deployed separately on Vercel.

### Production Architecture

```text
                    Internet
                       │
                       ▼
              ┌─────────────────┐
              │ Learnix Frontend│
              │     Vercel      │
              └────────┬────────┘
                       │
                       ▼
              ┌─────────────────┐
              │ Learnix Backend │
              │     Vercel      │
              └────────┬────────┘
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
    MongoDB Atlas    Redis        Cloudinary
        │
        └──────────────┐
                       ▼
                    Stripe
```

---

# 📱 Responsive Design

The Learnix interface is designed to work across:

* 📱 Mobile devices
* 📱 Tablets
* 💻 Laptops
* 🖥️ Desktop screens

The UI includes responsive layouts for:

* Navigation
* Authentication
* Course pages
* Student dashboard
* Admin dashboard
* Course management
* Analytics
* Payment screens

---

# 🧪 API Testing

The backend APIs can be tested using:

* Postman
* Thunder Client
* REST Client

The main API prefix is:

```text
/api/v1
```

---

# 🛡️ Security Considerations

The application implements:

* Password hashing
* JWT authentication
* Protected API routes
* Role-based authorization
* Secure cookies
* Server-side Stripe payment verification
* Environment-based secrets
* CORS configuration
* Redis-based token/session handling
* Centralized error handling

---

# 📈 Future Improvements

Planned improvements include:

* [ ] Student course progress tracking
* [ ] Course completion certificates
* [ ] Course reviews and ratings
* [ ] Advanced search and filtering
* [ ] Video streaming optimization
* [ ] Improved analytics
* [ ] Automated testing
* [ ] API documentation with Swagger/OpenAPI
* [ ] CI/CD improvements
* [ ] Advanced monitoring and logging
* [ ] Additional learning features

---

# 🎯 Project Goals

Learnix was developed to provide a practical, production-oriented LMS experience while implementing real-world full-stack concepts including:

* Full-stack application architecture
* REST API development
* Authentication and authorization
* Database design
* Cloud storage
* Payment processing
* Real-time communication
* Caching
* Email services
* Admin dashboards
* Analytics
* Production deployment

---

# 👨‍💻 Author

## Muhammad Hassan

Computer Science Student & Full-Stack Developer

**GitHub:**
https://github.com/hassanshahid5218

**LinkedIn:**
https://linkedin.com/in/muhammad-hassan-90866334b/

**LeetCode:**
https://leetcode.com/u/hassanshahid5218/

**Portfolio:**
https://portfolio-five-hazel-91.vercel.app/

---

# ⭐ Show Your Support

If you found this project interesting or useful, consider giving the repository a ⭐ on GitHub.

---

## 📄 License

This project is developed for educational, portfolio, and learning purposes.
