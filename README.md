# Local Ollama Setup

This repository contains configuration and setup for running Ollama locally with the DeepSeek R1:1.5b model.

## Requirements
- Linux-based system
- Port 11434 available
- Sufficient disk space for the model

## Installation
1. Install Ollama
2. Download and run the DeepSeek R1:1.5b model
3. Configure API access
4. Set up firewall rules

## API Usage
Send requests to `http://localhost:11434/api/generate` with the following format:
```json
{
  "model": "deepseek-r1:1.5b",
  "prompt": "Your prompt here"
}
```
