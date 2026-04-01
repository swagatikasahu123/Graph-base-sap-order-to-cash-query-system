# 🚀 Graph-Based SAP Order-to-Cash Query System

## 📌 Overview

This project is a **full-stack data intelligence system** that transforms SAP Order-to-Cash (O2C) data into an **interactive graph visualization + AI-powered query interface**.

It allows users to:

* Visualize complex business relationships as a graph
* Explore entities like customers, orders, deliveries, invoices, and payments
* Ask natural language questions and receive **accurate, data-backed answers (NL → SQL → Result)**

---

## Deployment
🌐 Live Demo: https://fde-project.vercel.app
🔗 Backend API: https://fde-project.onrender.com

## 📸 Screenshots

<img width="1366" height="730" alt="image" src="https://github.com/user-attachments/assets/0e08ef92-15cb-4d1f-84ac-f8e93d11a0ef" />
<img width="1366" height="686" alt="image" src="https://github.com/user-attachments/assets/db2f6af2-d5e3-42e0-b451-86be5e5adc15" />


---

## 🧩 Architecture Diagram

```
User (Frontend - React)
        ↓
Graph UI + Chat Panel
        ↓
Backend (Node.js + Express)
        ↓
Groq LLM (NL → SQL → Answer)
        ↓
SQLite Database
```

---

## 🎯 Key Features

### 🔹 Interactive Graph Visualization

* 590+ nodes and 4000+ edges
* Expandable nodes (double-click)
* Node metadata inspection panel
* Built using React Flow

---

### 🔹 AI-Powered Query System (Groq)

* Natural Language → SQL → Answer pipeline
* Uses **Groq API (llama3-70b-8192)**
* Displays generated SQL queries

---

### 🔹 Guardrails

* Rejects off-topic queries
* Ensures answers are grounded in SAP dataset

---

## 🧠 Architecture

### 🔹 Tech Stack

| Layer    | Technology               |
| -------- | ------------------------ |
| Frontend | React (Vite), React Flow |
| Backend  | Node.js, Express         |
| Database | SQLite (better-sqlite3)  |
| LLM      | Groq API (Llama3-70B)    |

---

### 🔹 System Flow

User Query
↓
Frontend (React UI)
↓
Backend `/api/chat`
↓
Groq LLM (NL → SQL generation)
↓
SQLite executes query
↓
Results sent back to LLM
↓
Final grounded answer returned

---

## 🗄️ Graph Data Model

### Nodes

* Customer
* SalesOrder
* Product
* Plant
* Delivery
* BillingDocument
* Payment

### Edges

* PLACES
* CONTAINS
* FULFILLED_BY
* SHIPS_FROM
* STORED_AT
* INVOICED_AS
* CLEARED_BY
* PAYS
* CANCELLED

---

## 🧠 LLM Prompting Strategy

The system uses a **3-step pipeline**:

### 1. Guardrail Classification

* Classifies query as SAP-related or off-topic
* Rejects irrelevant queries

### 2. SQL Generation

* Injects database schema + relationships
* Generates **safe SQLite SELECT queries only**

### 3. Answer Generation

* Executes SQL on real data
* Produces grounded natural language responses

---

## 🛡️ Guardrails

### ❌ Blocked Queries

* General knowledge ("Who is Elon Musk?")
* Creative writing ("Write a poem")

### ✅ Allowed Queries

* Business insights
* Data analysis
* Relationship tracing

---

## 💡 Example Queries

* Which products are associated with the highest number of billing documents?
* Trace the full flow of billing document 90504248
* Find sales orders that are delivered but not billed

---

## 🛠️ Setup Instructions

### 1️⃣ Clone Repository

```bash
git clone https://github.com/swagatikasahu123/Graph-base-sap-order-to-cash-query-system.git
cd Graph-base-sap-order-to-cash-query-system
```

---

### 2️⃣ Backend Setup

```bash
cd backend
npm install
```

Create `.env` file:

```env
PORT=4000
DB_PATH=./sap_o2c.db
CORS_ORIGINS=http://localhost:3000,http://localhost:5173
GROQ_API_KEY=your_api_key_here
```

Run backend:

```bash
node server.js
```

---

### 3️⃣ Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Open:

```
http://localhost:5173
```

---

## 🔐 Environment Variables

| Variable     | Description  |
| ------------ | ------------ |
| PORT         | Backend port |
| DB_PATH      | SQLite DB    |
| GROQ_API_KEY | Groq API key |

---

## 🧪 Testing

### ✅ Valid Queries

* Billing insights
* Order flow tracking

### ❌ Guardrail Testing

* Who is Elon Musk?
* Write a poem

---

## 🚀 Deployment

| Service  | Platform |
| -------- | -------- |
| Frontend | Vercel   |
| Backend  | Render   |

---

## 🧠 Design Decisions

### Why Groq?

* Free tier
* Fast inference
* Strong SQL generation

### Why SQLite?

* Lightweight
* Ideal for structured SAP data
* Efficient joins

### Why Graph Model?

* SAP O2C has complex relationships
* Graph improves understanding

---

## 📊 Future Improvements

* Graph filtering
* Analytics dashboard
* Query caching
* Role-based access

---



---


