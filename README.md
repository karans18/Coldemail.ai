# 🚀 AI Cold Email Generator

![MERN](https://img.shields.io/badge/Stack-MERN-green)
![Node](https://img.shields.io/badge/Backend-Node.js-blue)
![React](https://img.shields.io/badge/Frontend-React-61DAFB)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-47A248)
![Groq](https://img.shields.io/badge/AI-Groq%20LLM-orange)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 🌐 Live Demo
👉 https://coldemail-ai-six.vercel.app/

## 📂 GitHub Repository
👉 https://github.com/karans18/Coldemail.ai

---

## 🧠 What the Project Does

**AI Cold Email Generator** is a full-stack MERN web application that transforms minimal user input into high-quality professional outreach content.

Just enter a short prompt (as little as *2–4 words* like **"SDE role at Google"**), and the system uses the **Groq LLM API (LLaMA 3.3-70B)** to instantly generate:

- ✉️ Cold email subject line  
- 📝 Cold email body  
- 💬 LinkedIn DM  
- 🔁 Follow-up email  

This enables users to create **personalized, professional outreach messages instantly** — perfect for job applications, networking, and cold emailing.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 🏗️ Architecture Overview

| Layer        | Technology |
|-------------|-----------|
| **Frontend** | React 18, Vite, Tailwind CSS, React Router |
| **Backend**  | Node.js, Express.js, REST API |
| **Database** | MongoDB (Mongoose ODM) |
| **AI Engine** | Groq API — LLaMA 3.3-70B |
| **Auth**     | JWT, bcrypt, OTP via Nodemailer |
| **DevOps**   | Docker, Docker Compose, GitHub Actions CI/CD |

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 🔐 Authentication Flow

1. User registers → OTP sent via Nodemailer (Gmail)  
2. User verifies 6-digit OTP (expires in 10 mins)  
3. On login → JWT token issued (30-day expiry)  
4. All AI routes protected by custom authentication middleware  
5. Passwords securely hashed using bcrypt (salt rounds: 10)  

--------------------------------------------------------------------------------------------------------------------------------------------------------------------

## 🤖 AI Generation Flow

1. User submits a prompt from the dashboard  
2. Backend validates input (type, length ≤ 2000 chars, non-empty)  
3. A detailed system prompt is constructed with strict output rules  
4. Request sent to Groq API → response parsed as strict JSON  
5. Result stored in MongoDB (`EmailHistory` collection)  
6. Full history retrievable per user, sorted by latest

--------------------------------------------------------------------------------------------------------------------------------------------------------------------
## 🐳 DevOps Setup

- 3 Docker containers — React frontend, Node.js API, and MongoDB — orchestrated using Docker Compose  
- Single `npm run dev` from root starts both frontend (localhost:5173) and backend (localhost:5000) concurrently  
- GitHub Actions CI/CD pipeline triggers on every push to `main` — installs dependencies, runs Vite production build, and detects broken builds early  
    




