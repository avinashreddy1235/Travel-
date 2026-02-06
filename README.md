# 🌍 AI-Powered Smart Travel Booking Application

A full-stack MERN travel booking platform with an integrated AI Virtual Travel Assistant powered by Google Gemini API. Book trips, hotels, and buses with intelligent recommendations.

![Travel App](client/public/assets/landscape-morning-fog-mountains-with-hot-air-balloons-sunrise.jpg)

## ✨ Features

### 🔐 Authentication & Authorization
- Secure user registration and login with JWT
- Password hashing with bcrypt
- Role-based access control (User/Admin)
- Protected routes

### 🎫 Travel Services
- Browse and search trips, hotels, and buses
- Advanced filtering (type, location, price range)
- Sorting and pagination
- Detailed service pages with amenities
- Service ratings and reviews

### 📅 Booking System
- Complete booking flow with passenger details
- View booking history
- Cancel bookings with refund simulation
- Status tracking (confirmed, pending, cancelled)

### 🤖 AI Virtual Travel Assistant
- Powered by Google Gemini API
- Context-aware responses using database data
- Suggested queries for quick help
- Fallback mechanism for reliability

### 👨‍💼 Admin Dashboard
- Dashboard with statistics (users, bookings, revenue)
- Complete CRUD for travel services
- User management
- Booking management

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Frontend** | React.js 18, React Router v6, Axios, React Icons, React Toastify |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB with Mongoose ODM |
| **Authentication** | JWT (JSON Web Tokens), bcryptjs |
| **AI Integration** | Google Gemini API (@google/generative-ai) |
| **Styling** | Custom CSS with CSS Variables |

## 📁 Project Structure

```
Travel_app/
├── backend/
│   ├── config/          # Database configuration
│   ├── controllers/     # Route controllers
│   ├── middleware/      # Auth & error middleware
│   ├── models/          # Mongoose schemas
│   ├── routes/          # API routes
│   ├── seed.js          # Database seeder
│   └── server.js        # Entry point
│
├── client/
│   ├── public/
│   │   └── assets/      # Images and static files
│   └── src/
│       ├── components/  # React components
│       ├── context/     # Auth context
│       ├── pages/       # Page components
│       ├── services/    # API service
│       └── App.js       # Main app component
│
└── README.md
```

## 🚀 Quick Start

### Prerequisites
- Node.js (v14+)
- MongoDB (local or Atlas)
- Google Gemini API Key

### 1. Clone & Install

```bash
# Clone the repository
git clone <repository-url>
cd Travel_app

# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../client
npm install
```

### 2. Environment Setup

**Backend (.env)**
```env
PORT=5000
MONGODB_URI=mongodb://localhost:27017/travel_app
JWT_SECRET=your-super-secret-jwt-key-here
JWT_EXPIRE=7d
GEMINI_API_KEY=your-gemini-api-key
```

**Frontend (.env)**
```env
REACT_APP_API_URL=http://localhost:5000/api
```

### 3. Seed Database

```bash
cd backend
node seed.js
```

This creates:
- Sample travel services (trips, hotels, buses)
- Admin user (admin@travel.com / admin123)

### 4. Run the Application

**Start Backend (Terminal 1)**
```bash
cd backend
npm run dev
```

**Start Frontend (Terminal 2)**
```bash
cd client
npm start
```

### 5. Access the Application

- **Frontend**: http://localhost:3000
- **Backend API**: http://localhost:5000/api
- **Admin Login**: admin@travel.com / admin123

## 📡 API Endpoints

### Authentication
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/signup` | Register new user |
| POST | `/api/auth/login` | User login |
| GET | `/api/auth/profile` | Get user profile |
| PUT | `/api/auth/profile` | Update profile |

### Travel Services
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/travel` | List all services |
| GET | `/api/travel/:id` | Get service details |
| POST | `/api/travel` | Create service (Admin) |
| PUT | `/api/travel/:id` | Update service (Admin) |
| DELETE | `/api/travel/:id` | Delete service (Admin) |

### Bookings
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/bookings` | Get user bookings |
| GET | `/api/bookings/:id` | Get booking details |
| POST | `/api/bookings` | Create booking |
| PUT | `/api/bookings/:id/cancel` | Cancel booking |

### Reviews
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/reviews/service/:id` | Get service reviews |
| POST | `/api/reviews` | Create review |

### Chatbot
| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/chatbot/chat` | Send message to AI |
| GET | `/api/chatbot/suggestions` | Get suggested queries |

### Admin
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/admin/dashboard` | Get dashboard stats |
| GET | `/api/admin/users` | List all users |
| GET | `/api/bookings/all` | All bookings (Admin) |

## 🎨 Key Components

### Frontend
- **Header**: Navigation with auth state
- **Footer**: Site links and contact info
- **TravelCard**: Service card component
- **Chatbot**: AI assistant interface
- **Loader**: Loading state component

### Pages
- **HomePage**: Hero, search, destinations, packages
- **SearchPage**: Filters, sorting, results
- **TravelDetailPage**: Service details, booking
- **BookingsPage**: User booking history
- **ProfilePage**: User settings
- **AdminDashboard**: Admin panel
- **LoginPage / SignupPage**: Authentication

## 🔐 Security Features

- JWT-based authentication
- Password hashing with bcrypt
- Protected API routes
- Role-based access control
- Input validation with express-validator
- CORS configuration

## 📱 Responsive Design

The application is fully responsive and works on:
- Desktop (1200px+)
- Tablet (768px - 1024px)
- Mobile (< 768px)

## 🤖 AI Assistant Features

The chatbot can help with:
- Finding travel packages
- Hotel recommendations
- Bus route information
- Price comparisons
- Travel tips and suggestions

## 🚀 Deployment

### Backend (Render)
1. Connect GitHub repository
2. Set environment variables
3. Deploy with `npm install && node server.js`

### Frontend (Netlify/Vercel)
1. Connect GitHub repository
2. Set `REACT_APP_API_URL` to deployed backend
3. Build command: `npm run build`
4. Publish directory: `build`

## 📝 License

This project is licensed under the MIT License.

## 👨‍💻 Author

**Avinash** - Tours and Travel Application

---

Made with ❤️ for travel enthusiasts
