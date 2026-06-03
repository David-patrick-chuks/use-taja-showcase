# User Journeys

## Purpose

This document describes the main end-to-end journeys for customers, sellers, admins, and support users.

## Journey 1: Customer Browse to Checkout

| Step | User Action | System Response |
|---|---|---|
| 1 | Opens WhatsApp conversation | Shows onboarding or main menu |
| 2 | Browses categories or searches | Returns ranked products and guided actions |
| 3 | Opens product details | Shows price, availability, and next step options |
| 4 | Adds item to cart | Updates cart state |
| 5 | Proceeds to checkout | Requests shipping and payment details |
| 6 | Confirms order | Creates order and sends receipt/confirmation |

## Journey 2: Seller Onboarding to Listing

| Step | User Action | System Response |
|---|---|---|
| 1 | Starts seller flow | Shows seller onboarding path |
| 2 | Submits business details | Stores profile and validates required fields |
| 3 | Sets payout details | Captures settlement information |
| 4 | Adds products | Saves product data and media |
| 5 | Reviews listing status | Shows pending, approved, or rejected state |

## Journey 3: Admin Operations

| Step | User Action | System Response |
|---|---|---|
| 1 | Logs into admin system | Verifies access and permissions |
| 2 | Reviews orders, users, and sellers | Loads operational dashboards |
| 3 | Approves or rejects content | Updates platform state and records audit logs |
| 4 | Handles support cases | Routes escalation or replies to user |
| 5 | Reviews metrics | Shows activity, revenue, and health indicators |

## Journey 4: Support Escalation

| Step | User Action | System Response |
|---|---|---|
| 1 | Requests help in WhatsApp or web | Collects issue details |
| 2 | AI triages the issue | Suggests category or next action |
| 3 | Human review if needed | Routes to support staff |
| 4 | Resolution sent | Updates user and logs outcome |

## Journey 5: Account Deletion

| Step | User Action | System Response |
|---|---|---|
| 1 | Opens deletion page | Shows account removal warning |
| 2 | Confirms identity | Verifies the signed-in user |
| 3 | Submits request | Marks account for deletion or immediate removal |
| 4 | Completion message | Confirms the action and next steps |

## Cross-Journey Rules

| Rule | Requirement |
|---|---|
| State continuity | Users should not lose progress if they return later |
| Clear status | Every journey should show where the user is |
| Safe recovery | Users should be able to recover from errors or retries |
| Minimal friction | Keep the number of steps as low as possible |

## Summary

The journey design should make Taja feel like one connected product, even though users may move between WhatsApp, web, and admin tools.
