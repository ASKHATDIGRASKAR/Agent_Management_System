# 🚀 Agent Management System

A full-stack **MERN application** for managing agents and distributing contact lists efficiently.  
Built with **React, Node.js, Express, and MongoDB**, styled with **TailwindCSS**, and powered by **Vite** for fast development.

---

## ✨ Features

### 🔑 Authentication
- Secure **admin login** with JWT tokens  
- Email + password validation  
- Session management  

### 👥 Agent Management
- Add agents (name, email, mobile number with country code, password)  
- View all agents in an organized table  
- Edit or delete agents  
- Track assigned contact counts  

### 📂 CSV Upload & Distribution
- Upload **CSV/XLSX/XLS** files containing contacts  
- Automatic validation of uploaded files  
- Equal distribution of contacts across all agents  
- Preview distribution before confirmation  
- Handle remainder contacts sequentially  

### 📊 Dashboard
- Overview statistics of agents & contacts  
- Quick insights into system performance  

---

## 🛠️ Tech Stack

- **Frontend:** React + Vite + TypeScript + TailwindCSS  
- **Backend:** Node.js + Express.js  
- **Database:** MongoDB (with Mongoose/Drizzle ORM)  
- **Auth:** JWT-based authentication  
- **Build Tooling:** Vite + PostCSS  

---

## 🚀 Getting Started

### 1️⃣ Clone the repository
```bash
git clone https://github.com/your-username/DataSpeakAI.git
cd DataSpeakAI
```

### 2️⃣ Install dependencies
```bash
npm install
```

### 3️⃣ Setup environment
Create a `.env` file in the root directory and add your configuration (e.g., MongoDB URI, JWT secret). Example:
```env
MONGO_URI=mongodb://localhost:27017/agentdb
JWT_SECRET=your_secret_key
PORT=5000
```

### 4️⃣ Run the development server
```bash
npm run dev
```

The app will be running at **http://localhost:5173/**.

---

## 📦 Scripts

- `npm run dev` → Start development server  
- `npm run build` → Build for production  
- `npm run preview` → Preview production build  
- `npm run lint` → Lint project files  

---

## 📂 Project Structure
```
DataSpeakAI/
├── src/                 # Source code
│   ├── components/      # Reusable UI components
│   ├── pages/           # Application pages
│   ├── services/        # API & business logic
│   ├── utils/           # Helpers & utilities
│   └── assets/          # Static assets
├── public/              # Public files
├── package.json         # Dependencies & scripts
└── README.md            # Project docs
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!  
Feel free to fork the repo and submit a pull request.

---

## 📜 License

This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.
