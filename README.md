# FinanceAI - Your Autonomous Financial Co-Pilot

A comprehensive financial management application with AI-powered insights, simulations, and personalized recommendations.

## Screenshots

| Login | Profile Selection |
|:---:|:---:|
| ![Login Screen](frontend/docs/pics/pics-01-login-screen-working.png) | ![Profile Selection](frontend/docs/pics/pics-02-profile-selection-screen.png) |

| Dashboard | AI Actions |
|:---:|:---:|
| ![Dashboard](frontend/docs/pics/pics-04-genz-dashboard.png) | ![AI Actions](frontend/docs/pics/pics-03-genz-spending-tracker.png) |

## One-Command Local Demo

> **TL;DR**: Clone, run one command, both services start at `http://localhost:8000` (backend) + auto-selected frontend port.

### macOS/Linux
```bash
chmod +x dev.sh && ./dev.sh
```

### Windows (PowerShell)
```powershell
powershell -ExecutionPolicy Bypass -File .\dev.ps1
```

The scripts will:
- Check Python 3 + Node.js requirements
- Set up Python virtual environment & install backend deps
- Start backend on **`http://localhost:8000`**
- Install frontend deps & find first available port (3000-3003)
- Start frontend with clear URL output
- Run smoke test to verify both services

### Manual Testing Checklist
After services start, quickly verify:
1. **Login Flow**: Click "Continue with FaceID" then select a profile
2. **Navigation**: Test Goals, AI Actions, Simulations tabs
3. **Deep Dive**: Click any "Deep Dive Analysis" button
4. **Simulation**: Start a simulation (Job Loss, Medical Crisis, etc.)
5. **Backend API**: Visit `http://localhost:8000/health` (should return `{"status": "ok"}`)

---

## Architecture

### Frontend (Next.js 14)
- **Framework**: Next.js 14 with App Router
- **Styling**: Tailwind CSS
- **Features**: Responsive design, real-time financial data, AI-powered recommendations, interactive simulations

### Backend (FastAPI)
- **Framework**: FastAPI (Python 3.11)
- **Database**: PostgreSQL
- **Features**: RESTful API, AI/ML integration, financial calculations, data processing

## Key Features

- **Financial Dashboard** - Net worth tracking, asset/liability breakdown, financial health metrics
- **AI-Powered Insights** - Transaction analysis, personalized recommendations, savings opportunities
- **Financial Simulations** - Job loss, medical crisis, market crash, home purchase, emergency fund scenarios
- **Market Data Integration** - Real-time stock prices, market trends, portfolio tracking

## Development Setup

### Prerequisites
- Node.js 18+ and npm
- Python 3.11+

### Manual Setup
```bash
# Clone the repository
git clone <repository-url>
cd FinAI

# Install frontend dependencies
cd frontend
npm install

# Install backend dependencies
cd ../backend/python_engine
pip install -r requirements.txt

# Start development servers
# Frontend (in frontend/ directory)
npm run dev

# Backend (in backend/python_engine/ directory)
uvicorn main:app --reload
```

## API Endpoints

### Core Endpoints
- `GET /health` - Health check
- `GET /profiles` - User profiles
- `POST /simulation/{scenarioType}` - Financial simulations
- `GET /market-data/quotes` - Market data

### AI Endpoints
- `POST /ai/chat` - AI chat interface
- `GET /ai/actions` - AI recommendations
- `POST /ai/analyze` - Transaction analysis

## Environment Variables

### Backend
- `DATABASE_URL` - PostgreSQL connection
- `OPENAI_API_KEY` - OpenAI API access
- `ANTHROPIC_API_KEY` - Anthropic API access
- `FMP_API_KEY` - Financial Modeling Prep API

### Frontend
- `NEXT_PUBLIC_API_URL` - Backend API URL
- `NEXT_PUBLIC_ENVIRONMENT` - Environment

## Documentation

- [Deployment Guide](DEPLOYMENT_GUIDE.md)
- [API Documentation](docs/)
- [Architecture Overview](docs/backend-engineering-spec.md)

## License

This project is licensed under the MIT License.
