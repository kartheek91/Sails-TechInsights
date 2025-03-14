# AI Chat Interface with PostgreSQL Database Workflow

![image](https://github.com/user-attachments/assets/8d3271c6-af80-482a-8eea-1008b4c45d32)

This n8n workflow creates an AI-powered chat interface that can interact with a PostgreSQL database, providing intelligent responses based on the database content.

## Workflow Components

1. **Chat Trigger**

   ![image](https://github.com/user-attachments/assets/d2ad03dd-a765-4bf5-b5ee-4b646e19707c)

   - Initiates the workflow when a chat message is received
   - Serves as the entry point for user interactions

3. **Ollama Chat Model**

   ![image](https://github.com/user-attachments/assets/379f3872-42b1-4a30-a6db-49885b2538b1)

   - Uses the model which we download and run in ollama i.e ```ollama run model```
   - Provides natural language processing capabilities
   - Handles user queries and generates responses

5. **AI Agent**

   ![image](https://github.com/user-attachments/assets/4e97b1b4-569e-4ed1-a1d6-1da31b1d7d2a)
   
   - Coordinates between the chat interface and database operations
   - Manages the conversation flow
   - Processes user inputs and determines appropriate actions

7. **Window Buffer Memory**

   ![image](https://github.com/user-attachments/assets/20ed241e-47b6-401c-b953-a8a43b3fb729)

   - Maintains conversation context
   - Stores recent interaction history
   - Helps in providing contextually relevant responses

9. **Database Tools**

   ![image](https://github.com/user-attachments/assets/5e0239cc-f17c-47bd-a3ad-1b0e06c3e764)

   - Execute SQL Query:
     - Retrieves data from USER_DRUG_MAPPING table
     - Provides access to medication-related information

   - Get DB Schema and Tables List:
     - Retrieves database structure information
     - Lists all available tables and their schemas

## Purpose

This workflow creates an intelligent chat interface that can:
- Answer queries about user drug mappings
- Provide information about the database structure
- Maintain context across conversations
- Execute database queries based on natural language requests

## Usage

1. Start a chat conversation through the provided interface
2. Ask questions about the drug mapping data or database structure
3. The AI agent will process your request and provide relevant information from the database

## Note

The workflow uses database credentials stored securely in n8n. Ensure proper access permissions are configured for the PostgreSQL database.
