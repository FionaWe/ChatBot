## Overview
This project creates a web server that acts as a proxy between client applications and a locally running Ollama instance. It simplifies the process of generating text from large language models by providing a clean API endpoint that handles streaming responses.

## Features
- Simple REST API for text generation
- Streaming responses for real-time text generation
- Minimal dependencies

## Requirements
- Python 3.6+
- Flask
- Requests
- A running Ollama instance with models installed


## Installation
Clone this repository:

```
git clone https://github.com/FionaWe/ChatBot.git
cd chatbot
```

Install the required dependencies:
```
pip install -r requirements.txt
```
Make sure Ollama is running locally:

```
ollama serve
```

Start the proxy server:

```
python app.py
```
## Usage
The server exposes a single endpoint at /generate that accepts POST requests with a JSON body containing a prompt:

```
curl -X POST http://localhost:8080/generate \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Hello, how are you?"}'
```
The response will be streamed as plain text.
```
Hello! I'm just a virtual assistant, so I don't have feelings, but I'm here and ready to help you with whatever you need. How are *you* doing? 😊% 
```

## Configuration
You can modify the following variables in app.py:

- OLLAMA_API_BASE: The base URL of your Ollama instance (default: http://localhost:11434)
- MODEL: The model to use for generation (default: deepseek-r1:1.5b)
- Port and host settings in the app.run() call

## Customization
To use a different model, modify the MODEL variable in app.py:
```
MODEL = "llama3:8b"  # Or any other model you have installed in Ollama
```
## Troubleshooting
Make sure Ollama is running and accessible at http://localhost:11434
Verify that the model specified in MODEL is installed in your Ollama instance

Check the Flask server logs for any error messages
License
MIT

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

