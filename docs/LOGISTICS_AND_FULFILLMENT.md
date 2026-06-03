# Logistics and Fulfillment

## Purpose

This document covers shipping, tracking, delivery, and fulfillment operations for Taja.

## Core Fulfillment Stages

| Stage | Description |
|---|---|
| Address capture | Collect a valid delivery address |
| Rate selection | Show available shipping options |
| Shipment creation | Create a shipment with the carrier or logistics partner |
| Tracking | Store and update shipment tracking info |
| Delivery | Mark the order as delivered or failed |
| Returns | Handle return or reverse logistics when needed |

## Required Data

| Field | Description |
|---|---|
| Recipient name | Delivery contact name |
| Phone number | Delivery contact number |
| Address line | Street and detailed address |
| City | Delivery city |
| State | Delivery state or region |
| Postal code | Postal or ZIP code |
| Country | Delivery country |
| Shipping method | Selected fulfillment option |
| Tracking code | Carrier tracking reference |

## Fulfillment Rules

| Rule | Requirement |
|---|---|
| Address validation | Prevent incomplete or invalid delivery data |
| Tracking updates | Keep users informed on shipment status |
| Failure handling | Mark failed deliveries clearly and notify support |
| Return handling | Support return cases and dispute resolution |
| State accuracy | Order state must match real delivery state |

## User-Facing Statuses

| Status | Meaning |
|---|---|
| Pending shipment | Order is waiting to be handed off |
| In transit | Package is moving through logistics |
| Out for delivery | Package is near final delivery |
| Delivered | Package reached the customer |
| Delivery failed | Package could not be delivered |
| Returned | Package was sent back or reversed |

## Summary

Fulfillment must feel reliable and transparent so customers and sellers trust the marketplace.
