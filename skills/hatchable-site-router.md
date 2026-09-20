---
name: intentguard-router
description: Route an AI task to the lowest-cost model that can complete it reliably. Returns model choice, cheaper alternative, optimized prompt and fallback.
version: 1.0.0
homepage: https://intentguard.hatchable.site
openapi: https://intentguard.hatchable.site/openapi.json
mcp: https://intentguard.hatchable.site/api/mcp
payment: x402
network: eip155:8453
price: 0.0009 USDC
---

# IntentGuard Router

Use before executing an AI task when model choice affects cost, speed or reliability.

## Free preview

POST `/api/router-preview` with `task` and optional constraints.

## Paid tool

MCP tool: `route_task`

HTTP: `POST /api/route`

Input:
- `task`: work to execute
- `objective`: balanced, lowest_cost, fastest or highest_quality
- `risk_level`: low, medium or high
- `available_models`: optional live model catalog with cost and capability fields
- `input_tokens` and `output_tokens`: optional estimates for dollar-cost calculation

Output:
- recommended model
- cheapest acceptable alternative
- model to avoid
- optimized prompt
- fallback
- savings and confidence

Each call costs 0.0009 USDC on Base via x402.