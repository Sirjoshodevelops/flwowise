# REBA Project Planning

## Project Overview
REBA (Real Estate Booking Assistant) is an AI assistant designed to convert property owners into booked appointments through a structured conversation flow. The system has been enhanced with HeyGen Interactive Avatar integration for voice and video interactions.

## Architecture
The project follows a modular architecture with the following key components:

1. **Core Agent Logic**
   - Main REBA agent implementation with conversation flow and real estate expertise
   - Custom Pydantic processor for integration with Pipecat

2. **Integration Components**
   - HeyGen Interactive Avatar frontend
   - Pipecat audio pipeline integration
   - Deepgram for Speech-to-Text
   - ElevenLabs for Text-to-Speech

3. **API Layer**
   - FastAPI server with WebSocket support for real-time communication

## Design Guidelines
- Keep code modular and organized by feature or responsibility
- Agent structure should follow:
  - `agent.py` - Main agent definition and execution logic
  - `tools.py` - Tool functions used by the agent
  - `prompts.py` - System prompts
- Follow PEP8, use type hints, and format with `black`
- Use Pydantic for data validation
- Include comprehensive documentation

## Implementation Constraints
- Files should not exceed 500 lines; split into modules when approaching this limit
- All functions should have Google-style docstrings
- Non-obvious code should be commented with explanations

## Conversation Flow
1. Warm greeting
2. Property information gathering (timeline and mortgage balance are high priority)
3. Present three cash offer options:
   - Wholesale
   - Retail Listing
   - Creative Finance
4. Value explanation
5. Appointment booking

## Testing Strategy
- Pytest for all unit tests
- Tests should be organized under a `/tests` directory
- Each feature should have at least 3 tests:
  - Expected use case
  - Edge case
  - Failure case