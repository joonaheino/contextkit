# The llms.txt Technical Specification

## Understanding the Standard

The llms.txt specification was created by Jeremy Howard at [llmstxt.org](https://llmstxt.org) to address a fundamental problem: **how can Large Language Models efficiently understand websites?**

## Core Components

### 1. The Main llms.txt File

Located at your domain root (`https://yoursite.com/llms.txt`), this file serves as the **instruction manual for AI systems**.

**Basic Structure:**
```markdown
# Your Company Name

> Brief, compelling summary of what you do and why it matters

Additional context, key differentiators, and instructions for AI systems.

## Products/Services
- [Product Name](url): Clear description of what it does and for whom
- [Another Product](url): Concise explanation with key benefits

## About
- [Company Story](url): Background, mission, founding story
- [Leadership Team](url): Key executives and their backgrounds

## Support
- [Contact Information](url): How to reach you
- [Documentation](url): Technical resources
```

### 2. Markdown Versions of Key Pages
For each important page, create a clean markdown version accessible by appending .md to the URL:

`https://yoursite.com/products/widget.md`
`https://yoursite.com/about/team.md`
`https://yoursite.com/pricing.md`

These contain LLM-optimized versions of your pages - clean, structured, and focused on essential information.

### 3. Optional: llms-full.txt
For AI systems with larger context windows (100k+ tokens), you can provide a comprehensive version:
```markdown
# Complete Business Information

[Expanded content with more detail, additional products, comprehensive FAQ, etc.]
```
## Technical Requirements
### Token Limits

- `llms.txt`: ~8,000 tokens per language (roughly 6,000 words)
- Individual `.md` files: 1,000-2,000 tokens each
- `llms-full.txt`: Up to 100,000 tokens

### Format Standards

- Markdown only (no HTML, rich formatting, or images)
- UTF-8 encoding
- Clear hierarchical structure with proper headers
- Absolute URLs for all links

### robots.txt Integration
Guide AI crawlers to your context files while keeping them hidden from traditional search:
```
User-agent: *
Allow: /

User-agent: GPTBot
Allow: /llms.txt
Allow: /llms-full.txt
Allow: /*.md$

User-agent: Google-Extended
Disallow: /llms.txt
Disallow: /llms-full.txt
Disallow: /*.md$
```

## Content Architecture Best Practices
### Information Hierarchy
Structure your llms.txt with clear priorities:

**1. Essential Business Info (first 500 tokens)**

- What you do
- Primary value proposition
- Target audience

**2. Key Products/Services (next 2,000 tokens)**

- Core offerings
- Pricing (if public)
- Key differentiators

**3. Supporting Information (remaining tokens)**

- Company background
- Contact details
- Additional resources

### Markdown Optimization
Effective Structure:
```markdown
# Product Name

> One-sentence value proposition

## What It Does
Clear, jargon-free explanation of functionality.

## Who It's For
Specific target audience and use cases.

## Key Features
- Feature 1: Specific benefit
- Feature 2: Measurable outcome
- Feature 3: Unique advantage

## Pricing
Transparent, up-to-date pricing information.

## Getting Started
Clear next steps for interested prospects.
```
Avoid:

- Complex HTML tables
- Image-dependent content
- Marketing fluff without substance
- Broken or relative links
- Outdated information

### Multi-Language Implementation
For international businesses:
- `/llms.txt` (English - default)
- `/llms-es.txt` (Spanish)
- `/llms-fr.txt` (French)
- `/llms-de.txt` (German)

Each language file should be:

- Fully translated (not just machine-translated)
- Culturally adapted
- Locally relevant (regional pricing, contact info, etc.)

### Version Control and Updates
#### File Naming for Updates
- `/llms.txt` (current version)
- `/llms-2024-01.txt` (archived version)
- `/llms-2024-02.txt` (archived version)

#### Change Tracking
Monitor what information AI systems are accessing:

- Server logs for `llms.txt` requests
- Analytics on `.md` file access
- Regular AI testing of your brand

## Common Implementation Mistakes
### 1. Information Overload
- **Wrong**: Trying to fit your entire website into `llms.txt`
- **Right**: Curating the most essential information that drives business outcomes

### 2. Marketing Speak
- **Wrong**: "Revolutionary solutions that transform businesses"
- **Right**: "Project management software that reduces planning time by 40%"

### 3. Technical Jargon
- **Wrong**: "Leverages advanced algorithms for optimization"
- **Right**: "Automatically schedules your team's tasks to meet deadlines"

### 4. Outdated Information
- **Wrong**: Last updated 6 months ago
- **Right**: Regular updates as business evolves

### 5. Poor Structure
- **Wrong**: Wall of text without clear sections
- **Right**: Hierarchical markdown with clear headers

## Testing Your Implementation
### Manual Testing

- **Readability**: Can a human quickly understand your business?
- **Completeness**: Are key questions answered?
- **Accuracy**: Is all information current and correct?
- **Token Count**: Are you within limits?

### AI Testing
Ask various AI systems about your business:

- "Tell me about [Your Company]"
- "What does [Your Company] cost?"
- "How do I contact [Your Company]?"
- "What are [Your Company]'s main products?"

## Integration with Existing Systems
### CMS Integration
Most content management systems can serve static files:

- **WordPress**: Add files to root directory
- **Shopify**: Use the Files section
- **Custom CMS**: Configure routing for `.txt` and `.md` files

### CDN Considerations
Ensure your CDN serves `llms.txt` files with appropriate headers:
- `Content-Type: text/plain; charset=utf-8`
- `Cache-Control: public, max-age=3600`

## Next Steps
Now that you understand the technical specification, let's explore the real business impact of proper llms.txt implementation.

[Continue to: Business Impact →](03-business-impact.md)

---
*Need professional implementation? ContextKit creates production-ready llms.txt files with expert curation and human oversight.* 