# Working-with-Ollama

This repository contains a Jupyter notebook demonstrating how to work with Ollama, a platform for running large language models locally. The notebook provides a comprehensive set of utilities for installing, managing, and interacting with Ollama models.

## Features

- Easy installation of Ollama and required dependencies
- Helper functions for managing Ollama server processes
- Model management utilities (pull, list, remove)
- Interactive query capabilities with both standard and streaming responses
- Performance benchmarking tools
- Error handling wrappers

## Prerequisites

- Python 3.x
- Jupyter Notebook/Lab
- Unix-based system (Linux/MacOS) for Ollama installation

## Installation

1. Clone the repository:
```bash
git clone https://github.com/SakibAhmedShuva/Working-with-Ollama.git
cd Working-with-Ollama
```

2. Install the required Python packages:
```bash
pip install huggingface_hub transformers accelerate
```

3. Install system dependencies:
```bash
apt-get update && apt-get install wget curl git -y
```

4. Install Ollama:
```bash
curl -fsSL https://ollama.com/install.sh | sh
```

## Usage

The main notebook `ollama.ipynb` contains several key components:

### 1. Server Management
```python
# Start the Ollama server
server_process = start_ollama_server()

# Remember to stop the server when done
stop_ollama_server(server_process)
```

### 2. Model Setup and Querying
```python
# Pull and setup a model
setup_ollama_model("llama2")

# Query the model
response = query_ollama("What is machine learning?", "llama2")
```

### 3. Streaming Responses
```python
# Get streaming responses for real-time output
stream_ollama_response("Write a short poem about AI", "llama2")
```

### 4. Model Management
```python
# List available models
print(list_available_models())

# Remove a model
remove_model("model_name")
```

### 5. Performance Monitoring
```python
# Benchmark model performance
benchmark_model("llama2", num_queries=5)
```

## Functions Overview

- `start_ollama_server()`: Initializes the Ollama server
- `stop_ollama_server(process)`: Gracefully terminates the server
- `setup_ollama_model(model_name)`: Downloads and sets up specified models
- `query_ollama(prompt, model_name)`: Sends queries to the model
- `stream_ollama_response(prompt, model_name)`: Provides streaming responses
- `list_available_models()`: Shows all installed models
- `remove_model(model_name)`: Removes specified models
- `safe_ollama_query(prompt, model_name)`: Error-handled query wrapper
- `benchmark_model(model_name, num_queries)`: Tests model performance

## Error Handling

The notebook includes error handling wrappers to manage common issues:
- Server connection failures
- Model loading errors
- Query timeouts
- Resource management

## Contributing

Feel free to open issues or submit pull requests for improvements and bug fixes.

## License

This project is open source and available under the [MIT License](LICENSE).

## Acknowledgments

- Ollama team for providing the base platform
- HuggingFace for transformer models support
