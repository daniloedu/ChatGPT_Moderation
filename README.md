# ChatGPT Moderation and Prompting Injection
## Introduction
This repository contains a Jupyter notebook that showcases experimentation with the OpenAI CHATGPT API. The notebook provides insights into structuring prompts and instructions to obtain desired outputs from the model. It further explores the model's capability to detect potential prompt injections or malicious instructions.

## Requirements
### Prerequisites
1. **Python Environment**: The code is written in Python and requires a Python 3.x environment.
2. **Python Libraries**: Ensure you have the following libraries installed in your system:
   - `os`
   - `openai`
   - `dotenv`
3. **OpenAI API Key**: You'll need an API key from OpenAI to interact with the service. Store it securely in an `.env` file or another secure location and make sure it's accessible to the notebook.

## Code Explanation
### Setup and Initialization
- **Library Imports**: The necessary Python libraries for the code's operation are imported.
- **Environment Variable Loading**: The code uses `dotenv` to load essential environment variables, particularly the OpenAI API key.

### Function Definitions
1. `get_completion_from_messages(messages, model="gpt-3.5-turbo", temperature=0, max_tokens=500)`: This function is designed to send a series of messages to the OpenAI model and receive a structured response. It takes into account:
    - `messages`:  A list of message objects containing a role (either "system" or "user") and content (the actual message).
    - `model`:  The OpenAI model to use (default is "gpt-3.5-turbo").
    - `temperature`: Adjusts the randomness of the model's output.
    - `max_tokens`: Limits the length of the model's response.
  
### Content Moderation
The notebook demonstrates using the OpenAI Moderation API to check for potentially harmful content in user inputs. A sample input, which seems like a quote from a movie, is sent to the model to evaluate its acceptability. Also, it replies with the certainty of how a request violates the guidelines of the use of the model.

### Example of Structured Prompting in Italian
The notebook introduces a structured system message that instructs the model to always respond in Italian. By using a delimiter, the model can identify and process user queries accurately. Two examples are presented:
  - A regular query.
  - A query attempting to override the system's instructions.

### Detecting Prompting Injection
The notebook presents a use case where the model detects potential prompt injections or malicious instructions. By providing the model with a series of messages, including examples of good and bad user inputs, the model learns to identify and flag suspicious inputs.

### Usage Tips
- Adjust the `temperature` and `max_tokens` parameters to influence the model's outputs.
- Always be wary of potential prompt injections, especially when accepting user inputs. The provided approach in the notebook is a good starting point but might require further refinements based on specific use-cases.
- The use of delimiters helps in clearly defining the start and end of a user's query, ensuring accurate model responses.
