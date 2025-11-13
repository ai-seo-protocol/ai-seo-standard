# AI-SEO Protocol — Open Standard v1.0

The **AI-SEO Protocol** is the first open standard designed to make websites readable, interpretable, and directly usable by Artificial Intelligence systems (LLMs, AI Agents, RAG pipelines, autonomous crawlers).

This repository contains the official specification, JSON schema, examples, validator, and crawler defining the AI-SEO Protocol.

---

## 🚀 Purpose

The AI-SEO Protocol provides a unified, machine-readable format that allows websites to declare structured knowledge explicitly for AI systems.

It enables AIs to:

- understand website content without ambiguity  
- retrieve real-time structured data  
- integrate knowledge into responses  
- use websites as authoritative sources  

Traditional SEO was designed for search engines.  
AI-SEO is designed for AI.

---

## 📘 Documentation

- **SPECIFICATION.md** — Full technical standard  
- **schema.json** — JSON Schema for validation  
- **examples/** — Example AI-SEO documents  
- **validator/** — Python validator  
- **crawler/** — AI-SEO crawler  

---

## 📂 Repository Structure

```
ai-seo-standard/
├── README.md
├── SPECIFICATION.md
├── schema.json
├── examples/
│   ├── winery.json
│   ├── company.json
│   ├── product.json
│   └── person.json
├── validator/
│   └── validate.py
└── crawler/
    └── ai_seo_crawler.py
```

---

## 🧩 What is an AI-SEO Document?

An AI-SEO document is a JSON definition that a website publishes to expose structured knowledge to Artificial Intelligence systems.

Example:

```json
{
  "ai-seo-version": "1.0",
  "entity-type": "company",
  "metadata": {
    "domain": "example.com",
    "lastUpdate": "2025-01-01T00:00:00Z"
  },
  "data": {
    "name": "Example Company"
  }
}
```

---

## 🌍 Official Website  
https://ai-seo-protocol.org

---

## 📝 License  
Open Standard — free to use, implement, and extend.
