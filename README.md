
# CST8917 Lab 1: Building Azure Function Apps with Output Bindings

## Objective

This lab demonstrates how to use output bindings in Azure Functions with Python to interact with Azure Storage Queues and Azure SQL Database. Two function apps were created and deployed to Azure using Visual Studio Code.

We followed these official Microsoft tutorials:

- [Add an Azure Storage Queue output binding to a function in Azure](https://learn.microsoft.com/en-us/azure/azure-functions/functions-add-output-binding-storage-queue-vs-code?pivots=programming-language-python)
- [Add an Azure SQL output binding to a function in Azure](https://learn.microsoft.com/en-us/azure/azure-functions/functions-add-output-binding-azure-sql-vs-code?pivots=programming-language-python)

---

## 🔧 Setup Instructions

### ⚙️ 1. Azure Storage Queue Function

- **Resources Created**:
  - Azure Function App
  - Azure Storage Account with Queue named `myqueue-items`
- **Local Setup**:
  - Python 3.10, Azure Functions Core Tools, VS Code with Azure extensions
  - Created function using VS Code
  - Configured output binding in `function.json` to send message to Storage Queue
- **Testing**:
  - Ran locally with `func start`
  - Confirmed messages were added to queue via Azure Portal

### 🗃️ 2. Azure SQL Output Binding Function

- **Resources Created**:
  - Azure SQL Server
  - SQL Database: `mySampleDatabase`
  - Table: `ToDo`
- **Local Setup**:
  - Used Python and HTTP trigger template
  - Configured output binding to insert records into `dbo.ToDo`
  - Added SQL connection string to `local.settings.json` and Function App Configuration
- **Testing**:
  - Used Postman and VS Code Function Runner
  - Confirmed inserts via Azure Portal Query Editor

---

## ▶️ Run & Test Locally

1. Clone the repo:
```bash
git clone https://github.com/ololadeakin/azurefunction
cd cst8917-lab1
```
2. Set up a Python virtual environment:
```bash
python -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

3. Add a local.settings.json:
```json
{
  "IsEncrypted": false,
  "Values": {
    "AzureWebJobsStorage": "<your-storage-conn-string>",
    "FUNCTIONS_WORKER_RUNTIME": "python",
    "SqlConnectionString": "<your-sql-conn-string>"
  }
}
```
4. Start the function app:
```bash
func start

```
## Demo Video
[Watch the demo on YouTube](https://youtu.be/GzAB3Ki9aRw)
## 💡 What I Learned
How Azure Functions simplify integration with other services using output bindings

How to connect serverless functions to Azure Queue Storage and SQL Database

How to configure and deploy Python-based Azure Functions using Visual Studio Code

How to test and validate serverless applications end-to-end using Azure tools