# REBA - Real Estate Booking Assistant

REBA is an AI agent designed to convert property owner leads into booked appointments through a structured conversation flow enhanced with voice and video interactions.

## Key Features

- **Intelligent Conversation Flow**: Guided 4-step process from greeting to booking
- **HeyGen Interactive Avatar**: Visual and voice interaction capabilities
- **Property Valuation**: Integration with Zillow API for property analysis
- **Multiple Offer Strategies**: Presents three tailored cash offer options
- **Objection Handling**: Smart responses to common seller concerns

## Architecture

### Core Components

1. **Agent Core**
   - Conversational AI agent with real estate expertise
   - Session-based conversation memory
   - Property analysis tools
   - Offer calculation logic

2. **Audio/Video Pipeline**
   - Pipecat audio pipeline integration
   - Deepgram Speech-to-Text
   - ElevenLabs Text-to-Speech
   - HeyGen avatar visualization

3. **API Layer**
   - FastAPI server with WebSocket support
   - Real-time communication capabilities

## Getting Started

### Prerequisites

- Python 3.9+
- API keys for:
  - AI model provider (OpenAI, Anthropic, Gemini, or OpenRouter)
  - RapidAPI (for Zillow integration)
  - Deepgram
  - ElevenLabs
  - HeyGen

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/Sirjoshodevelops/flwowise.git
   cd flwowise
   ```

2. Set up a virtual environment
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables
   ```bash
   cp .env.example .env
   # Edit .env with your API keys
   ```

5. Run the application
   ```bash
   python -m src.main
   ```

## Conversation Flow

REBA follows a structured conversation flow:

1. **GATHER**: Collect property information (prioritizing timeline and mortgage balance)
2. **ANALYZE**: Process information and calculate property value
3. **OFFER**: Present three cash offer options with clear benefits
4. **BOOK**: Schedule consultation appointment

## Project Structure

```
src/
├── reba_agent.py      # Main agent implementation
├── agent_tools.py     # Property analysis tools
├── agent_prompt.md    # System prompt
└── server/            # FastAPI server and HeyGen integration
```

## License

[MIT](LICENSE)