# 🚀 Graph-Based Data Modeling & Query System (SAP Order-to-Cash)

## 📌 Overview

This project is a **full-stack data intelligence system** that converts SAP Order-to-Cash data into an **interactive graph + AI-powered query interface**.

It enables users to:

* Visualize business processes as a graph
* Explore relationships between entities
* Ask questions in natural language and get **real data-backed answers (NL → SQL → Result)**

---

## 🎯 Key Features

### 🔹 Graph Visualization

* Interactive node-edge graph using React Flow
* Expand nodes dynamically
* View metadata for each entity
* 590 nodes and 4000+ relationships visualized

---

### 🔹 AI Chat (Groq Powered)

* Natural Language → SQL → Answer pipeline
* Uses **Groq API (llama3-70b-8192)** for fast and free inference
* Displays generated SQL for transparency

---

### 🔹 Guardrails

* Filters out irrelevant queries
* Restricts system to SAP dataset-related questions only

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
Groq LLM (NL → SQL)
↓
SQLite Execution
↓
Results → Groq LLM
↓
Final Answer → UI

---

## 🗄️ Graph Data Model

### Nodes:

* Customer
* SalesOrder
* Product
* Plant
* Delivery
* BillingDocument
* Payment

### Edges:

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

## 💡 Example Queries

* "Which products are associated with the highest number of billing documents?"
* "Trace the full flow of billing document 90504248"
* "Find sales orders that are delivered but not billed"

---

## 🛠️ Setup Instructions

### 1️⃣ Clone the repository

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
GROQ_API_KEY=gsk_your_key_here
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

Frontend runs at:

```
http://localhost:5173
```

---

## 🔐 Environment Variables

| Variable     | Description    |
| ------------ | -------------- |
| PORT         | Backend port   |
| DB_PATH      | SQLite DB path |
| GROQ_API_KEY | Groq API key   |

---

## 🧪 Testing

### ✔ Valid Queries:

* Business insights (billing, orders, payments)
* Relationship tracing

### ❌ Guardrail Examples:

* "Who is Elon Musk?"
* "Write a poem"

---

## 🚀 Deployment

| Service  | Platform |
| -------- | -------- |
| Frontend | Vercel   |
| Backend  | Render   |

---

## 🧠 Design Decisions

### Why Groq?

* Completely free tier
* Extremely fast inference
* Strong performance for SQL generation

### Why SQLite?

* Lightweight and portable
* Ideal for relational SAP data
* Supports complex joins efficiently

### Why Graph Model?

* SAP O2C involves multi-step relationships
* Graph improves understanding of data flow

---

## 📊 Future Improvements

* Graph filtering & clustering
* Analytics dashboard (charts)
* Query caching
* Role-based access

---


---


