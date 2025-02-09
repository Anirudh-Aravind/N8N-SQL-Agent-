# N8N SQL Agent - Online Shop Data Query Generator

A locally-hosted implementation of an AI-powered SQL query generator using N8N and LangChain. This workflow generates SQL queries for an online shop database, using a locally cached schema file for improved performance.

![image](https://github.com/user-attachments/assets/bac195e2-ba67-45d2-9eeb-058306c41f1e)

## 📝 Project Overview

This project is a local implementation of the [N8N SQL Agent Template](https://n8n.io/workflows/2508-generate-sql-queries-from-schema-only-ai-powered/) with MySQL DB connection and different prompt, adapted to work with an online shop database. The workflow uses cached database schema and AI to generate SQL queries for an online shop database system, all running on your local machine.

## 🔒 How It Works

1. **First-Time Setup**: 
   - Workflow scans your MySQL database structure
   - Captures the complete schema
   - Stores it locally as a JSON file

2. **Regular Operation**:
   - Uses the cached schema file for all queries
   - When SQL query is needed:
     - Generates query based on cached schema
     - Executes query against actual database
     - Returns formatted results
   - For non-SQL questions:
     - Provides direct answers using schema knowledge

## 🛠️ Prerequisites

1. Node.js & npm installed
2. MySQL Server running locally
3. N8N account (free)
4. Groq API key (free)
5. Online shop database

## 📥 Setup Guide

### 1. N8N Installation
```bash
npm install n8n -g
n8n
```
Access N8N at `http://localhost:5678`

### 2. Database Setup
1. Download the [Online Shop Dataset from Kaggle](https://www.kaggle.com/datasets/marthadimgba/online-shop-2024?resource=download)
2. Import the data into your local MySQL server
3. Configure MySQL connection in N8N:
   - Host: localhost
   - Database: online_shop
   - Username: your_username
   - Password: your_password

### 3. Groq API Setup
1. Visit [Groq's website](https://groq.com)
2. Sign up for a free account
3. Generate API key from dashboard
4. Add key to N8N workflow

### 4. Workflow Setup
1. Download the workflow JSON file
2. In N8N: Go to Workflows → Import From File
3. Upload the JSON file
4. Configure your credentials:
   - MySQL connection
   - Groq API key
5. Run the initial schema extraction workflow
6. Start using the chat interface!

## 💬 Example Queries

Try these queries specific to the online shop database:
1. "Which product has the highest number of orders?"
2. "List all customers from a specific country"
3. "What are the different product categories?"
4. "Show me the relationship between orders and customers"

## 🏷️ Cost Overview

This implementation is completely free:
- N8N: Free self-hosted version
- MySQL: Free local installation
- Groq: Free tier API access
- Dataset: Free from Kaggle

## 🔍 Technical Details

### Schema Caching Process
1. Initial run captures complete database structure
2. Schema stored as JSON file locally
3. Subsequent queries reference cached schema
4. Actual data queries only execute when needed

### Workflow Components
- Schema Extraction Node
- AI Agent (using Groq)
- Query Processing
- Result Formatting

## 🛟 Troubleshooting

Common issues and solutions:
- Schema file not generating: Check MySQL permissions
- Connection errors: Verify local MySQL setup
- API issues: Confirm Groq API key
- Import errors: Check JSON file format

## 📦 Distribution

Users can:
1. Download the workflow JSON file
2. Import into their N8N instance
3. Configure local connections
4. Start querying their data

## 🙏 Credits

- Original template: [N8N SQL Agent Template](https://n8n.io/workflows/2508-generate-sql-queries-from-schema-only-ai-powered/)
- Dataset: [Kaggle Online Shop Dataset](https://www.kaggle.com/datasets/marthadimgba/online-shop-2024?resource=download)
- N8N Platform: [N8N Website](https://n8n.io/?ps_partner_key=NzkwZTY1NWM2ODEz&ps_xid=P3k1LdZpw3xdyQ&gsxid=P3k1LdZpw3xdyQ&gspk=NzkwZTY1NWM2ODEz)

