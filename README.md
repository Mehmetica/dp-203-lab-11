# dp-203-lab-11

# Use an Apache Spark Notebook in a Pipeline

This project demonstrates how to use an Apache Spark notebook inside an Azure Synapse Analytics pipeline. The goal is to perform data transformation using Spark and automate the process by integrating the notebook into a pipeline.

## 🚀 Lab Overview

You will:

- Provision an Azure Synapse Analytics workspace.
- Run a Spark notebook interactively to transform CSV data into Parquet format.
- Parameterize the notebook.
- Create and run a Synapse pipeline that executes the notebook.
- Verify the transformed data output.
- Optionally clean up resources to avoid costs.

## 🧰 Prerequisites

- An [Azure subscription](https://azure.microsoft.com/free).
- Admin access to the subscription.
- Basic familiarity with Synapse Studio and Spark.

## 🛠️ Setup Instructions

1. Clone the lab files using Azure Cloud Shell (PowerShell):

    ```powershell
    git clone https://github.com/MicrosoftLearning/dp-203-azure-data-engineer dp-203
    cd dp-203/Allfiles/labs/11
    ./setup.ps1
    ```

2. Set a password for the Synapse SQL pool when prompted.

3. Wait for the script to complete (approx. 10 mins).

## 📓 Run Spark Notebook Interactively

- Open Synapse Studio.
- Preview sample CSV files in the `/data` folder in Azure Data Lake.
- Download and import the `Spark Transform.ipynb` notebook.
- Attach it to your Spark pool and run all cells.
- Confirm output is saved as Parquet files in a uniquely named folder.

## ⚙️ Create and Run Pipeline

- Parameterize the `folderName` variable in the notebook.
- Create a pipeline named **Transform Sales Data**.
- Add a **Notebook** activity that:
    - Runs the Spark notebook.
    - Passes `@pipeline().RunId` as the `folderName` parameter.
    - Uses your Spark pool with Small executor size.

- Publish and trigger the pipeline manually.
- Verify that transformed Parquet data is saved in a new folder named with the pipeline run ID.

## 🧪 Verification

- Use Synapse Studio to run a `SELECT TOP 100 ROWS` query on the new Parquet files.
- Confirm that customer name fields have been properly split and transformed.

##SS
![Screenshot 2025-04-14 at 15 56 18](https://github.com/user-attachments/assets/453c13e9-8c02-4838-b9d2-5a92e7115ff9)
![Screenshot 2025-04-14 at 15 55 44](https://github.com/user-attachments/assets/eafee909-84ac-4563-a62c-b64a9abd2bd9)
![Screenshot 2025-04-14 at 15 53 35](https://github.com/user-attachments/assets/296b07ed-23c1-4519-b714-b82398ed416c)
![Screenshot 2025-04-14 at 15 52 32](https://github.com/user-attachments/assets/6b22f07b-7528-47b8-a32f-ed86831949d5)
![Screenshot 2025-04-14 at 15 46 04](https://github.com/user-attachments/assets/15c8b88b-1fdc-499d-9304-173bfb46664b)
![Screenshot 2025-04-14 at 15 45 41](https://github.com/user-attachments/assets/4b0ca8f5-4113-4bc7-af68-a34aa6c1a5a1)
![Screenshot 2025-04-14 at 15 45 18](https://github.com/user-attachments/assets/28fee19c-bcca-4803-8081-9eff323801ea)
![Screenshot 2025-04-14 at 15 43 45](https://github.com/user-attachments/assets/44845169-0419-4be8-a22c-3fb1df73639f)
![Screenshot 2025-04-14 at 15 43 00](https://github.com/user-attachments/assets/9833391d-19f9-45be-889b-339723e4c72f)
![Screenshot 2025-04-14 at 15 37 31](https://github.com/user-attachments/assets/3b3bdec8-cac1-4fe8-8258-bb1948a2a340)
![Screenshot 2025-04-14 at 15 36 38](https://github.com/user-attachments/assets/1cee7fc5-d498-4cfb-b10b-24356cf6a654)



## 🧹 Clean Up

To avoid charges:

- In the Azure Portal, delete the `dp203-xxxxxxx` resource group.

## 📁 Folder Structure

/dp-203-azure-data-engineer/ └── Allfiles/ └── labs/ └── 11/ ├── setup.ps1 └── notebooks/ └── Spark Transform.ipynb


## 📚 Resources

- [Azure Synapse Analytics Documentation](https://learn.microsoft.com/en-us/azure/synapse-analytics/)
- [Apache Spark Documentation](https://spark.apache.org/docs/latest/)
- [Azure Synapse Pipelines](https://learn.microsoft.com/en-us/azure/data-factory/concepts-data-flow-performance-pipelines)

---

© Microsoft Learn | DP-203: Data Engineering on Microsoft Azure
