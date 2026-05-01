# 🚀 Nexus Agent: Multi-Model Automated Code Reviewer

![Version](https://img.shields.io/badge/version-2.1.0--beta-blue.svg)
![Status](https://img.shields.io/badge/status-Enterprise_Core-orange.svg)
![Token Consumption](https://img.shields.io/badge/Token_Usage-~10M%2FDay-red.svg)
![Models](https://img.shields.io/badge/Models-Gemini%20|%20DeepSeek%20|%20GPT4o-success.svg)

> **Notice:** This repository contains the public facing documentation and the core architectural orchestrator for the **Nexus Agent System**. The underlying proprietary rule-engine and enterprise data-connectors remain in the private enterprise repository.

## 🎯 Overview

**Nexus Agent** is an enterprise-grade, Multi-Agent collaborative system designed to solve the critical pain points of scaling microservice architectures: **technical debt accumulation and inefficient manual code reviews.** 

By orchestrating massive-context models (Gemini 1.5 Pro) with reasoning-optimized models (DeepSeek-Coder / GPT-4o), Nexus performs autonomous codebase mapping, deep vulnerability hunting, and automated patch generation via Chain-of-Thought (CoT).

## 🧠 Multi-Agent Architecture

```mermaid
graph TD
    A[GitLab/GitHub Enterprise] -->|Webhook: Push/PR| B(Agent A: Architect)
    B -->|Context Vectorization & Topology Mapping <br> 1M+ Tokens/Run| C{Context DB & Cache}
    
    C --> D(Agent B: Vulnerability Hunter)
    D -->|CoT Reasoning via DeepSeek/GPT-4o| E{Technical Debt or Bug Found?}
    
    E -->|Yes| F(Agent C: Auto-Fix & Refactor)
    E -->|No| G[Terminate Pipeline]
    
    F -->|Generate Patch & Unit Tests| H[Sandboxed CI/CD Pipeline]
    H -->|Tests Failed| F
    H -->|Tests Passed| I[Auto-Commit & Open PR <br> w/ Bilingual Report]
    
    style B fill:#1e1e2f,stroke:#03a9f4,stroke-width:2px,color:#fff
    style D fill:#1e1e2f,stroke:#ff9800,stroke-width:2px,color:#fff
    style F fill:#1e1e2f,stroke:#4caf50,stroke-width:2px,color:#fff
