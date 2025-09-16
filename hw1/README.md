# HW1: Personal AI Assistant with CrewAI

## Project Overview

This project implements a personal AI assistant using CrewAI framework that can help with various tasks including text summarization, email drafting, personal introductions, and professional communications. The agent is specifically configured to represent Mrugank Pednekar, a Master of Business Analytics student at MIT Sloan.

## What It Does

### Core Functionality
- **Personal Introductions**: Creates professional and engaging introductions tailored to different contexts and audiences
- **Email Drafting**: Generates complete email drafts with appropriate subject lines, greetings, body content, and closings
- **Text Summarization**: Provides clear and concise summaries of complex information with structured formatting
- **Professional Communications**: Adapts tone and content based on academic, professional, or casual contexts

### Agent Configuration
The agent is configured with the following personal information:
- **Name**: Mrugank Pednekar
- **Education**: Master of Business Analytics student at MIT Sloan
- **Interests**: Creating AI agents to streamline user feedback and interview processes
- **Location**: Boston, MA

## Technical Architecture

### Framework
- **CrewAI**: Multi-agent framework for building AI assistants
- **LiteLLM**: Model abstraction layer supporting multiple providers
- **Python**: Core programming language

### Model Support
- **Cerebras**: Primary model provider (llama3.1-8b)
- **OpenAI**: Alternative provider support
- **Other Providers**: Extensible to any LiteLLM-supported provider

### Project Structure
```
mrugank_ai/
├── src/mrugank_ai/
│   ├── config/
│   │   ├── agents.yaml      # Agent configuration
│   │   └── tasks.yaml       # Task definitions
│   ├── crew.py              # Crew orchestration
│   ├── main.py              # Entry point
│   └── tools/               # Custom tools
├── knowledge/
│   └── user_preference.txt  # Personal information
├── pyproject.toml           # Dependencies
└── README.md               # Project documentation
```

## Setup Instructions

### Prerequisites
- Python 3.10-3.13
- UV package manager (recommended) or pip

### Installation
1. Navigate to the project directory:
   ```bash
   cd mrugank_ai
   ```

2. Install dependencies:
   ```bash
   uv sync
   # or
   pip install -e .
   ```

3. Set up environment variables:
   ```bash
   # For Cerebras
   export CEREBRAS_API_KEY="your_cerebras_api_key"
   export MODEL="cerebras/llama3.1-8b"
   
   # For OpenAI
   export OPENAI_API_KEY="your_openai_api_key"
   export MODEL="gpt-4o-mini"
   ```

### Running the Agent
```bash
# Run with default introduction task
uv run run_crew

# Or using the project script
python -m mrugank_ai.main
```

## Available Tasks

### 1. Introduction Task
- **Purpose**: Create professional introductions for various contexts
- **Input**: Context-specific prompt (e.g., "Introduce yourself to the class")
- **Output**: Tailored introduction highlighting relevant background

### 2. Email Draft Task
- **Purpose**: Generate complete email drafts
- **Input**: Email requirements and context
- **Output**: Professional email with subject, greeting, body, and closing

### 3. Summarize Task
- **Purpose**: Summarize complex information
- **Input**: Text or information to summarize
- **Output**: Structured summary with key points

## Customization

### Adding New Tasks
1. Define the task in `config/tasks.yaml`
2. Add the task method in `crew.py`
3. Update the crew configuration to include the new task

### Modifying Agent Behavior
- Edit `config/agents.yaml` to change agent personality, goals, or backstory
- Update `knowledge/user_preference.txt` with new personal information

### Adding Tools
- Create custom tools in `src/mrugank_ai/tools/`
- Register tools in the agent configuration

## Troubleshooting

### Common Issues
1. **Import Errors**: Ensure the project is properly installed and paths are correct
2. **API Key Issues**: Verify environment variables are set correctly
3. **Model Errors**: Check provider-specific API keys and model availability

### Getting Help
- Check the CrewAI documentation: https://docs.crewai.com/
- Review LiteLLM provider documentation for specific model requirements

## Future Enhancements

- Web scraping capabilities for real-time information gathering
- Integration with calendar and email systems
- Multi-language support
- Advanced personalization based on interaction history
- Integration with external APIs and services
