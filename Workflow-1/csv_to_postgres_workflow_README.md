# CSV to PostgreSQL Data Import Workflow

This n8n workflow automates the process of importing data from a CSV file into a PostgreSQL database, specifically designed for managing user drug mapping data.

## Workflow Components

1. **Manual Trigger**
   - Initiates the workflow when manually executed

2. **Read From File**
   - Reads data from `/data/shared/user_drug_mappingg.csv`
   - Processes the CSV file containing user drug mapping information

3. **Convert To Spreadsheet**
   - Converts the CSV data into a spreadsheet format for database import
   - Prepares the data for PostgreSQL insertion

4. **PostgreSQL Operations**
   - Creates the `user_drug_mapping` table if it doesn't exist
   - Table schema includes fields for:
     - mapping_id (Primary Key)
     - user_id
     - drug_id
     - brand_name
     - generic_name
     - prescription_date
     - end_date
     - dosage
     - administration_route
     - frequency
     - prescribing_doctor
     - pharmacy_name
     - pharmacy_address
     - refills_remaining
     - special_instructions
     - status
     - side_effects_reported
   - Performs upsert operations using `mapping_id` as the matching column

## Purpose

This workflow is designed to automate the process of importing and updating user drug mapping data from CSV files into a PostgreSQL database. It ensures data consistency by using upsert operations and maintains a structured format for storing medication-related information.

## Usage

1. Place your CSV file at the specified path
2. Execute the workflow manually
3. The workflow will automatically create the table if it doesn't exist and import/update the data

## Note

Ensure that your CSV file structure matches the database schema to avoid data import issues.
