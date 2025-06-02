
# Natural Language to SQL Query Generation using Gemini and LangChain

## Project Overview
This project demonstrates how to convert natural language questions into SQL queries using Google's Gemini AI and LangChain. It integrates with Google Cloud SQL to execute queries automatically, providing efficient and intuitive database interactions using natural language.

## Key Features

- Natural Language Processing (NLP): Converts plain English into SQL queries.
- AI Integration: Uses Google's Gemini AI model (gemini-2.0-flash) to generate SQL queries.
- Automated Query Execution: Automatically executes generated queries on Google Cloud SQL.
- Result Rephrasing: Clearly conveys results in readable form.
- Error Handling: Comprehensive diagnostics and SQL query sanitization.

## Technical Stack

- Python 3
- LangChain
- Gemini AI (Google Generative AI)
- Google Cloud SQL
- SQLAlchemy
- PyMySQL

## Setup Instructions

### 1. Clone the Repository
```bash
git clone [my repo](https://github.com/VisvaV/Natural-Language-to-SQL-Query-Generation-with-Gemini)
cd [my repo](Natural-Language-to-SQL-Query-Generation-with-Gemini)
```

### 2. Install Dependencies
```bash
pip install langchain langchain-openai langchain-google-genai sqlalchemy pymysql google-cloud-sql-connector langsmith
```

### 3. Configure Environment Variables

Set these variables:
```bash
export GOOGLE_API_KEY='your_google_api_key'
export LANGSMITH_API_KEY='your_langsmith_api_key'
export LANGCHAIN_ENDPOINT='https://api.smith.langchain.com'
export LANGCHAIN_PROJECT='your_langchain_project_name'
```

### 4. Google Cloud Authentication
Place your Google Cloud credentials JSON file in the project directory and set the path:
```python
os.environ["GOOGLE_APPLICATION_CREDENTIALS"] = "path/to/your/credentials.json"
```

## Database Schema Description
Include your database schema description CSV in the repository root as `database_table_descriptions.csv`. This file helps the model accurately generate queries.

```bash
database_table_descriptions.csv
```

This CSV should describe tables, columns, data types, constraints, and relationships.

## Workflow and Concepts Explained

### LangChain Pipelines
LangChain manages NLP inputs, the Gemini model, and database execution. Workflow steps:
1. Prompt Templating
2. SQL Query Generation by Gemini
3. Query Cleaning
4. Execution on Google Cloud SQL
5. Result Rephrasing

### Prompt Engineering
Detailed schema descriptions and clear task definitions greatly enhance query accuracy.

### Error Handling and Debugging
The project includes detailed error handling:
- KeyError: Ensuring consistent input naming (`input`, `question`, `table_info`).
- SQL Syntax Errors: Handled through SQLAlchemy, ensuring adherence to schema.

## Troubleshooting

Common issues:
- Credential Errors: Verify Google Cloud credentials and paths.
- KeyError Issues: Ensure correct input keys.
- SQL Query Errors: Verify queries against provided schema.

## Use Cases

Applicable for:
- Business Intelligence Automation
- AI-powered Database Interfaces
- Automated Analytics and Reporting
- Quick Data Exploration

## Future Enhancements

- Implement caching mechanisms.
- Support additional SQL dialects and databases.
- Optimize prompt engineering for accuracy.

## Contribution

Contributions welcomed. Submit issues or pull requests via GitHub.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
