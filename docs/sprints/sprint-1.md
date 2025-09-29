# 🔖 Sprint 1 Documentation

## 📅 Sprint Information

- **Period:** 08/09 - 28/09
- **Status:** Done
- **Total Story Points:** 32

## 🎯 Sprint Objectives

Sprint 1 focuses on establishing the foundational components of the Synapse platform, including user authentication, basic report management, and core system infrastructure. This sprint delivers the essential features that enable users to register, authenticate, and begin interacting with the automated reporting system.

## 📋 User Stories

### Authentication Epic

| ID    | User Story                                                                                                        | Story Points | Priority | Status  |
| ----- | ----------------------------------------------------------------------------------------------------------------- | ------------ | -------- | ------- |
| US-01 | As a user, I want to access the registration interface to be able to create my system account simply and quickly. | 3            | High     | Done ✅ |
| US-02 | As a user, I want to register in the system to be able to access the system.                                      | 3            | High     | Done ✅ |
| US-03 | As a user, I want to access the login interface to authenticate my account safely.                                | 2            | High     | Done ✅ |
| US-04 | As a user, I want to authentication in the system to be able to access the main page and use available resources. | 3            | High     | Done ✅ |

### Reports Epic

| ID    | User Story                                                                                                                                                                    | Story Points | Priority | Status  |
| ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------- | ------- |
| US-05 | As a user, I want the system to manage reports following the template defined for the business, ensuring consistency and standardization of information.                      | 8            | High     | Done ✅ |
| US-06 | As a user, I want to receive the reports generated in the email informed in the register to be able to analyze the results and make decisions based on the submitted summary. | 5            | High     | Done ✅ |
| US-07 | As a user, I want to access the tab that contains all reports that the system sent me by email to be able to view the reports again.                                          | 2            | High     | Done ✅ |
| US-08 | As a user, I want to filter reports for a specific time interval to be able to consult the reports more efficiently.                                                          | 3            | High     | Done ✅ |
| US-09 | As a user, I want to filter by the name of the report to be able to consult the desired report more efficiently.                                                              | 3            | High     | Done ✅ |
| US-10 | As a user, I want to filter through the content of the report to be able to consult the desired report more efficiently.                                                      | 3            | High     | Done ✅ |
| US-11 | As a user, I want to view the emails sent in the system if I have not received the email.                                                                                     | 5            | High     | Done ✅ |

## 🏗️ Development Stage

### 📁 Project Structure

The Synapse platform follows a modern full-stack architecture with clear separation between frontend and backend components:

#### Backend Structure (`/backend/`)

```
backend/
├── src/
│   ├── auth/              # Authentication modules
│   ├── database/          # Database models and connections
│   ├── modules/           # Business logic modules
│   ├── routers/           # API route handlers
│   ├── schemas/           # Pydantic schemas for validation
│   ├── templates/         # Email templates
│   └── tests/             # Test suites
├── alembic/               # Database migrations
├── monitoring/            # Grafana & Prometheus setup
├── utils/                 # Utility scripts and sample data
├── docker-compose.yml     # Container orchestration
├── Dockerfile            # Container configuration
└── pyproject.toml        # Python dependencies and config
```

#### Frontend Structure (`/frontend/`)

```
frontend/
├── src/
│   ├── assets/           # Static assets (images, icons)
│   ├── config/           # Configuration files (WebSocket)
│   ├── constants/        # Application constants
│   ├── interfaces/       # TypeScript interfaces
│   ├── pages/            # React page components
│   ├── routes/           # Routing configuration
│   ├── shared/           # Shared components and services
│   └── utils/            # Utility functions
├── public/               # Public assets
└── package.json          # Node.js dependencies
```

### 🛠️ Technology Stack

#### Backend Technologies

- **FastAPI**: High-performance web framework for building APIs
- **PostgreSQL**: Primary database for data persistence
- **Docker**: Containerization for consistent deployment
- **Alembic**: Database migration management
- **Pytest**: Testing framework
- **Prometheus & Grafana**: Monitoring and observability

#### Frontend Technologies

- **React**: Component-based UI library
- **TypeScript**: Type-safe JavaScript development
- **PrimeReact**: UI component library
- **TailwindCSS**: Utility-first CSS framework
- **Vite**: Fast build tool and development server

