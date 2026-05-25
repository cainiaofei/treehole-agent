# Treehole Agent

Treehole Agent is an LLM-powered emotional support and anonymous matching platform.

In Phase 1, it provides a safe, empathetic AI companion for users experiencing stress, anxiety, sadness, loneliness, or other difficult emotions.

In Phase 2, it builds privacy-preserving emotional profiles and helps users discover others with similar experiences, only after explicit user opt-in.

## Why this project exists

Many people need a low-pressure place to express what they are going through. Traditional social platforms often feel too public, while professional help may not always be immediately available. Treehole Agent aims to provide a private, non-judgmental first step: a place to talk, reflect, and feel heard.

This product is not a therapist, does not provide medical diagnosis, and should not replace professional care. It is designed as an emotional support and reflection tool with clear safety boundaries.

## Product Phases

### Phase 1: AI Treehole Companion

The first version focuses on one-on-one conversation between a user and an AI agent.

Core capabilities:

- Anonymous chat experience
- Empathetic and non-judgmental responses
- Emotional state and topic extraction
- Conversation summary and lightweight memory
- Safety risk detection for self-harm, suicide, violence, abuse, or medical crisis signals
- User consent and privacy controls

### Phase 2: Similar Experience Matching

The second phase introduces privacy-preserving matching between users who opt in.

Core capabilities:

- Anonymous emotional profile generation
- Semantic similarity search over user profiles
- Matching based on topics, emotions, language, support preference, and risk level
- Double opt-in before any user-to-user connection
- No raw conversation sharing between users
- High-risk users excluded from normal peer matching flows

## Initial Architecture

```text
User
  ↓
Frontend Chat UI
  ↓
Backend API
  ↓
LLM Orchestrator
  ├── Safety Agent
  ├── Conversation Agent
  ├── Profile Extractor
  └── Embedding Service
  ↓
PostgreSQL + pgvector
  ├── Conversations
  ├── Messages
  ├── Emotional Profiles
  └── Match Candidates
```

## Recommended MVP Tech Stack

- Frontend: Next.js + TypeScript
- Backend: Python FastAPI
- Database: PostgreSQL + pgvector
- LLM Provider: OpenAI API first, with a provider interface for future Bedrock or other models
- Local Development: Docker Compose
- Testing: pytest for backend, standard frontend test setup later

## Safety Principles

Treehole Agent should follow these principles from the beginning:

- Never claim to be a therapist or doctor
- Never provide medical diagnosis
- Always handle crisis or self-harm signals conservatively
- Encourage users in crisis to contact local emergency services or trusted people around them
- Avoid matching users who are currently high risk
- Store only what is necessary
- Use opt-in for profile-based matching
- Support data deletion and matching opt-out

## Repository Status

This repository currently contains the initial product and agent planning documents. Implementation will be added incrementally through small, reviewable tasks.

## Planned Development Steps

1. Define product scope and safety boundaries
2. Create backend skeleton with FastAPI
3. Add OpenAI provider abstraction
4. Implement chat API
5. Implement Safety Agent
6. Implement Profile Extractor Agent
7. Add PostgreSQL schema and migrations
8. Add pgvector-based profile matching
9. Build frontend chat UI
10. Add consent and privacy controls
11. Add tests and CI

## License

TBD.
