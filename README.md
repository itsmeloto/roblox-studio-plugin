# Roblox Studio AI Plugin Server

This is the server component of the Roblox Studio AI Plugin. It provides API endpoints for the Roblox Studio plugin to interact with AI models, manage users, and handle file uploads.

## Features

- **Multiple AI Providers**: Support for OpenRouter, Hugging Face, and Ollama
- **User Authentication**: Role-based access control with different permission levels
- **Usage Logging**: Comprehensive logging of AI requests and responses
- **Chat History**: Persistent conversation history for each user
- **File Management**: Upload, download, and manage files for use in Roblox Studio
- **Admin Panel API**: Endpoints for managing users and viewing logs

## Setup

### Prerequisites

- Python 3.7 or higher
- pip (Python package manager)

### Installation

1. Clone the repository:
   ```
   git clone https://github.com/yourusername/roblox-studio-ai-plugin.git
   cd roblox-studio-ai-plugin/server
   ```

2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

3. Configure API keys:
   - Open `config.py` and update the API keys for the AI providers you want to use
   - By default, the server uses OpenRouter with a free API key

4. Run the server:
   ```
   python app.py
   ```

The server will start on port 5000 by default. You can change the port by setting the `PORT` environment variable.

## API Endpoints

### Authentication

- `POST /auth_check`: Check if a user is authorized and get their role information
- `POST /add_user`: Add a user to the authorized list
- `POST /remove_user`: Remove a user from the authorized list
- `POST /update_user`: Update a user's role
- `GET /list_users`: List all authorized users

### AI Generation

- `POST /generate`: Generate a response from the AI model
- `GET /get_models`: Get available AI models

### Chat History

- `GET /get_conversation`: Get a conversation history
- `GET /get_user_conversations`: Get all conversations for a user
- `POST /clear_conversation`: Clear a conversation history

### File Management

- `POST /upload_file`: Upload a file
- `GET /get_file/<file_id>`: Get a file by ID
- `POST /delete_file`: Delete a file by ID
- `GET /list_files`: List files with optional filtering

### Logging and Statistics

- `GET /get_logs`: Get usage logs
- `GET /get_usage_stats`: Get usage statistics

## Deployment

### Railway

1. Create a new project on [Railway](https://railway.app/)
2. Connect your GitHub repository
3. Add the following environment variables:
   - `PORT`: 5000
   - `OPENROUTER_API_KEY`: Your OpenRouter API key
   - `HUGGINGFACE_API_KEY`: Your Hugging Face API key (optional)
4. Deploy the project

### Heroku

1. Create a new app on [Heroku](https://heroku.com/)
2. Connect your GitHub repository
3. Add the following environment variables:
   - `OPENROUTER_API_KEY`: Your OpenRouter API key
   - `HUGGINGFACE_API_KEY`: Your Hugging Face API key (optional)
4. Deploy the app

### Self-hosted

1. Install the required dependencies
2. Configure the API keys in `config.py`
3. Run the server using a production WSGI server:
   ```
   gunicorn app:app
   ```

## License

This project is licensed under the MIT License - see the LICENSE file for details.