### 🔧 Development Environment Setup

#### Prerequisites

- Python 3.8+
- Node.js 16+
- Docker & Docker Compose
- PostgreSQL (if running locally)

#### Backend Setup

1. Navigate to backend directory: `cd backend/`
2. Install dependencies: `pip install -r requirements.txt`
3. Set up environment variables
4. Run database migrations: `alembic upgrade head`
5. Start development server: `uvicorn src.main:app --reload`

#### Frontend Setup

1. Navigate to frontend directory: `cd frontend/`
2. Install dependencies: `npm install`
3. Start development server: `npm run dev`

### 🗄️ Database Design

The system uses a relational database structure with the following core entities:

- **Users**: User authentication and profile information
- **Reports**: Generated reports with metadata
- **Email Logs**: Tracking of sent emails
- **Templates**: Report template configurations

### 🔐 Authentication System

#### Features Implemented

- User registration with email validation
- Secure login with JWT tokens
- Password hashing using bcrypt
- Session management
- Protected route middleware

### 📈 Monitoring & Observability

#### Metrics Collection

- Application performance metrics via Prometheus
- Custom business metrics tracking
- Error rate and response time monitoring

#### Dashboards

- Grafana dashboards for system health
- Report generation analytics
- User activity tracking

## ✅ Acceptance Criteria

### Authentication

- [x] Users can register with valid email and password
- [x] Users can login with correct credentials
- [x] Invalid login attempts are properly handled
- [x] JWT tokens are properly generated and validated
- [x] Protected routes require authentication

### Report Management

- [x] System generates reports using predefined templates
- [x] Reports are sent via email to registered users
- [x] Users can view their report history
- [x] Filtering by date range works correctly
- [x] Filtering by report name works correctly

## 🚀 Deployment Configuration

### Development Environment

- Local development with hot reload
- Docker containers for consistent environment
- Database migrations handled automatically

### Production Considerations

- Environment variable configuration
- SSL/HTTPS setup
- Database connection pooling
- Error logging and monitoring
- Backup strategies

## 📝 API Documentation

The API documentation is automatically generated using FastAPI's built-in Swagger UI:

- Development: `http://localhost:8000/docs`
- Interactive API testing available
- Complete endpoint documentation with examples

## 🎨 UI/UX Design

### Design System

- Consistent color palette and typography
- Responsive design for mobile and desktop
- Accessible components following WCAG guidelines
- PrimeReact component library for consistency

### User Interface Components

- Registration and login forms
- Report dashboard with filtering options
- Email status indicators
- Responsive navigation

## 🔄 Development Workflow

### Git Workflow

- Feature branches for each user story
- Conventional commit messages following project standards
- Pull request reviews required
- Automated testing on CI/CD

### Code Quality

- ESLint for JavaScript/TypeScript
- Black and isort for Python formatting
- Type checking with mypy
- Pre-commit hooks for consistency

## 📋 Sprint Deliverables

### Completed Features

- [x] Project structure setup
- [x] Development environment configuration
- [x] Database schema design
- [x] Basic authentication system
- [ ] Report management system (In Progress)
- [ ] Email notification system (In Progress)
- [ ] Frontend components (In Progress)

### Next Steps (Sprint 2)

- Complete report filtering functionality
- Implement NLP chat interface
- Add user administration features
- Enhance UI/UX components
- Performance optimization

## 🐛 Known Issues & Technical Debt

### Current Issues

- Email template styling needs refinement
- Report generation performance optimization needed
- Frontend loading states implementation
- Error handling improvements

### Technical Debt

- Test coverage improvement needed
- API rate limiting implementation
- Database query optimization

## 👥 Team Contributions

- **Wellington Luiz de Faria (PO)**: Requirements definition and acceptance criteria
- **Gabriel de Oliveira Silva Reis (SM)**: Sprint planning and team coordination
- **Development Team**: Feature implementation and testing
  - Iago Cardoso Souza
  - João Vitor dos Santos Pereira
  - Ryan Verissimo de Araujo

---

**Last Updated:** 28/09/2025  
**Next Review:** Sprint 1 Retrospective
