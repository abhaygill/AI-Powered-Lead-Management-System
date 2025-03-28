# 🚀 AI-Powered Lead Generator & Management System

A full-stack application designed for businesses to efficiently capture, analyze, and manage leads with AI-driven insights.

---

## 📌 Features
- **Multi-step lead capture form** 📝
- **AI-powered lead analysis & scoring** 🤖
- **Admin dashboard for lead management** 📊
- **Email integration for lead follow-up** ✉️
- **PDF export functionality** 📄
- **Modern, responsive UI with dark mode support** 🌙

---

## 🏗 System Architecture

### 🎨 Frontend (FE)
✅ **Tech Stack:** React + TypeScript
✅ **Build Tool:** Vite ⚡
✅ **Styling:** Tailwind CSS + shadcn/ui
✅ **Features:** Component-based architecture, mobile-responsive design

### 🛠 Backend (BE)
✅ **Tech Stack:** Node.js + Express + TypeScript
✅ **Database:** PostgreSQL (via Prisma ORM)
✅ **AI Integration:** OpenAI API 🤯
✅ **Email Services:** SMTP integration

---

## 🔧 Prerequisites
- Node.js (v18 or higher) 🌍
- PostgreSQL 🗄
- OpenAI API key 🔑
- SMTP server credentials 📧

---

## ⚙️ Setup Instructions

### 🖥 Backend Setup
```sh
cd BE
npm install
```

Create a `.env` file and add:
```env
DATABASE_URL="postgresql://user:password@localhost:5432/leadgenerator"
JWT_SECRET="your-secret-key"
OPENAI_API_KEY="your-openai-api-key"
SMTP_HOST="your-smtp-host"
SMTP_PORT=587
SMTP_USER="your-smtp-user"
SMTP_PASS="your-smtp-password"
```

Run database migrations:
```sh
npx prisma migrate dev
```

Start the backend server:
```sh
npm run dev
```

### 🎨 Frontend Setup
```sh
cd FE
npm install
```

Create a `.env` file:
```env
VITE_API_URL="http://localhost:3000"
```

Start the development server:
```sh
npm run dev
```

---

## 📡 API Documentation

### 🔑 Authentication
#### `POST /auth/login`
- **Description:** Login for admin access
- **Body:** `{ email: string, password: string }`
- **Returns:** JWT Token

### 📋 Leads
#### `POST /leads`
- **Description:** Create a new lead
- **Body:** Lead form data
- **Returns:** Created lead object

#### `GET /leads`
- **Description:** Fetch all leads (Admin Only)
- **Query Params:** `page`, `limit`, `search`, `status`
- **Returns:** Paginated leads with total count

#### `GET /leads/:id`
- **Description:** Get lead details by ID (Admin Only)
- **Returns:** Lead object with AI insights

#### `PUT /leads/:id`
- **Description:** Update lead status (Admin Only)
- **Body:** `{ status: string }`
- **Returns:** Updated lead object

#### `DELETE /leads/:id`
- **Description:** Delete a lead (Admin Only)
- **Returns:** Success message

### ✉️ Email
#### `POST /email/send`
- **Description:** Send email using a template
- **Body:** `{ to: string, templateId: string, variables: object }`
- **Returns:** Success message

#### `POST /email/send-custom/:leadId`
- **Description:** Send a custom email to a lead (Admin Only)
- **Body:** `{ subject: string, content: string }`
- **Returns:** Success message

---

## 📂 Project Structure
```
├── BE/                 # Backend directory
│   ├── src/
│   │   ├── routes/    # API routes
│   │   ├── services/  # Business logic
│   │   ├── models/    # Database models
│   │   └── middleware/# Custom middleware
│   └── prisma/        # Database schema
│
└── FE/                 # Frontend directory
    ├── src/
    │   ├── components/# React components
    │   ├── pages/     # Page components
    │   ├── lib/       # Utilities and types
    │   └── hooks/     # Custom hooks
    └── public/        # Static assets
```

---

## 🤝 Contributing
1. **Fork the repository** 🍴
2. **Create a feature branch:** `git checkout -b feature/amazing-feature` 🚀
3. **Commit changes:** `git commit -m 'Add amazing feature'` ✅
4. **Push to branch:** `git push origin feature/amazing-feature` 📤
5. **Open a Pull Request** 🔥

---

## 📜 License
This project is licensed under the **MIT License** 📄 – see the `LICENSE` file for details.
