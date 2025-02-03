# Local Ollama Setup

This repository provides a streamlined setup for running Ollama with DeepSeek models, featuring external API access and monitoring capabilities.

## Quick Start

One-step deployment:
```bash
curl -fsSL https://ollama.com/install.sh | sh && ollama run deepseek-r1:1.5b
```

The API will be available at: `http://localhost:11434`

## Models

Currently supported models:
- DeepSeek R1:1.5b (default)
- DeepSeek R1:32b (requires 24GB+ RAM)

## API Usage

Send requests to the API endpoint:
```bash
curl -X POST http://localhost:11434/api/generate -d '{
  "model": "deepseek-r1:1.5b",
  "prompt": "Your prompt here"
}'
```

Example response:
```json
{
  "model": "deepseek-r1:1.5b",
  "created_at": "2024-02-04T12:34:56.789Z",
  "response": "Generated text will appear here",
  "done": true
}
```

## System Requirements

Minimum requirements:
- Linux-based system
- 8GB RAM for 1.5B model
- 24GB RAM for 32B model
- 10GB free storage
- Port 11434 available

## Monitoring

The setup includes Prometheus monitoring:
1. Metrics available at: `http://localhost:9090`
2. Node exporter metrics: `http://localhost:9100`
3. Ollama metrics: `http://localhost:11434/metrics`

To start monitoring:
```bash
cd monitoring
docker-compose up -d
```

## Troubleshooting

Common issues:
1. Port already in use: Check if port 11434 is available
2. Memory issues: Verify system has sufficient RAM for chosen model
3. API connection: Ensure firewall allows connections to port 11434

## Security Notes

- The API is configured to accept external connections
- Basic authentication is enabled by default
- Firewall rules are configured to allow only necessary ports
