# Home Service Full-Stack Application

A complete full-stack home service platform built with React, Node.js, PostgreSQL, and Prisma.

## 🚀 Features

- **Customer App**: Book services, track jobs, manage profile
- **Worker App**: Accept jobs, manage earnings, build profile  
- **Admin Panel**: Manage users, services, bookings, and complaints
- **Real-time Authentication**: JWT-based auth system
- **Database**: PostgreSQL with Prisma ORM
- **Responsive Design**: Mobile-first approach

## 🛠️ Tech Stack

### Frontend
- React 19 with Vite
- React Router DOM
- Tailwind CSS
- Framer Motion
- Axios for API calls
- React Hot Toast

### Backend
- Node.js with Express
- PostgreSQL database
- Prisma ORM
- JWT authentication
- bcryptjs for password hashing
- CORS enabled

## 📋 Prerequisites

Before running this project, make sure you have:

- Node.js (v18 or higher)
- PostgreSQL (v12 or higher)
- npm or yarn package manager

## 🔧 Installation & Setup

### 1. Clone the repository
```bash
git clone <your-repo-url>
cd "home service"
```

### 2. Backend Setup

```bash
cd backend

# Install dependencies
npm install

# Setup environment variables
# Edit .env file with your database credentials:
# DATABASE_URL="postgresql://username:password@localhost:5432/homeservice?schema=public"
# JWT_SECRET="your-super-secret-jwt-key-here"
# PORT=5000

# Generate Prisma client
npm run db:generate

# Push database schema
npm run db:push

# Seed database with sample data
node prisma/seed.js

# Start backend server
npm run dev
```

### 3. Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Start frontend development server
npm run dev
```

## 🗄️ Database Setup

1. Create a PostgreSQL database named `homeservice`
2. Update the `DATABASE_URL` in `backend/.env` with your credentials
3. Run the Prisma commands to set up the schema:

```bash
cd backend
npm run db:generate
npm run db:push
node prisma/seed.js
```

## 🚀 Running the Application

### Development Mode

1. **Start Backend** (Terminal 1):
```bash
cd backend
npm run dev
```
Backend will run on `http://localhost:5000`

2. **Start Frontend** (Terminal 2):
```bash
cd frontend
npm run dev
```
Frontend will run on `http://localhost:5173`

3. **Open Prisma Studio** (Optional - Terminal 3):
```bash
cd backend
npm run db:studio
```
Prisma Studio will open on `http://localhost:5555`

## 👥 Default Users

After seeding the database, you can login with:

### Admin
- Email: `admin@homeservice.com`
- Password: `admin123`

### Customer
- Email: `customer@example.com`
- Password: `customer123`

### Worker
- Email: `worker@example.com`
- Password: `worker123`

## 📱 Application Routes

### Customer Routes
- `/customer` - Home page
- `/customer/login` - Customer login
- `/customer/bookings` - View bookings
- `/customer/profile` - User profile

### Worker Routes
- `/worker` - Worker dashboard
- `/worker/login` - Worker login
- `/worker/jobs` - Job management
- `/worker/earnings` - Earnings tracking

### Admin Routes
- `/admin` - Admin dashboard
- `/admin/login` - Admin login
- `/admin/workers` - Worker management
- `/admin/services` - Service management

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/login` - User login
- `POST /api/auth/register` - User registration

### Services
- `GET /api/services` - Get all services
- `POST /api/services` - Create service (Admin)

### Bookings
- `POST /api/bookings` - Create booking
- `GET /api/bookings/my` - Get user bookings

### Workers
- `GET /api/workers` - Get all workers
- `GET /api/workers/:id` - Get worker details

## 🏗️ Project Structure

```
home service/
├── backend/
│   ├── prisma/
│   │   ├── schema.prisma
│   │   └── seed.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── bookings.js
│   │   ├── services.js
│   │   ├── users.js
│   │   └── workers.js
│   ├── middleware/
│   │   └── auth.js
│   ├── server.js
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── context/
│   │   ├── lib/
│   │   ├── pages/
│   │   └── App.jsx
│   └── package.json
└── README.md
```

## 🔒 Environment Variables

### Backend (.env)
```
DATABASE_URL="postgresql://username:password@localhost:5432/homeservice?schema=public"
JWT_SECRET="your-super-secret-jwt-key-here"
PORT=5000
NODE_ENV=development
```

## 🚀 Deployment

### Backend Deployment
1. Set up PostgreSQL database on your hosting platform
2. Update environment variables
3. Run database migrations
4. Deploy to platforms like Heroku, Railway, or DigitalOcean

### Frontend Deployment
1. Build the project: `npm run build`
2. Deploy to platforms like Netlify, Vercel, or AWS S3

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

If you encounter any issues:
1. Check the console for error messages
2. Ensure PostgreSQL is running
3. Verify environment variables are set correctly
4. Make sure both frontend and backend servers are running

For additional help, please create an issue in the repository.