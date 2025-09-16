# AI Studio

This repository contains AI projects and experiments, including CrewAI agents and other AI-related tools.

## Projects

### hw1/mrugank_ai
A personal AI assistant built with CrewAI that can help with:
- Personal introductions
- Email drafting
- Text summarization
- Professional communications

The agent is configured to represent Mrugank Pednekar, a Master of Business Analytics student at MIT Sloan, with expertise in AI agents for user feedback and interview processes.

## Setup

1. Navigate to the specific project directory
2. Install dependencies using `uv` or `pip`
3. Set up environment variables for your preferred AI model provider
4. Run the project using the provided scripts

## Environment Variables

For the CrewAI projects, you'll need to set up API keys for your preferred model provider:

```bash
# For Cerebras
export CEREBRAS_API_KEY="your_cerebras_api_key"
export MODEL="cerebras/llama3.1-8b"

# For OpenAI
export OPENAI_API_KEY="your_openai_api_key"
export MODEL="gpt-4o-mini"

# For other providers, see CrewAI documentation
```

## Usage

Each project has its own README with specific instructions for setup and usage.
