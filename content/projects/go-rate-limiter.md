---
title: "Go Rate Limiter"
date: 2026-01-26
draft: false
weight: 3
---

A distributed rate limiting service built in Go, featuring token bucket algorithm, Redis backend with automatic fallback, and production-ready features.

## Key Features

- **Token Bucket Algorithm**: Industry-standard rate limiting with burst support
- **Distributed Architecture**: Redis backend for multi-instance deployments
- **Automatic Fallback**: Graceful degradation to in-memory storage
- **Retry Logic**: Exponential backoff for Redis operations
- **Production Ready**: Docker support, CI/CD, comprehensive testing

## Tech Stack

- **Language**: Go 1.24
- **Storage**: Redis (with in-memory fallback)
- **Testing**: Standard library + table-driven tests
- **Infrastructure**: Docker, GitHub Actions
- **Architecture**: HTTP middleware pattern

## What I Learned

### Go Idioms and Patterns

- **Composition over inheritance**: Interfaces for storage abstraction
- **Concurrency primitives**: Mutex vs RWMutex for different access patterns
- **Error handling**: Explicit error returns vs panic for different scenarios
- **Memory optimization**: Multi-stage Docker builds reducing image size 23x

### Systems Design

- **Graceful degradation**: Automatic fallback when dependencies fail
- **Retry strategies**: Exponential backoff to prevent retry storms
- **State management**: Choosing between local and distributed state
- **Configuration design**: Environment-based with sensible defaults

### Testing Philosophy

Wrote 16 tests covering:
- Unit tests for core algorithms
- Integration tests for HTTP flows
- Table-driven tests for multiple scenarios
- Mock failures for error paths

### Production Concerns

- **Observability**: Metrics endpoint for monitoring
- **Operational simplicity**: Single binary deployment
- **Performance**: <1μs for in-memory, ~2ms for Redis operations
- **Security**: No exposed credentials, configurable via env vars

## Performance

- Docker image: ~15MB (multi-stage build)
- In-memory latency: <1 microsecond
- Redis latency: 1-2ms (network-dependent)
- Throughput: Handles concurrent requests safely

## Links

- [GitHub Repository](https://github.com/gyounes/go-rate-limiter)
- [Live Demo](https://github.com/gyounes/go-rate-limiter#quick-start) (run locally)