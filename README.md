# Smart Healthcare System

A full-stack web application for managing hospital operations — appointments, patient records, prescriptions, payments, and staff scheduling — with role-based dashboards for Admins, Doctors, Nurses, and Patients.

---

## Features

- **Role-Based Access Control** — Separate dashboards and permissions for Admin, Doctor, Nurse, and Patient roles
- **Appointment Management** — Book, view, update, and cancel appointments with real-time availability
- **Doctor Scheduling** — Weekly time-slot management with availability tracking
- **Patient Diagnosis & Prescriptions** — Create diagnoses, manage prescriptions, generate QR codes for sharing
- **Payment Processing** — Stripe credit card payments and bank deposit/transfer support
- **Insurance Management** — Create and manage patient insurance policies with coverage tracking
- **PDF Generation** — Export prescriptions and medical reports as PDF documents
- **Staff Management** — CRUD operations for hospital staff with qualifications and work experience
- **Patient Profiles** — Detailed patient records with medical history

---

## Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| React 18 + TypeScript | UI framework |
| Vite | Build tool |
| React Router DOM v6 | Client-side routing |
| React Bootstrap 5 | UI components |
| Formik + Yup | Form handling and validation |
| Axios | HTTP client |
| Chart.js | Data visualization |
| Stripe.js + PayPal SDK | Payment integrations |
| jsPDF | PDF generation |
| react-qr-code | QR code generation |
| react-toastify | Toast notifications |

### Backend
| Technology | Purpose |
|---|---|
| Node.js + Express.js | Server framework |
| TypeScript | Type safety |
| MongoDB + Mongoose | Database |
| JWT | Authentication |
| bcrypt | Password hashing |
| Stripe SDK | Payment processing |
| Multer | File uploads |
| Helmet + CORS | Security middleware |
| express-validator | Input validation |

---

## Prerequisites

- Node.js v18+
- MongoDB (local or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))
- A [Stripe](https://stripe.com/) account (for payment features)

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/Smart-Healthcare-System.git
cd Smart-Healthcare-System
```

### 2. Set up the Backend

```bash
cd Hospital-Backend
npm install
```

Create a `.env` file in `Hospital-Backend/`:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
STRIPE_SECRET_KEY=your_stripe_secret_key
```

Create a `src/config/config.env` file:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
```

Start the backend:

```bash
npm run dev
```

### 3. Set up the Frontend

```bash
cd ../Hospital-Frontend
npm install
```

Create a `.env` file in `Hospital-Frontend/`:

```env
VITE_BACKEND_URL=http://localhost:5000
```

Start the frontend:

```bash
npm run dev
```

The app will be available at `http://localhost:5173`.

---

## Project Structure

```
Smart-Healthcare-System/
├── Hospital-Backend/
│   └── src/
│       ├── config/         # Database configuration
│       ├── controllers/    # Route controllers
│       ├── models/         # Mongoose models
│       ├── routes/         # API routes
│       ├── services/       # Business logic
│       ├── repository/     # Data access layer
│       ├── interfaces/     # TypeScript interfaces
│       └── middlewares/    # Auth and validation middleware
│
└── Hospital-Frontend/
    └── src/
        ├── pages/          # Role-based page components
        ├── components/     # Shared UI components
        ├── services/       # API service calls
        ├── context/        # React Context (auth state)
        └── utils/          # Helper utilities
```

---

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/v1/auth/register` | Register a new user |
| POST | `/api/v1/auth/login` | Login |
| GET/POST/PUT/DELETE | `/api/v1/staff` | Staff management |
| GET/POST/PUT/DELETE | `/api/v1/appointments` | Appointment management |
| GET/POST/PUT/DELETE | `/api/v1/patient-diagnosis` | Diagnosis and prescriptions |
| GET/POST | `/api/v1/payment` | Payments |
| POST | `/api/v1/create-payment-intent` | Stripe payment intent |
| POST | `/api/v1/submit-bank-deposit` | Bank deposit submission |
| GET/POST/PUT/DELETE | `/api/insurance` | Insurance management |
| GET/PUT | `/api/v1/profile` | User profiles |
| GET/POST/PUT/DELETE | `/api/v1/staff-details` | Staff qualifications |

---

## User Roles

| Role | Capabilities |
|---|---|
| **Admin** | Full access — manage staff, view all patients, manage insurance, view payments |
| **Doctor** | Manage own schedule, view assigned appointments, create diagnoses and prescriptions |
| **Nurse** | View patient records and appointments |
| **Patient** | Book appointments, view own records, make payments, view prescriptions |

---

## Environment Variables Reference

### Backend (`Hospital-Backend/.env`)

| Variable | Description |
|---|---|
| `PORT` | Server port (default: 5000) |
| `MONGO_URI` | MongoDB connection string |
| `JWT_SECRET` | Secret key for signing JWTs |
| `STRIPE_SECRET_KEY` | Stripe secret API key |

### Frontend (`Hospital-Frontend/.env`)

| Variable | Description |
|---|---|
| `VITE_BACKEND_URL` | Backend API base URL |


