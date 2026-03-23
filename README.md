# KeepRule Investment Principles API

Free, open-source API serving curated investment wisdom from the world's greatest investors — Warren Buffett, Charlie Munger, Benjamin Graham, Peter Lynch, Howard Marks, Ray Dalio, and more.

**Powered by [KeepRule](https://keeprule.com)** — Your guide to timeless investment principles.

## API Endpoints

All endpoints are static JSON files hosted on GitHub Pages. No authentication required.

| Endpoint | Description |
|----------|-------------|
| [`/api/principles.json`](https://henu-wang.github.io/keeprule-api/api/principles.json) | 100 investment principles with author, category & source |
| [`/api/authors.json`](https://henu-wang.github.io/keeprule-api/api/authors.json) | List of all investment masters |
| [`/api/categories.json`](https://henu-wang.github.io/keeprule-api/api/categories.json) | Investment principle categories |

**Base URL:** `https://henu-wang.github.io/keeprule-api`

## Data Format

### Principles

```json
{
  "total": 100,
  "source": "https://keeprule.com",
  "principles": [
    {
      "id": 1,
      "text": "Rule No. 1: Never lose money. Rule No. 2: Never forget Rule No. 1.",
      "author": "Warren Buffett",
      "category": "Risk Management",
      "source": "Berkshire Hathaway Annual Meeting"
    }
  ]
}
```

### Authors

```json
{
  "total": 18,
  "authors": [
    {
      "id": 1,
      "name": "Warren Buffett",
      "title": "Chairman & CEO, Berkshire Hathaway",
      "known_for": "Value Investing, Long-term Holding",
      "principles_count": 20
    }
  ]
}
```

### Categories

```json
{
  "total": 13,
  "categories": [
    {
      "id": 1,
      "name": "Risk Management",
      "description": "Principles about identifying, assessing, and mitigating investment risks",
      "principles_count": 14
    }
  ]
}
```

## Usage Examples

### cURL

```bash
# Get all principles
curl https://henu-wang.github.io/keeprule-api/api/principles.json

# Get authors
curl https://henu-wang.github.io/keeprule-api/api/authors.json

# Get categories
curl https://henu-wang.github.io/keeprule-api/api/categories.json
```

### JavaScript

```javascript
// Fetch all investment principles
const response = await fetch('https://henu-wang.github.io/keeprule-api/api/principles.json');
const data = await response.json();

// Get a random principle
const random = data.principles[Math.floor(Math.random() * data.total)];
console.log(`"${random.text}" — ${random.author}`);

// Filter by author
const buffett = data.principles.filter(p => p.author === 'Warren Buffett');
console.log(`Found ${buffett.length} Buffett principles`);

// Filter by category
const risk = data.principles.filter(p => p.category === 'Risk Management');
console.log(`Found ${risk.length} risk management principles`);
```

### Python

```python
import requests
import random

# Fetch all principles
response = requests.get('https://henu-wang.github.io/keeprule-api/api/principles.json')
data = response.json()

# Random principle
principle = random.choice(data['principles'])
print(f'"{principle["text"]}" — {principle["author"]}')

# Filter by author
munger = [p for p in data['principles'] if p['author'] == 'Charlie Munger']
print(f'Found {len(munger)} Munger principles')
```

## Featured Investors

| Investor | Principles | Known For |
|----------|-----------|-----------|
| Warren Buffett | 20 | Value Investing, Long-term Holding |
| Charlie Munger | 13 | Mental Models, Multidisciplinary Thinking |
| Benjamin Graham | 10 | Margin of Safety, Security Analysis |
| Peter Lynch | 10 | Invest in What You Know |
| Howard Marks | 10 | Second-Level Thinking |
| Ray Dalio | 10 | Principles-Based Investing |
| Philip Fisher | 7 | Growth Investing, Scuttlebutt Method |
| John Templeton | 4 | Global Contrarian Investing |
| + 10 more | ... | ... |

## Categories

Risk Management, Value Investing, Market Psychology, Long-term Thinking, Mental Models, Decision Making, Circle of Competence, Portfolio Management, Business Quality, Self-improvement, Contrarian Thinking, Research, Compounding

## About KeepRule

[KeepRule](https://keeprule.com) is an interactive platform for exploring investment principles from the world's greatest investors. Features include:

- Scenario-based learning with real-world investment situations
- Principles organized by master investor and category
- AI-powered investment wisdom chat

## License

This API is free to use for personal and commercial projects. Attribution to [KeepRule](https://keeprule.com) is appreciated but not required.

Data is provided for educational purposes only and does not constitute financial advice.
