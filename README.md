# CourseCraft.ai 🎓✈️

CourseCraft.ai is an intelligent, AI-powered **Outcomes-Based Education (OBE)** curriculum and course design platform. It automates the complex, time-consuming process of academic planning, syllabus drafting, course outcomes (CO) generation, and Program Outcomes (PO) mapping.

Designed for educators, university department heads, and instructional designers, CourseCraft.ai transforms curriculum construction from a weeks-long manual drafting exercise into a structured, compliance-ready process completed in minutes.

---

## 🌟 Real-Life Impact & How It Helps

In modern higher education, academic programs must comply with international standards like the **Washington Accord** and national accreditation frameworks (e.g., **NBA, NAAC, and ABET**). Achieving this requires rigorous alignment with **Outcomes-Based Education (OBE)** principles, which is traditionally a heavy administrative burden. 

CourseCraft.ai solves this by:
*   **Empowering Accreditation Compliance:** Instantly maps Course Outcomes (COs) directly to institutional Program Outcomes (POs) with weighted correlation values (0–3 scale), saving departments hundreds of hours of spreadsheet work.
*   **Eliminating Academic Planning Bottlenecks:** Instantly maps full degree plans and credit distributions across multiple semesters, factoring in core courses, electives, and practical laboratory components.
*   **Enforcing Educational Standards:** Uses natural language processing aligned with **Bloom's Taxonomy** action verbs to ensure that course syllabi promote progressive cognitive levels (from basic *Remembering* up to advanced *Creating*).
*   **Accelerating Bootcamps & Workshops:** Generates highly structured, week-by-week learning paths with specific activities, deliverables, and capstone milestones tailored to the learning level.

---

## 🚀 Key Features

*   **AI-Powered Curriculum Designer:** Input your program degree, department, career goals, and credit requirements to receive a structured semester-by-semester course directory.
*   **Comprehensive Syllabus Generator:** Generates custom course descriptions, prerequisites, Bloom's-aligned course objectives, unit-wise topic lists, and practical lab experiments matching standard credit-hour constraints.
*   **Automatic Course Outcomes (CO) Engine:** Synthesizes course outlines to formulate 5 to 6 distinct Course Outcomes, categorizing each by its primary Bloom's Taxonomy cognitive level (L1–L6).
*   **NBA/NAAC Compliant CO-PO Mapping Matrix:** Generates a structured mathematical matrix mapping Course Outcomes to Program Outcomes using weighted logic (Low/Medium/High correlation thresholds).
*   **Weekly Bootcamp Scheduler:** Creates week-by-week progress plans containing specialized topics, hands-on activities, grading deliverables, and comprehensive Capstone project milestones.
*   **Contextual Academic Chatbot:** Features an integrated learning assistant to answer questions about the curriculum, offer recommendations, and adapt syllabi interactively.
*   **Seamless PDF Exports:** Offers direct download capabilities for courses, curriculum frameworks, and mapping matrices in printable, shareable PDF formats.

---

## 🛠️ The Tech Stack: What & Why

CourseCraft.ai utilizes a modern, highly performant stack curated specifically for fast generation speeds, clean rendering, and structured data handling.

| Technology | Role | Why We Selected It |
| :--- | :--- | :--- |
| **LLaMA 3.3 70B (via Groq SDK)** | Core AI Engine | Chosen for its high-level reasoning capabilities and fast tokens-per-second throughput. Utilizing the `groq-sdk` with `llama-3.3-70b-versatile` guarantees quick JSON responses, reducing course generation wait times to seconds. |
| **React 19** | Frontend Framework | Provides a reactive component model with performance optimizations, ensuring smooth rendering of complex, nested curriculum maps, expandable tables, and chat streams. |
| **Vite** | Build Tool & Server | Replaces slower bundlers with near-instant hot module replacement (HMR) and lightning-fast production builds, maximizing frontend developer efficiency. |
| **Tailwind CSS v4** | UI Styling | Utilizes utility-first styling to create a modern, responsive, and responsive dashboard interface with glassmorphic elements and dark-mode aesthetic compatibility. |
| **Node.js & Express.js** | Backend API Layer | Delivers a lightweight, event-driven backend to handle curriculum requests asynchronously, managing incoming LLM tokens and saving outputs to the database. |
| **MongoDB & Mongoose** | Database | A document-oriented database is ideal for storing rich, hierarchically nested JSON structures (e.g., courses containing units, which contain laboratory experiments and mappings) without complex relational joins. |
| **JSON Web Tokens (JWT) & bcrypt** | Security | Ensures secure user login sessions and robust password hashing on the server side to protect user-created curricula. |
| **jsPDF & jsPDF-Autotable** | Document Export | Allows dynamic, client-side generation of structured PDF documents from React state, meaning users can download syllabi offline without server-side print scripts. |

---

## 📁 Repository Structure

```
CourseCraft-AI-main/
├── backend/                   # Node.js + Express backend API
│   ├── src/
│   │   ├── config/            # Environment configurations
│   │   ├── controllers/       # Route controllers (Auth, Chatbot, Syllabus, etc.)
│   │   ├── middleware/        # JWT auth verify and route security
│   │   ├── models/            # Mongoose schemas (User, Course, CO-PO Matrix)
│   │   ├── routes/            # REST API endpoint definitions
│   │   └── services/          # Groq LLaMA integration service
│   └── server.js              # Entrypoint server script
│
├── frontend/                  # React 19 + Vite + Tailwind v4 client
│   ├── public/                # Static public assets
│   └── src/
│       ├── components/        # Reusable UI elements (Sidebar, Loader, Modals)
│       ├── pages/             # Major views (Dashboard, Curriculum, Matrix, Export)
│       ├── context/           # App state providers (Auth, Global context)
│       └── App.jsx            # Routing and core layout
│
└── package.json               # Monorepo command scripts
```

---

## ⚙️ Getting Started

### Prerequisites
*   [Node.js](https://nodejs.org/) (v18 or higher recommended)
*   [MongoDB Atlas](https://www.mongodb.com/cloud/atlas) or a running local MongoDB instance
*   [Groq API Key](https://console.groq.com/)

### Installation

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/veeruveerendra05/CourseCraft.ai.git
    cd CourseCraft.ai
    ```

2.  **Install All Dependencies:**
    This project uses a monorepo setup. You can install all root, backend, and frontend dependencies with a single command:
    ```bash
    npm run install:all
    ```

### Environment Configuration

1.  **Backend Environment:**
    Create a `.env` file inside the `backend` directory:
    ```env
    PORT=5000
    MONGO_URI=your_mongodb_connection_string
    JWT_SECRET=your_jwt_signing_secret
    GROQ_API_KEY=your_groq_api_key
    ```

2.  **Frontend Environment:**
    Create a `.env` file inside the `frontend` directory:
    ```env
    VITE_API_URL=http://localhost:5000
    ```

### Running Locally

You can launch both the frontend and backend servers simultaneously from the root directory:
```bash
npm run dev:all
```
*   **Backend** will run on `http://localhost:5000`
*   **Frontend** will run on `http://localhost:5173](https://coursecraft-ai-brown.vercel.app/`
