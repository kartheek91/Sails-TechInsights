# CSV to PostgreSQL Data Import Workflow

![image](https://github.com/user-attachments/assets/1d41c89c-46de-40c3-a8b0-02f76c922a2d)

This n8n workflow automates the process of importing data from a CSV file into a PostgreSQL database, specifically designed for managing user drug mapping data.

## Workflow Components

1. **Manual Trigger**
      
   ![image](https://github.com/user-attachments/assets/0fceb127-a16d-42cd-b1a9-5d045298ffc7)

   - Initiates the workflow when manually executed

3. **Read From File**

   ![image](https://github.com/user-attachments/assets/5651ed55-aab7-4b83-b06f-a461232a9941)

   - Reads data from `/data/shared/<your-csv-file>`
   - Processes the CSV file containing user drug mapping information

5. **Convert To Spreadsheet**

   ![image](https://github.com/user-attachments/assets/f3cc1d48-d318-4c4e-9155-7599a17a159c)

   - Converts the CSV data into a spreadsheet format for database import
   - Prepares the data for PostgreSQL insertion

7. **PostgreSQL Operations**

   ![image](https://github.com/user-attachments/assets/c51a03c3-03a2-437b-a162-8ab488608fff)

   - Creates the table if it doesn't exist
   - Include The Table Schema i.e the columns that have been created when performing `create table` function.
   - Performs upsert operations using `primary_key` as the matching column (Use ID columns for ease of access).

## Purpose

This workflow is designed to automate the process of importing and updating user drug mapping data from CSV files into a PostgreSQL database. It ensures data consistency by using upsert operations and maintains a structured format for storing medication-related information.

## Usage

1. Place your CSV file at the specified path i.e
```sh
/data/shared/<place-your-file-here>
```
2. You can find this path inside the n8n-starter-kit once you have cloned it.

![image](https://github.com/user-attachments/assets/9b7f85dc-680b-490c-b5fc-298452bd0061)

3. Execute the workflow manually
4. The workflow will automatically create the table if it doesn't exist and import/update the data

## Note

Ensure that your CSV file structure matches the database schema to avoid data import issues.
