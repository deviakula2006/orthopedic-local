# Orthopedic Rajahmundry Hospital Management System

A comprehensive, full-stack hospital management application specifically tailored for Orthopedic clinics and hospitals. Built with modern web technologies to handle everything from patient registration and doctor appointments to bed management, billing, and lab investigations.

## 🚀 Tech Stack

### Frontend
- **Framework**: [React 19](https://react.dev/) with [Vite](https://vitejs.dev/)
- **Styling**: [Tailwind CSS 4](https://tailwindcss.com/)
- **Routing**: [React Router](https://reactrouter.com/)
- **Icons**: [Lucide React](https://lucide.dev/)
- **Charts**: [Recharts](https://recharts.org/)
- **PDF Generation**: [jsPDF](https://github.com/parallax/jsPDF) & [jsPDF-AutoTable](https://github.com/simonbengtsson/jsPDF-AutoTable)
- **Forms**: [React Hook Form](https://react-hook-form.com/)
- **Animations**: [Framer Motion](https://www.framer.com/motion/)

### Backend
- **Runtime**: [Node.js](https://nodejs.org/) (v20+)
- **Framework**: [Express.js](https://expressjs.com/)
- **Database**: [PostgreSQL](https://www.postgresql.org/) (hosted on [Supabase](https://supabase.com/))
- **Authentication**: Custom JWT-based auth with [Bcrypt](https://www.npmjs.com/package/bcryptjs)
- **Validation**: [Zod](https://zod.dev/)
- **Logging**: [Pino](https://getpino.io/)
- **Security**: [Helmet](https://helmetjs.github.io/), [Cors](https://expressjs.com/en/resources/middleware/cors.html), Express Rate Limit

## ✨ Key Features

- **🛡️ Role-Based Access Control (RBAC)**: Secure authentication system with separate roles (Admin, Doctor, Receptionist) and restricted views.
- **📊 Interactive Dashboard**: Real-time overview of hospital metrics, including patient counts, daily appointments, bed occupancy, and revenue trends.
- **🧑‍⚕️ Doctor & Patient Management**: Complete profiles, medical history tracking, and doctor availability management.
- **📅 Appointment Scheduling**: Efficient booking system with conflict resolution (prevents double-booking), statuses, and queue management.
- **🩺 Electronic Medical Records (EMR)**: Comprehensive EMR for capturing patient symptoms, vitals, clinical notes, diagnosis, and treatment plans.
- **🛏️ Bed & Ward Management**: Real-time tracking of ward availability, bed occupancy, admissions, and discharges.
- **🧪 Lab Investigations**: Order tracking and result management for laboratory tests and diagnostics.
- **💰 Billing & Invoicing**: Automated invoice generation, payment tracking, itemized bills (OPD, IPD, Lab, Pharmacy), and PDF receipt downloads.
- **📜 Reporting**: Detailed analytics and printable reports for revenue, patient registrations, and investigation trends.
- **🏥 Hospital Settings**: Configurable hospital details for dynamic receipt/invoice branding.

## 📂 Project Structure

```text
orthopedic_rajamundry/
├── .env                  # Frontend environment variables
├── package.json          # Frontend dependencies and scripts
├── index.html            # Vite entry point
├── src/                  # Frontend React application code
│   ├── components/       # Reusable UI components
│   ├── context/          # React Context (Auth, Theme)
│   ├── pages/            # Application views/screens
│   └── services/         # API integration methods
└── server/               # Node.js Express Backend
    ├── .env              # Backend environment variables
    ├── package.json      # Backend dependencies and scripts
    └── src/
        ├── config/       # Database & Env config
        ├── db/           # SQL schemas, migrations, and seed scripts
        ├── middlewares/  # Express middlewares (Auth, Validation, Error Handling)
        ├── modules/      # Feature modules (Controllers, Services, Repositories, Routes)
        └── utils/        # Utility helpers
```

## 🛠️ Local Development Setup

### 1. Prerequisites
- Node.js (v20 or newer)
- PostgreSQL database (or a Supabase project)

### 2. Clone the repository
```bash
git clone https://github.com/deviakula2006/orthopedic_rajamundry.git
cd orthopedic_rajamundry
```

### 3. Setup the Backend
```bash
cd server
npm install
```

Create a `.env` file in the `server` directory using the provided example:
```bash
cp .env.example .env
```
Ensure your `DATABASE_URL` is correctly configured to point to your PostgreSQL instance.

**Run database migrations to initialize the schema:**
```bash
npm run db:migrate
```
*(Optional)* Seed the database with dummy data for testing:
```bash
npm run db:seed
```

**Start the development server:**
```bash
npm run dev
```
The backend will run on `http://localhost:5000`.

### 4. Setup the Frontend
Open a new terminal window and navigate to the project root:
```bash
cd orthopedic_rajamundry
npm install
```

Create a `.env` file in the root directory:
```env
# Uncomment and set this for production deployment
# VITE_API_URL=https://your-production-backend.com/api
```
*(During local development, the frontend proxy setup automatically falls back to `http://localhost:5000`)*

**Start the Vite development server:**
```bash
npm run dev
```
The frontend will run on `http://localhost:5173`.

### 5. Login Credentials
If you seeded the database or ran the production reset script, you can log in as the system admin:
- **Username**: `admin`
- **Password**: `admin@123`

## 🚀 Deployment

The project is configured for easy deployment:

- **Frontend**: Configured for GitHub Pages. Run `npm run deploy` to build and deploy to the `gh-pages` branch. (Ensure `homepage` in `package.json` and `base` in `vite.config.js` are set correctly).
- **Backend**: Contains a `render.yaml` configuration for seamless deployment on [Render](https://render.com/).

## 📄 License

This project is proprietary and confidential. Unauthorized copying, sharing, or distribution of this code is strictly prohibited.
