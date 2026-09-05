<div align="center">

# 🛒 TypeMarket — Full-Stack Marketplace

### *A Modern TypeScript-Powered Marketplace Platform*

![Next.js](https://img.shields.io/badge/Next.js-16-000000?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-5_(strict)-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-9-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-v4-06B6D4?style=for-the-badge&logo=tailwind-css&logoColor=white)

[![Live Demo](https://img.shields.io/badge/Live_Demo-Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://type-script-project-delta.vercel.app)

</div>

---

## 📖 Overview

**TypeMarket** is a production-ready full-stack marketplace application built with Next.js 16 App Router and TypeScript in strict mode. Features public item browsing, search, filtering, pagination, protected listing management, admin analytics dashboard, reviews, and role-based access — all in a beautifully responsive UI.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🔍 **Advanced Search** | Full-text search across title, description, location |
| 🏷️ **Category Filtering** | Electronics, Fashion, Food, Health, Education, Services |
| 💰 **Price Range Filter** | Min/max price filtering |
| 📊 **Sorting Options** | Newest, Oldest, Price (Low→High, High→Low), Rating |
| 📄 **Pagination** | 12 items per page with smooth navigation |
| 🔐 **JWT Auth** | Dual delivery (Header + Cookie) |
| 👤 **User Roles** | User & Admin with different permissions |
| 📈 **Admin Dashboard** | Analytics with Recharts (Bar + Pie charts) |
| ⭐ **Reviews System** | Rate & review items (1 per user per item) |
| 🎨 **Glass Morphism UI** | Modern frosted glass navbar |
| 🔄 **Auto-Seeding** | Demo data on first DB connection |

---

## 🛠️ Tech Stack

### Frontend

| Technology | Purpose |
|------------|---------|
| **Next.js 16** | App Router + Turbopack |
| **React 19** | UI library |
| **TypeScript (strict)** | Complete type safety |
| **Tailwind CSS v4** | Utility-first styling |
| **TanStack Query v5** | Server state management |
| **React Hook Form + Zod** | Forms & validation |
| **Framer Motion** | Smooth animations |
| **Recharts** | Dashboard charts |
| **Lucide React** | Beautiful icons |
| **React Hot Toast** | Notifications |
| **Axios** | HTTP client |

### Backend (API Routes)

| Technology | Purpose |
|------------|---------|
| **Next.js API Routes** | REST API endpoints |
| **MongoDB + Mongoose** | Database & ODM |
| **JWT + bcryptjs** | Auth & password hashing |
| **Helmet** | Security headers |
| **Morgan** | HTTP logging |
| **cookie-parser** | Cookie handling |

---

## 📁 Project Structure

```
TypeScript-Project/
├── src/
│   ├── app/                              # 🗂️ App Router
│   │   ├── api/                          # 🔌 API Routes
│   │   │   ├── auth/
│   │   │   │   ├── login/                # POST /api/auth/login
│   │   │   │   ├── register/             # POST /api/auth/register
│   │   │   │   ├── logout/               # POST /api/auth/logout
│   │   │   │   ├── me/                  # GET  /api/auth/me
│   │   │   │   └── google/              # POST /api/auth/google
│   │   │   ├── items/
│   │   │   │   ├── route.ts              # GET (list), POST (create)
│   │   │   │   ├── [id]/                 # GET/PUT/DELETE /api/items/:id
│   │   │   │   ├── mine/                 # GET /api/items/mine
│   │   │   │   └── dashboard/            # GET /api/items/dashboard
│   │   │   ├── contact/                  # POST /api/contact
│   │   │   └── seed/                     # POST /api/seed
│   │   ├── items/                        # 📦 Item Pages
│   │   │   ├── page.tsx                  # Browse all items
│   │   │   ├── [id]/                     # Item detail
│   │   │   ├── add/                      # Create listing
│   │   │   ├── edit/[id]/               # Edit listing
│   │   │   └── manage/                   # Manage my listings
│   │   ├── dashboard/                    # 📊 Admin Dashboard
│   │   ├── login/                        # 🔐 Login
│   │   ├── register/                     # 📝 Register
│   │   ├── profile/                      # 👤 User Profile
│   │   ├── about/                        # ℹ️ About
│   │   ├── contact/                      # 📧 Contact
│   │   ├── blog/                         # 📰 Blog
│   │   ├── privacy/                      # 🔒 Privacy
│   │   ├── terms/                        # 📋 Terms
│   │   ├── support/                      # 🆘 Support
│   │   └── page.tsx                      # 🏠 Homepage
│   ├── components/                       # 🧩 Reusable Components
│   │   ├── AuthContext.tsx               # Auth provider + useAuth
│   │   ├── Card.tsx                      # Item card
│   │   ├── CardSkeleton.tsx              # Loading skeleton
│   │   ├── ConfirmationModal.tsx         # Delete confirmation
│   │   ├── EmptyState.tsx               # Empty state
│   │   ├── Navbar.tsx                    # Glass morphism nav
│   │   ├── Footer.tsx                    # Site footer
│   │   ├── ProtectedRoute.tsx            # Route guard
│   │   ├── BackToTop.tsx                 # Scroll to top
│   │   └── LoadingSpinner.tsx            # Loading indicators
│   ├── hooks/                            # 🪝 Custom Hooks
│   │   ├── useItems.ts                   # Item CRUD hooks
│   │   ├── useReviews.ts                 # Review hooks
│   │   └── useDebounce.ts               # Debounce hook
│   ├── lib/                              # 🛠️ Utilities
│   │   ├── auth.ts                       # JWT sign/verify
│   │   ├── db.ts                         # MongoDB + auto-seed
│   │   └── models/                       # Mongoose schemas
│   │       ├── Item.ts
│   │       ├── Review.ts
│   │       └── User.ts
│   ├── services/                         # 📡 API Services
│   │   ├── api.ts                        # Axios instance
│   │   ├── authService.ts                # Auth API
│   │   ├── itemService.ts                # Item API
│   │   └── reviewService.ts              # Review API
│   ├── constants/                        # ⚙️ Constants
│   ├── types/                            # 📐 TypeScript Types
│   └── context/                          # 🌐 Providers
├── backend/                              # Standalone backend
├── AGENTS.md                             # Agent rules
├── CLAUDE.md                             # Claude references
└── README.md
```

---

## 🗃️ Database Models

### User
| Field | Type | Details |
|-------|------|---------|
| name | String | required |
| email | String | unique, lowercase |
| password | String | bcrypt hashed (12 rounds), select: false |
| role | String | enum: `user`, `admin` |

### Item
| Field | Type | Details |
|-------|------|---------|
| title | String | required, trim |
| shortDescription | String | maxlength 200 |
| fullDescription | String | required |
| price | Number | min 0 |
| category | String | enum: electronics, fashion, food, health, education, services, other |
| images | [String] | array of URLs |
| rating | Number | 0-5 |
| priority | String | low, medium, high |
| userId | ObjectId | ref: User |

### Review
| Field | Type | Details |
|-------|------|---------|
| itemId | ObjectId | ref: Item |
| userId | ObjectId | ref: User |
| rating | Number | 1-5 |
| comment | String | maxlength 500 |

---

## 📡 API Endpoints

| Method | Endpoint | Auth | Description |
|--------|----------|------|-------------|
| POST | `/api/auth/register` | No | Register |
| POST | `/api/auth/login` | No | Login |
| POST | `/api/auth/logout` | Yes | Logout |
| GET | `/api/auth/me` | Yes | Get profile |
| GET | `/api/items` | No | List (search, filter, sort, paginate) |
| GET | `/api/items/:id` | No | Item detail |
| POST | `/api/items` | Yes | Create item |
| PUT | `/api/items/:id` | Yes | Update (owner only) |
| DELETE | `/api/items/:id` | Yes | Delete (owner only) |
| GET | `/api/items/mine` | Yes | My items |
| GET | `/api/items/dashboard` | Admin | Dashboard stats |
| POST | `/api/seed` | No | Seed database |

### Query Parameters (GET /api/items)
| Param | Description |
|-------|-------------|
| `search` | Full-text search |
| `category` | Filter by category |
| `minPrice` / `maxPrice` | Price range |
| `sort` | newest, oldest, price_asc, price_desc, rating |
| `page` / `limit` | Pagination |

---

## 👥 Role-Based Access

| Feature | User | Admin |
|---------|:----:|:-----:|
| Browse items | ✅ | ✅ |
| Create listings | ✅ | ✅ |
| Edit own listings | ✅ | ✅ |
| Delete own listings | ✅ | ✅ |
| Write reviews | ✅ | ✅ |
| Access dashboard | ❌ | ✅ |
| View all stats | ❌ | ✅ |

---

## 📊 Admin Dashboard

- **Statistics Cards** — Total Items, Users, Reviews, Categories (animated with Framer Motion)
- **Bar Chart** — Items by category
- **Pie Chart** — Category distribution with percentages

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** ≥ 18.0
- **MongoDB Atlas** account

### Installation

```bash
git clone https://github.com/sojibahmedshorif25-ai/TypeScript-Project.git
cd TypeScript-Project
npm install
```

### Environment Variables

```env
MONGODB_URI=mongodb+srv://<user>:<pass>@cluster.mongodb.net/typemarket
JWT_SECRET=your_super_secret_key
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Run Development

```bash
npm run dev
```

### Demo Credentials

| Role | Email | Password |
|------|-------|----------|
| User | user@typemarket.com | password123 |
| Admin | admin@typemarket.com | password123 |

---

## 🌐 Deployment

| Service | Platform | URL |
|---------|----------|-----|
| App | **Vercel** | [type-script-project-delta.vercel.app](https://type-script-project-delta.vercel.app) |
| Database | **MongoDB Atlas** | Cloud |

---

## 👨‍💻 Author

**Sojib Ahmed**

[![GitHub](https://img.shields.io/badge/GitHub-sojibahmedshorif25--ai-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sojibahmedshorif25-ai)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Sojib_Ahmed-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/sojib-ahmed-shorif)

---

<div align="center">

**⭐ Star this repo if you find it impressive!**

</div>
