# 🧠 LangQueryAI — LLM-Powered Text-to-SQL (SQL → NLP / NL2SQL) Engine

## 🌟 Introduction  
Understanding and querying databases can be challenging for non-technical users, so **LangQueryAI** was built to bridge that gap.  
This project uses **Large Language Models (LLMs)** like **Qwen**, **LLaMA**, and **OpenAI GPT** to let users ask questions in plain English and receive accurate SQL queries along with meaningful, easy-to-understand results.  

By combining **LangChain**, **Hugging Face Transformers**, and **Long Chain-of-Thought reasoning**, LangQueryAI transforms natural language into SQL, executes the query on a **MySQL** database, and converts the output back into a clear natural-language explanation.  
This project demonstrates how LLMs can make data access more intuitive, intelligent, and user-friendly.

---

## 🚀 Features

- 🗣 **SQL → NLP (Text-to-SQL / NL2SQL)** natural language query handling  
- 🤖 **LLM integration** with **Qwen**, **LLaMA**, and **OpenAI GPT**  
- 🔗 **LangChain pipelines** with multi-step reasoning  
- 🧠 **Long Chain-of-Thought reasoning** for generating complex SQL queries  
- 🔍 **Schema-aware SQL generation** for accurate query construction  
- 🔐 **SQL safety validation** to prevent destructive commands  
- 💬 Converts SQL outputs into **human-readable explanations**  
- 🗄️ Works seamlessly with the **MySQL Sakila** sample database  

---

## 🧰 Tech Stack

| Category | Tools / Frameworks |
|----------|--------------------|
| **Programming Language** | Python |
| **LLMs / Models** | Qwen, LLaMA, OpenAI GPT |
| **AI Frameworks** | LangChain, Hugging Face Transformers |
| **Database** | MySQL (Sakila) |
| **Libraries** | SQLAlchemy, PyMySQL, python-dotenv |
| **Key Concepts** | LLM Connection, Text-to-SQL (NL2SQL), SQL → NLP, Chain-of-Thought Reasoning |
| **Environment** | Google Colab / Localhost |

---

## ⚙️ How It Works

1. **User Input:** A natural language question is provided.  
2. **Schema Extraction:** Database schema is fetched using SQLAlchemy and sent to the LLM.  
3. **LLM Reasoning:** LangChain + LLM generate a valid SQL query using schema-aware reasoning.  
4. **Safe Execution:** SQL query is validated and executed against the MySQL database.  
5. **Natural Language Output:** The result is explained back in plain English.  

---

## 🧪 Example

### **User Query:**  
> “Show the top 5 customers by total amount spent.”

### **Generated SQL:**  
```sql
SELECT c.customer_id, CONCAT(c.first_name, ' ', c.last_name) AS customer_name, 
       SUM(p.amount) AS total_spent
FROM customer c
JOIN payment p ON c.customer_id = p.customer_id
GROUP BY c.customer_id, customer_name
ORDER BY total_spent DESC
LIMIT 5;
```
### **Natural Language Response:**
 The top 5 customers are listed along with their total spending, ranked from highest to lowest.
---

## 🔧 Setup Instructions

### 1️⃣ Clone the Repository  
```bash
git clone https://github.com/<your-username>/LangQueryAI.git
cd LangQueryAI

2️⃣ Install Dependencies
Make sure you are using Python 3.9+.

pip install -r requirements.txt

3️⃣ Configure Environment Variables
Create a .env file in the project root and add your API keys:

OPENAI_API_KEY=your_openai_key
HUGGINGFACEHUB_API_TOKEN=your_huggingface_key

4️⃣ Set Up the MySQL Database
Download and import the Sakila sample database (if not already installed.
Update your DB connection string inside the notebook or script:

DB_URL = "mysql+pymysql://username:password@host:port/sakila"

5️⃣ Run the Notebook (Google Colab or Local Jupyter)
Open the main notebook and execute the cells in order:

LangQueryAI.ipynb

6️⃣ Test the System
Try a sample natural language query:
answer_user_query("Show the first 10 films by title")
```
You should receive:
-Generated SQL
-SQL execution result
-A natural-language explanation powered by the LLM

## 🧠 Key Concepts Demonstrated

- Natural Language Understanding
- Large Language Models (LLMs)
- Schema-aware SQL generation
- Chain-of-Thought-based reasoning
- Text-to-SQL (SQL → NLP / NL2SQL)
- Data interpretation and summarization
