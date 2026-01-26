---
title: "Distributed Rate Limiter"
date: 2026-01-26
draft: false
weight: 1
---

Production-ready rate limiting service using the token bucket algorithm.

## Overview
Distributed rate limiter with Redis backend, automatic failover, and comprehensive observability.

## Tech Stack
- Python 3.12, FastAPI
- Redis (with in-memory fallback)
- Docker + docker-compose
- GitHub Actions CI/CD

## Performance
- **Throughput:** 185-242 req/sec
- **Test Coverage:** 75%
- **Zero errors** under 10k request load

## Key Features
- Token bucket algorithm (industry standard: AWS, Stripe)
- Redis for distributed state across instances
- Exponential backoff retry (100ms → 200ms → 400ms)
- Metrics endpoint for monitoring
- Comprehensive error handling

## What I Learned
Implementing this taught me the importance of graceful degradation - the permanent fallback to in-memory storage keeps the service available even when Redis fails, though at the cost of distributed state. In production, I'd use a circuit breaker pattern for automatic recovery.

## Links
- [GitHub Repository](https://github.com/gyounes/rate-limiter)
- [Documentation](https://github.com/gyounes/rate-limiter#readme)