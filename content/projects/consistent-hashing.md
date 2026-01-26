---
title: "Consistent Hashing Library"
date: 2026-01-26
draft: false
weight: 2
---

Thread-safe consistent hashing implementation in Python.

## Overview
High-performance library for distributing keys across dynamic node sets with minimal redistribution.

## Tech Stack
- Python 3.13
- pytest for testing
- matplotlib for visualization

## Features
- Thread-safe operations with locks
- Weighted nodes for heterogeneous clusters
- Visualization of key distribution
- Efficient O(log N) lookups using bisect

## What I Learned
This project connected my PhD research in distributed systems to practical implementation - seeing how theory (consistent hashing minimizes key movement) translates to real performance gains (only ~20% keys moved when adding nodes vs 80-100% with naive hashing).

## Links
- [GitHub Repository](https://github.com/gyounes/consistent-hashing)