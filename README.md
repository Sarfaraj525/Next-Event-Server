# Next Event Pro Server - Event Planner & Participation System API

A robust, secure, JWT-protected RESTful API backend that powers the Next Event Pro platform, enabling comprehensive event management with integrated payment processing and advanced participant management features.

## 🌐 Live API

**[Visit Next Event Pro](https://next-event-pro.vercel.app/)**

## 📚 Repositories

- **Frontend Repository:** [Next-Event-Client](https://github.com/sumon-ray/Next-Event-Client)
- **Backend Repository:** [Next-Event-Server](https://github.com/sumon-ray/Next-Event-Server)

## 📖 Project Overview

The **Next Event Pro Server** is a comprehensive Node.js/Express.js backend that provides secure APIs for event creation, management, and participation. Built with TypeScript and Prisma ORM, it features sophisticated payment processing, role-based authentication, and scalable architecture patterns.

### 🎯 Core API Capabilities

- **RESTful Architecture** - Clean, standardized API endpoints following REST principles
- **JWT Authentication** - Secure token-based authentication and authorization
- **Payment Processing** - Integrated SSLCommerz payment gateway with invoice generation
- **File Management** - Secure file upload and storage capabilities
- **Email Services** - Automated email notifications and invoice delivery
- **Database Management** - Type-safe operations with Prisma ORM
- **Error Handling** - Comprehensive error management and validation

## 👥 API Access Control

### 🔧 Admin Endpoints
- Monitor all events and user activity through `/api/meta/*`
- Manage users and content moderation via `/api/user/*`
- Access comprehensive analytics and reports
- Override user permissions for system maintenance

### 👤 User Endpoints
- **Authentication**: `/api/auth/*` - Login, register, password management
- **Event Management**: `/api/event/*` - CRUD operations for personal events
- **Participation**: `/api/participant/*` - Join requests and approvals
- **Payments**: `/api/payment/*` - Secure payment processing
- **Invitations**: `/api/invite/*` - Send and manage event invitations
- **Reviews**: `/api/review/*` - Post-event feedback and ratings
- **Profile**: `/api/profile/*` - User profile management

## 💰 Payment Integration Features

### SSLCommerz Integration
- **Secure Transactions** - PCI DSS compliant payment processing
- **Multiple Payment Methods** - Cards, mobile banking, net banking
- **Automatic Invoice Generation** - PDF invoices with event details
- **Payment Verification** - Webhook-based payment confirmation
- **Refund Management** - Automated refund processing

### Payment Workflows
- **Immediate Processing** - Real-time payment validation
- **Status Tracking** - Complete payment lifecycle monitoring
- **Email Notifications** - Automated payment confirmations
- **Invoice Delivery** - Professional PDF invoice generation

## 🏗️ Architecture Overview

### Backend Architecture
- **Modular Design** - Feature-based module organization
- **Service Layer** - Business logic separation from controllers
- **Middleware Stack** - Authentication, validation, and error handling
- **Database Layer** - Prisma ORM with PostgreSQL
- **File Processing** - Secure file upload and management

### Security Implementation
- **JWT Authentication** - Secure token-based sessions
- **Input Validation** - Zod schema validation for all endpoints
- **Error Handling** - Comprehensive error management system
- **Rate Limiting** - API abuse prevention
- **CORS Configuration** - Cross-origin request security

## 📁 Server Project Structure

```
src/
├── app/
│   ├── builders/                 # Query builders and utilities
│   │   └── PrismaQueryBuilder.ts
│   │
│   ├── config/                   # Application configuration
│   │   └── index.ts
│   │
│   ├── errors/                   # Error handling utilities
│   │   ├── AppError.ts
│   │   └── handleZodError.ts
│   │
│   ├── globalTypes/              # Global TypeScript definitions
│   │   ├── error.type.ts
│   │   └── response.type.ts
│   │
│   ├── helpers/                  # Utility functions
│   │   ├── CalculatePagination.ts
│   │   ├── catchAsync.ts
│   │   ├── emailHelper.ts
│   │   ├── fileUploader.ts
│   │   ├── generatePaymentInvoicePDF.ts
│   │   ├── invoiceSender.ts
│   │   ├── jwtHelpers.ts
│   │   ├── RefineQuery.ts
│   │   ├── sendResponse.ts
│   │   └── tokenDecoder.ts
│   │
│   ├── interfaces/               # TypeScript interfaces
│   │   ├── file.ts
│   │   └── pagination.ts
│   │
│   ├── middlewares/              # Express middlewares
│   │   ├── Auth.ts
│   │   ├── globalErrorhandler.ts
│   │   ├── notFound.ts
│   │   └── validateRequest.ts
│   │
│   ├── modules/                  # Feature modules
│   │   ├── auth/                 # Authentication module
│   │   │   ├── auth.constant.ts
│   │   │   ├── auth.controller.ts
│   │   │   ├── auth.interface.ts
│   │   │   ├── auth.route.ts
│   │   │   ├── auth.service.ts
│   │   │   └── emailSender.ts
│   │   │
│   │   ├── event/                # Event management
│   │   │   ├── event.constants.ts
│   │   │   ├── event.controller.ts
│   │   │   ├── event.interface.ts
│   │   │   ├── event.routes.ts
│   │   │   ├── event.service.ts
│   │   │   └── event.validation.ts
│   │   │
│   │   ├── invite/               # Invitation system
│   │   │   ├── invite.controller.ts
│   │   │   ├── invite.interface.ts
│   │   │   ├── invite.route.ts
│   │   │   └── invite.service.ts
│   │   │
│   │   ├── meta/                 # System metadata & analytics
│   │   │   ├── meta.controller.ts
│   │   │   ├── meta.route.ts
│   │   │   ├── meta.service.ts
│   │   │   └── meta.utils.ts
│   │   │
│   │   ├── participant/          # Participant management
│   │   │   ├── participant.constants.ts
│   │   │   ├── participant.controller.ts
│   │   │   ├── participant.inteface.ts
│   │   │   ├── participant.route.ts
│   │   │   └── participant.service.ts
│   │   │
│   │   ├── payment/              # Payment processing
│   │   │   ├── payment.constants.ts
│   │   │   ├── payment.controller.ts
│   │   │   ├── payment.interface.ts
│   │   │   ├── payment.route.ts
│   │   │   ├── payment.service.ts
│   │   │   └── payment.utils.ts
│   │   │
│   │   ├── profile/              # User profile management
│   │   │   ├── profile.constraint.ts
│   │   │   ├── profile.controller.ts
│   │   │   ├── profile.interface.ts
│   │   │   ├── profile.routes.ts
│   │   │   ├── profile.services.ts
│   │   │   └── profile.validation.ts
│   │   │
│   │   ├── review/               # Review system
│   │   │   ├── review.controller.ts
│   │   │   ├── review.interface.ts
│   │   │   ├── review.router.ts
│   │   │   └── review.service.ts
│   │   │
│   │   ├── sslcommerz/           # Payment gateway integration
│   │   │   ├── sslcommerz.controller.ts
│   │   │   ├── sslcommerz.route.ts
│   │   │   └── sslcommerz.service.ts
│   │   │
│   │   └── user/                 # User management
│   │       ├── user.constants.ts
│   │       ├── user.controller.ts
│   │       ├── user.interface.ts
│   │       ├── user.routes.ts
│   │       ├── user.service.ts
│   │       └── user.validation.ts
│   │
│   ├── routes/                   # Route definitions
│   │   └── index.ts
│   │
│   ├── shared/                   # Shared utilities
│   │   └── prisma.ts
│   │
│   ├── templates/                # Email/PDF templates
│   │   └── invoice.template.hbs
│   │
│   └── types/                    # Additional type definitions
│       ├── profile.types.ts
│       └── sslcommerz-lts.d.ts
```

## 🛠️ Technology Stack

### Core Backend Technologies
- **[Node.js](https://nodejs.org/)** - JavaScript runtime environment
- **[Express.js](https://expressjs.com/)** - Fast, unopinionated web framework
- **[TypeScript](https://www.typescriptlang.org/)** - Type safety and enhanced developer experience
- **[Prisma](https://www.prisma.io/)** - Next-generation ORM with type safety
- **[PostgreSQL](https://www.postgresql.org/)** - Advanced relational database

### Authentication & Security
- **[JWT](https://jwt.io/)** - JSON Web Token for secure authentication
- **[bcrypt](https://www.npmjs.com/package/bcrypt)** - Password hashing and security
- **[Zod](https://zod.dev/)** - TypeScript-first schema validation
- **[Helmet](https://helmetjs.github.io/)** - Security middleware for Express

### Payment & Communication
- **[SSLCommerz](https://sslcommerz.com/)** - Secure payment gateway
- **[Nodemailer](https://nodemailer.com/)** - Email sending capabilities
- **[Handlebars](https://handlebarsjs.com/)** - Template engine for emails/invoices
- **[Puppeteer](https://pptr.dev/)** - PDF generation for invoices

### Development & Deployment
- **[Railway](https://railway.app/)/[Render](https://render.com/)** - Backend hosting
- **[Cloudinary](https://cloudinary.com/)** - Image and file management
- **[Cors](https://www.npmjs.com/package/cors)** - Cross-origin resource sharing

## 🚀 API Features

### 🔐 Authentication System
- **User Registration** - Secure account creation with email verification
- **Login/Logout** - JWT-based session management
- **Password Management** - Secure password reset and change functionality
- **Email Verification** - Account activation via email confirmation
- **Role-Based Access** - Admin and user role management

### 🎟️ Event Management APIs
- **CRUD Operations** - Complete event lifecycle management
- **Event Types** - Support for Public/Private and Free/Paid events
- **File Upload** - Event image and document management
- **Search & Filter** - Advanced event discovery capabilities
- **Capacity Management** - Event size limitations and waitlist handling

### 👥 Participant Management
- **Join Requests** - Sophisticated approval workflow APIs
- **Invitation System** - Direct user invitation with payment integration
- **Ban Management** - Host controls for participant management
- **Status Tracking** - Real-time participant status updates

### 💳 Payment Processing
- **SSLCommerz Integration** - Secure payment gateway connection
- **Transaction Management** - Complete payment lifecycle tracking
- **Invoice Generation** - Automated PDF invoice creation
- **Webhook Handling** - Real-time payment status updates
- **Refund Processing** - Automated refund management

### 📊 Analytics & Reporting
- **System Metrics** - Comprehensive application analytics
- **User Statistics** - User engagement and activity tracking
- **Event Analytics** - Event performance and participation data
- **Payment Reports** - Financial transaction reporting

### 🔔 Notification System
- **Email Services** - Automated email notifications
- **Payment Confirmations** - Transaction success/failure notifications
- **Event Updates** - Participant communication system
- **System Alerts** - Administrative notification system

## 📱 API Response Format

All API responses follow a consistent format:

```typescript
{
  success: boolean;
  statusCode: number;
  message: string;
  meta?: {
    page: number;
    limit: number;
    total: number;
  };
  data: any;
}
```

## 🎨 Development Patterns

### Architecture Patterns
- **MVC Pattern** - Model-View-Controller separation
- **Service Layer** - Business logic encapsulation
- **Repository Pattern** - Data access abstraction
- **Middleware Pattern** - Request/response processing pipeline

### Code Quality
- **TypeScript** - Full type safety throughout the application
- **ESLint & Prettier** - Code formatting and linting
- **Error Boundaries** - Comprehensive error handling
- **Input Validation** - Zod schema validation for all inputs

## 📧 Contact Information

- **Email:** [sumonray146371@gmail.com](mailto:sumonray146371@gmail.com)
- **Portfolio:** [https://sumon-ray.vercel.app/](https://sumon-ray.vercel.app/)
- **LinkedIn:** [https://www.linkedin.com/in/sumon60/](https://www.linkedin.com/in/sumon60/)

## 🚀 Getting Started

### Prerequisites
- Node.js 18+
- PostgreSQL database
- SSLCommerz merchant credentials
- Email service credentials (Gmail/SendGrid)

### Installation & Setup

1. Clone the repository
```bash
git clone https://github.com/sumon-ray/Next-Event-Server.git
cd Next-Event-Server
```

2. Install dependencies
```bash
npm install
```

3. Configure environment variables
```bash
cp .env.example .env
```

Add the following environment variables:
```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/nextevent"

# JWT
JWT_SECRET="your-jwt-secret"
JWT_EXPIRES_IN="7d"

# SSLCommerz
STORE_ID="your-store-id"
STORE_PASSWD="your-store-password"
SSL_PAYMENT_API="https://sandbox.sslcommerz.com/gwprocess/v4/api.php"
SSL_VALIDATION_API="https://sandbox.sslcommerz.com/validator/api/validationserverAPI.php"

# Email
EMAIL_USER="your-email@gmail.com"
EMAIL_PASS="your-app-password"

# File Upload
CLOUDINARY_CLOUD_NAME="your-cloudinary-name"
CLOUDINARY_API_KEY="your-cloudinary-key"
CLOUDINARY_API_SECRET="your-cloudinary-secret"

# Frontend URL
CLIENT_URL="http://localhost:3000"
```

4. Setup the database
```bash
npx prisma migrate dev
npx prisma generate
npx prisma db seed
```

5. Start the development server
```bash
npm run dev
```

The server will start on `http://localhost:5000`

## 🧪 API Testing

### Test Credentials
```json
{
  "admin": {
    "email": "admin@nextevent.com",
    "password": "admin123"
  },
  "user": {
    "email": "user@nextevent.com",
    "password": "user123"
  }
}
```

### Available Scripts
```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run format       # Format code with Prettier
npm run migrate      # Run database migrations
npm run generate     # Generate Prisma client
npm run seed         # Seed database with test data
```

## 📈 Performance Optimizations

- **Database Indexing** - Optimized queries with proper indexing
- **Connection Pooling** - Efficient database connection management
- **Caching Strategy** - Redis caching for frequently accessed data
- **Query Optimization** - Prisma query optimization techniques
- **Error Handling** - Comprehensive error management system

## 🔐 Security Implementation

- **JWT Authentication** - Secure token-based authentication
- **Password Hashing** - bcrypt for secure password storage
- **Input Validation** - Zod schema validation for all inputs
- **SQL Injection Prevention** - Prisma ORM protection
- **XSS Protection** - Helmet.js security middleware
- **CORS Configuration** - Proper cross-origin resource sharing
- **Rate Limiting** - API abuse prevention middleware

## 📄 API Documentation

### Core Endpoints

#### Authentication
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `POST /api/auth/forgot-password` - Password reset request
- `POST /api/auth/reset-password` - Password reset confirmation

#### Events
- `GET /api/event` - Get all events (with filters)
- `POST /api/event` - Create new event
- `GET /api/event/:id` - Get event details
- `PUT /api/event/:id` - Update event
- `DELETE /api/event/:id` - Delete event

#### Payments
- `POST /api/payment/init` - Initialize payment
- `POST /api/payment/success` - Payment success callback
- `POST /api/payment/fail` - Payment failure callback
- `GET /api/payment/history` - Payment history

#### Participants
- `POST /api/participant/join` - Join event request
- `PUT /api/participant/approve/:id` - Approve participant
- `DELETE /api/participant/remove/:id` - Remove participant

## 🤝 Contributing

This project demonstrates advanced backend development practices and is available for portfolio review and professional evaluation.

## 📄 License

This project is created for portfolio purposes and professional demonstration.

## 🙏 Acknowledgments

- **Express.js Team** - For the robust web framework
- **Prisma Team** - For the excellent ORM and database toolkit
- **SSLCommerz** - For secure payment processing capabilities
- **Railway/Render** - For reliable backend hosting solutions
- **TypeScript Team** - For enhanced development experience

---

**Created with ❤️ by Sumon Ray**

*This backend demonstrates production-ready API development, secure payment integration, and scalable architecture patterns for modern web applications.*
