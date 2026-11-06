# AtithiFusion — Luxury Hospitality Portal & Conversational AI Concierge

[![AWS CloudFront](https://img.shields.io/badge/AWS-CloudFront%20%7C%20Amplify-FF9900?logo=amazon-aws&logoColor=white)](#aws-cloud-architecture)
[![UI System](https://img.shields.io/badge/Design-Luxury%20Editorial%20Grid-0052CC)](#design-system)
[![Branch Status](https://img.shields.io/badge/Preservation-Ex%20Branch-22C55E)](#branch-architecture)
[![License: MIT](https://img.shields.io/badge/License-MIT-gray.svg)](LICENSE)

> Responsive hospitality marketplace featuring real-time property listings, booking workflows, and an intelligent budget-aware reservation assistant.

---

## 1. Executive Brief
Modern vacation rental experiences demand frictionless search and instant conversational assistance. **AtithiFusion** pairs an editorial luxury grid layout with an embedded AI concierge capable of answering property queries, recommending local itineraries, and filtering listings by dynamic budgetary constraints.

* **Preservation**: Original Airbnb clone baseline preserved on [`Ex`](https://github.com/prak05/AtithiFusion-Hospitality-Portal/tree/Ex).
* **Architecture**: CloudFront + S3 static hosting, ECS Fargate backend, and Amazon Bedrock concierge agent.

---

## 2. AWS Cloud Architecture

```mermaid
flowchart TD
    Guest["Guest Browser / Mobile"] --> CloudFront["Amazon CloudFront (Edge CDN)"]
    CloudFront --> S3["Amazon S3 (Static Web Assets)"]
    Guest --> APIGW["Amazon API Gateway"]
    APIGW --> LambdaAuth["Amazon Cognito / Auth Lambda"]
    APIGW --> ECS["AWS ECS Fargate (Booking & Catalog Microservice)"]
    ECS --> Aurora["Amazon Aurora Serverless (PostgreSQL)"]
    Guest --> ChatWS["API Gateway WebSocket (Concierge Chat)"]
    ChatWS --> Bedrock["Amazon Bedrock (Claude 3.5 Sonnet Concierge)"]
```

---

## 3. Branch Architecture
* [`main`](https://github.com/prak05/AtithiFusion-Hospitality-Portal/tree/main): Modernized hospitality portal with CloudFront CDN and Bedrock agent.
* [`Ex`](https://github.com/prak05/AtithiFusion-Hospitality-Portal/tree/Ex): Preserved original frontend baseline.

<!-- antigravity-certified -->
