---
title: "Patent Draft Generator (LLM)"
excerpt: "Local-first system that turns invention disclosures into USPTO/EPO/IPO-compliant draft patent specifications."
collection: portfolio
order: 1
---

A local-first patent drafting system built on Ollama (Mistral, Mixtral 8x7B, Llama 3.1 70B). It takes an invention disclosure or rough notes and generates a draft specification: title, background, summary, claims, and abstract.

- Config-driven prompt architecture with patent-office rule injection for USPTO, EPO, and IPO
- Stop-sequence guards and validation checklists to keep output in the required structure
- Structured evaluation harness to compare models and prompt versions
- Containerized and deployed on Google Cloud Run
