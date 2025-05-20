# Next-Gen Microservice Gateways: Real-Time Forwarding with Bun

Explore how Bun and TypeScript can be combined to build a lightning-fast, real-time gateway that forwards incoming requests to microservices based on live context. Learn how this modern architecture improves performance, simplifies routing logic, and reduces latency in microservice communication.

[![Next-Gen Microservice Gateways: Real-Time Forwarding with Bun](poster.png)](https://basemax.github.io/microservice-gateways-forwarding-talk/presentation.html)

**View slides:** https://basemax.github.io/microservice-gateways-forwarding-talk/presentation.html

## Overview

In today's microservice architectures, latency and scalability remain critical challenges — especially when handling dynamic, real-time routing of client requests. Traditional solutions like NGINX or Express-based proxies often introduce bottlenecks and unnecessary complexity.

This talk presents a high-performance gateway built with **Bun** and **TypeScript**, designed to forward HTTP requests in real-time to microservices or sub-projects based on context, headers, or routing rules. 

We’ll explore:
- How Bun’s speed and native TypeScript support make it ideal for gateway development
- A working example of live request forwarding across multiple services
- Architecture diagrams, benchmarks, and lessons learned

Whether you're scaling a large platform or building the backend for your next startup, this session will show how to rethink your gateway layer using modern tools.

## What You'll Learn

1. How to design and implement a real-time gateway using Bun + TypeScript that forwards requests with minimal latency.
2. Why Bun can replace traditional reverse proxies and Node.js-based routers for superior performance in microservice environments.

## Build Slides

To build the presentation slides:

```bash
# On Linux/macOS:
bash b.sh

# On Windows (cmd0
b.bat

# On Windows (with Git Bash or WSL):
./b.sh
```

## Conference Details

Node.js Global Summit 25

May 20 | Node.js Day

## License

© 2025 Max Base

License MIT
