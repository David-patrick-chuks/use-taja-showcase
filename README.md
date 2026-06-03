# use-taja-showcase

`use-taja-showcase` is the public product reference for **Taja**, a WhatsApp-first commerce platform that lets customers shop, sellers manage inventory, and admins run the marketplace from one connected system.

This repo is intentionally lightweight. It is meant to help any team member, whether they work in engineering, product, design, operations, or support, understand:

- what the product is
- who it is for
- what the experience should feel like
- what must be built first
- how success is measured

## What You’ll Find Here

- A full product requirement document in [docs/PRD.md](docs/PRD.md)
- A project goal document in [docs/PROJECT_GOAL.md](docs/PROJECT_GOAL.md)
- A simple docs structure that can grow with the project
- A shared product language for all team members

## Product Summary

Taja is a commerce platform designed to keep the main customer journey inside WhatsApp.

The platform supports:

- customer browsing, cart, checkout, and tracking
- seller onboarding, product management, and payouts
- admin moderation, analytics, and support tooling
- official WhatsApp Cloud API flows for forms and structured actions
- fallback compatibility for legacy WhatsApp provider behavior

## Core Principle

The platform should feel simple to use even when the backend is complex.

That means:

- fewer app switches
- clearer menus and guided actions
- structured forms for sensitive or repetitive input
- fast support for customers and sellers
- reliable admin controls behind the scenes

## Who This Repo Is For

- Product managers who need the full feature scope
- UI and UX designers who need the user journey and interaction model
- Backend developers who need system requirements and constraints
- QA testers who need acceptance criteria and edge cases
- Operations and support teams who need to understand how the product works

## How To Use This Repo

1. Start with [docs/PRD.md](docs/PRD.md) for the full product definition.
2. Use this README as the top-level summary.
3. Add future documents under `docs/` as the product grows.

## Repo Structure

```text
use-taja-showcase/
├── README.md
└── docs/
    ├── PRD.md
    ├── PROJECT_GOAL.md
    └── README.md
```

## Current Scope

This repo documents the product. It does not contain the full application source code.

The implementation lives in the separate project repos for backend, web, model, and landing page.

## Short Version

Taja is a WhatsApp-native commerce platform for shopping, selling, support, and operations.
