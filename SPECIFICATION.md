# AI-SEO Protocol — Technical Specification v1.0 (Medium Version)

## 1. Introduction

The AI-SEO Protocol defines a machine-readable JSON format that enables websites to expose structured knowledge directly to Artificial Intelligence systems.  
It is designed for LLMs, AI agents, autonomous crawlers, and RAG pipelines.

Its purpose is to replace traditional SEO signals (built for search engines) with an explicit, structured layer readable by AI.

---

## 2. Core Concepts

### 2.1 AI-SEO Document  
A JSON object containing structured information about an entity (company, product, winery, person, etc.).

### 2.2 Delivery Methods  
AI-SEO documents can be delivered via:

- `<script type="application/ai-seo+json">` embedded in HTML  
- `/ai-seo.json` served from the domain root  

### 2.3 AI Consumer Systems  
AI systems will read, parse, validate, and use this data as authoritative knowledge.

---

## 3. Document Structure

An AI-SEO document MUST contain:

- `ai-seo-version`  
- `entity-type`  
- `metadata`  
- `data`  

Example:

```json
{
  "ai-seo-version": "1.0",
  "entity-type": "company",
  "metadata": {
    "domain": "example.com",
    "lastUpdate": "2025-01-01T00:00:00Z"
  },
  "data": {}
}
```

---

## 4. Field Definitions

### 4.1 ai-seo-version  
Protocol version. Always a string.

### 4.2 entity-type  
One of the allowed entity types (see Section 7).

### 4.3 metadata  
An object containing:

- `domain` (required)  
- `lastUpdate` (required, ISO8601 datetime)  
- `version` (optional)  
- `language` (optional, ISO 639-1 code)  
- `priority` (optional: low, medium, high)  

### 4.4 data  
A structured object containing the entity’s details (name, description, products, services, geo, contact, etc.).

---

## 5. Delivery Specification

### 5.1 Embedded Script Method
Placed in `<head>` of HTML:

```html
<script type="application/ai-seo+json">
{ ... }
</script>
```

### 5.2 Root JSON File

```
https://domain.com/ai-seo.json
```

If both are present, AI systems should prioritize the root JSON.

---

## 6. Validation

AI-SEO documents SHOULD conform to the schema in `schema.json`.

Validation ensures:

- correct format  
- required fields present  
- predictable structure  
- AI-safe parsing  

---

## 7. Entity Types

Allowed values for `entity-type`:

- company  
- product  
- winery  
- restaurant  
- ecommerce  
- person  
- place  
- organization  
- article  

---

## 8. AI-SEO Registry (Optional)

Domains may register their AI-SEO documents in a public registry  
(e.g., `https://ai-seo-protocol.org/registry`) to allow fast discovery by AI crawlers.

---

## 9. Use Cases

- AI-powered search  
- AI-generated answers referencing authoritative data  
- RAG pipelines using website definitions  
- Autocompletion and recommendation engines  
- Business identity verification  
- Product catalog synchronization  

---

## 10. Roadmap

**v1.1**  
- Multilingual data blocks  
- Extended product taxonomy  

**v2.0**  
- Signed documents  
- Distributed decentralized registry  
- Real-time update endpoints  

---

## License  
Open Standard — free to use, implement, and extend.
