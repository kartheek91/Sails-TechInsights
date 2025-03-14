# AI Chat Interface with PostgreSQL Database Workflow

This n8n workflow creates an AI-powered chat interface that can interact with a PostgreSQL database, providing intelligent responses based on the database content.

## Workflow Components

1. **Chat Trigger**
   - Initiates the workflow when a chat message is received
   - Serves as the entry point for user interactions

2. **Ollama Chat Model**
   - Uses the Qwen 2.5 (0.5B parameters) model
   - Provides natural language processing capabilities
   - Handles user queries and generates responses

3. **AI Agent**
   - Coordinates between the chat interface and database operations
   - Manages the conversation flow
   - Processes user inputs and determines appropriate actions

4. **Window Buffer Memory**
   - Maintains conversation context
   - Stores recent interaction history
   - Helps in providing contextually relevant responses

5. **Database Tools**
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
