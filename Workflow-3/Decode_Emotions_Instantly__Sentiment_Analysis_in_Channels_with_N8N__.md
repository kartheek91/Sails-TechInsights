# Teams Sentiment Analysis Workflow

This n8n workflow automates sentiment analysis of Microsoft Teams messages, providing instant emotional context feedback through automated replies.

## Workflow Components

### Manual Trigger
- Initiates the workflow when manually executed
- Serves as the starting point for message analysis

### Microsoft Teams Message Retrieval
- Reads the latest message from specified Teams channel
- Configuration path: Microsoft Teams → Channel Message → Get All
- Limits retrieval to 1 message for immediate analysis

### Sentiment Analysis Node
- Processes message content for emotional context
- Uses Langchain integration for analysis
- Configuration settings:
  ```json
  {
    "categories": ["Positive", "Negative"],
    "includeDetailedResults": true,
    "inputText": "={{ $json.body.content }}"
  }
  ```

### Ollama Chat Model
- Local LLM integration using llama3.2
- Provides AI processing capabilities
- Configuration:
  ```json
  {
    "model": "llama3.2:latest",
    "options": {}
  }
  ```

### Response Nodes (Positive/Negative)
- Two separate nodes for handling different sentiment outcomes
- Reply format:
  ```
  Sentiment Analysis Result

  Input Message: [Original Message]

  Category: [Positive/Negative]
  Strength: [Value] (Indicating sentiment level)
  Confidence: [Score]
  ```

## Purpose
This workflow is designed to automate sentiment analysis of Teams messages, providing instant feedback on the emotional context of communications. It helps in understanding message tone and maintaining communication awareness in digital conversations.

## Usage
1. Ensure your n8n instance has access to:
   - Microsoft Teams channel
   - Local Ollama service
   - Required credentials

2. Configure the workflow:
   - Set up Microsoft Teams OAuth2 credentials
   - Configure Team ID and Channel ID
   - Ensure Ollama service is running with llama3.2 model

3. Execute:
   - Navigate to the workflow in n8n
   - Click "Test workflow"
   - Check Teams channel for analysis reply

## Note
- Ensure Microsoft Teams permissions are properly configured
- The workflow analyzes one message at a time
- Response time depends on Ollama model performance
