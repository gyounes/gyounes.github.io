---
title: "LangGraph Research Agent"
date: 2026-02-06
draft: false
weight: 2
---

Intelligent research agent with conditional routing built using LangGraph and LangChain.

## Overview

Agentic system that intelligently routes user questions based on whether they require external information or can be answered with general knowledge.

## Tech Stack

- Python 3.12
- LangGraph 1.0+
- LangChain (OpenAI integration)
- OpenAI GPT-4o-mini

## Architecture

Uses StateGraph with conditional routing:
- **Classify node** - LLM decides if search is needed
- **Search node** - Fetches external information (mocked)
- **Synthesize node** - Combines search results with question
- **Answer node** - Direct LLM response for general knowledge

## Key Concepts Demonstrated

- **StateGraph** - Core LangGraph abstraction for agent workflows
- **Conditional routing** - Dynamic path selection based on LLM classification
- **Typed state management** - Using TypedDict for structured data flow
- **Separation of concerns** - Routing logic separate from node implementations

## What I Learned

Building this reinforced the importance of separating decision-making (routing) from execution (nodes). The conditional edge pattern keeps the graph logic clean and testable. In a production system, I'd replace the mock search with a real API (Tavily/Serper) and add conversation memory for multi-turn interactions.

## Links

- [GitHub Repository](https://github.com/gyounes/langgraph-research-agent)
- [Documentation](https://github.com/gyounes/langgraph-research-agent#readme)
