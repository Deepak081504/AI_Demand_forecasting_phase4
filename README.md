# Advanced AI Demand Forecasting — Phase 4

Enterprise AI-powered Demand Forecasting Platform with Phase 4 intelligent automation, enterprise integrations, advanced AI features, and enhanced user management.

---

##  Quick Start

### Backend Setup (FastAPI + MySQL)

```bash
cd backend

# 1. Create virtual environment
python -m venv venv
source venv/bin/activate        # Linux/Mac
# or: venv\Scripts\activate     # Windows

# 2. Install dependencies
pip install -r requirements.txt

# 3. Configure database
# Edit app/core/config.py:
#   MYSQL_USER, MYSQL_PASSWORD, MYSQL_DB

# 4. Create the MySQL database
mysql -u root -p -e "CREATE DATABASE IF NOT EXISTS demand_forecasting;"

# 5. Start server (auto-creates tables on first run)
uvicorn app.main:app --reload --port 8000
```

---

### Frontend Setup (React + Vite)

```bash
cd frontend

# 1. Install dependencies
npm install

# 2. Start dev server
npm run dev
```

Frontend runs at: http://localhost:5174

---

##  Phase 4 New Modules

| Module | Route | Description |
|--------|-------|-------------|
| Smart Automation | `/automation` | Forecast schedules, recurring runs, alert configs |
| Enterprise Integrations | `/integrations` | ERP (SAP, Oracle), inventory APIs, webhooks |
| AI Features | `/ai-features` | Recommendations, demand spikes, buying behavior, optimization |
| Model Comparison | `/forecast-comparison` | Multi-model dashboard, accuracy trends, business insights |
| User Management | `/user-management` | Profiles, activity tracking, account status, password reset |

---

##  All Routes

| Page | Route |
|------|-------|
| Login | `/` |
| Dashboard | `/dashboard` |
| Upload Dataset | `/upload` |
| Forecast | `/forecast` |
| Forecast History | `/forecast/history` |
| **Model Comparison** | `/forecast-comparison` |
| Reports | `/reports` |
| Advanced Analytics | `/analytics` |
| **AI Features** | `/ai-features` |
| Real-Time Monitor | `/realtime` |
| Notifications | `/notifications` |
| Settings | `/settings` |
| Admin Dashboard | `/admin` |
| **User Management** | `/user-management` |
| Role Management | `/roles` |
| **Smart Automation** | `/automation` |
| **Enterprise Integrations** | `/integrations` |
| System Monitor | `/system` |
| ML Ops | `/mlops` |

---

##  Default Login

```
Email: admin@example.com
Password: admin123
```

---

##  Architecture

```
project/
├── backend/
│   ├── app/
│   │   ├── api/v1/endpoints/     # REST API endpoints
│   │   │   ├── automation.py        ← Phase 4 NEW
│   │   │   ├── integrations.py      ← Phase 4 NEW
│   │   │   ├── ai_features.py       ← Phase 4 NEW
│   │   │   ├── forecast_comparison.py ← Phase 4 NEW
│   │   │   ├── user_management.py   ← Phase 4 NEW
│   │   │   ├── auth.py, forecasting.py, analytics.py ...
│   │   ├── core/                 # DB, config, security
│   │   ├── models/               # SQLAlchemy models
│   │   ├── ml/                   # ML predict, train, metrics
│   │   └── main.py               # FastAPI app (v4.0)
│   └── requirements.txt
└── frontend/
    ├── src/
    │   ├── pages/
    │   │   ├── SmartAutomation.jsx      ← Phase 4 NEW
    │   │   ├── EnterpriseIntegrations.jsx ← Phase 4 NEW
    │   │   ├── AIFeatures.jsx           ← Phase 4 NEW
    │   │   ├── ForecastComparison.jsx   ← Phase 4 NEW
    │   │   ├── UserManagement.jsx       ← Phase 4 NEW
    │   │   ├── Dashboard.jsx       ← Enhanced (widgets, drill-down, export)
    │   │   ├── Notifications.jsx   ← Enhanced (email, thresholds)
    │   │   ├── Settings.jsx        ← Enhanced (security, audit log)
    │   │   └── ...existing pages
    │   ├── components/layout/Sidebar.jsx  ← Updated with new nav items
    │   ├── App.jsx                        ← Updated with new routes
    │   └── context/, api/, routes/
    └── package.json
```

---

##  Phase 4 API Endpoints

### Smart Automation
- `GET /automation/schedules` — List all schedules
- `POST /automation/schedules` — Create schedule
- `PUT /automation/schedules/{id}/toggle` — Enable/disable
- `POST /automation/schedules/{id}/run` — Manual trigger
- `GET /automation/alerts` — Alert configurations
- `POST /automation/alerts` — Create alert config
- `GET /automation/workflow-runs` — Execution history

### Enterprise Integrations
- `GET /integrations/` — List integrations
- `POST /integrations/` — Add integration
- `PUT /integrations/{id}/sync` — Trigger sync
- `GET /integrations/webhooks` — Webhook endpoints

### AI Features
- `GET /ai-features/recommendations` — Product recommendations
- `GET /ai-features/buying-behavior` — Customer segments
- `GET /ai-features/demand-spikes` — Spike predictions
- `GET /ai-features/low-stock-predictions` — Stockout forecast
- `GET /ai-features/inventory-optimization` — AI suggestions

### Forecast Comparison
- `GET /forecast-comparison/models` — Compare all models
- `GET /forecast-comparison/accuracy-trends` — Trends over time
- `GET /forecast-comparison/confidence-scores` — Confidence intervals
- `GET /forecast-comparison/recommendations` — Business recommendations

### User Management
- `GET /user-management/users` — All users (with filters)
- `PUT /user-management/users/{id}` — Update user
- `PUT /user-management/users/{id}/toggle-status` — Suspend/activate
- `POST /user-management/users/{id}/reset-password` — Reset password
- `GET /user-management/activity` — Activity log
