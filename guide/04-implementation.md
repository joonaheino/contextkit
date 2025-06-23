# Step-by-Step Guide to llms.txt Implementation

This guide provides a practical, step-by-step process for implementing `llms.txt` on your website. Following these steps will ensure that AI systems can find and accurately interpret your curated content.

## Prerequisites

Before you begin, ensure you have:
1.  The ability to upload files to your website's root directory.
2.  The ability to edit your website's `robots.txt` file.

## Step 1: Create Your Core `llms.txt` File

This is the central file that AI crawlers will look for. Create a new text file named `llms.txt`.

### File Content and Structure

Start with the most critical information first. Structure the file using Markdown for clarity.

```markdown
# Your Company Name
> A clear, one-sentence summary of your business. Example: "We sell high-quality, ethically-sourced coffee beans directly to consumers."

This section should expand on your value proposition, target audience, and what makes you unique. Keep it concise and factual.

## Key Products
- [Product A](https://yourdomain.com/product-a.md): Description of what Product A is and who it's for.
- [Product B](https://yourdomain.com/product-b.md): Description of what Product B is and its main benefit.

## About Us
- [Our Story](https://yourdomain.com/about.md): Your company's mission and background.

## Contact
- [Contact Page](https://yourdomain.com/contact.md): How customers can reach you for support or sales.
```

**Key Considerations:**
-   **Token Limit:** Aim to keep `llms.txt` under 8,000 tokens (approx. 6,000 words).
-   **Hierarchy:** Place the most essential information at the top.
-   **Clarity over Marketing:** Use direct, factual language. Instead of "world-class solutions," write "software that automates invoicing."

## Step 2: Create Markdown Versions of Key Pages

For each URL you linked in `llms.txt`, create a corresponding `.md` file.

For example, for a page at `https://yourdomain.com/product-a`, you will create a file accessible at `https://yourdomain.com/product-a.md`.

### Markdown File Best Practices

-   **Clean and Simple:** These files should contain only essential text content. Remove all HTML, navigation, footers, and sidebars.
-   **Structured Text:** Use Markdown headings, lists, and bold text to create a clear hierarchy.
-   **Token Limits:** Keep individual `.md` files between 1,000-2,000 tokens.
-   **Absolute URLs:** Ensure all links within your markdown files are absolute (e.g., `https://yourdomain.com/page` not `/page`).

## Step 3: Configure Your `robots.txt`

You need to update your `robots.txt` file to tell AI crawlers where to find your new files, while preventing traditional search engines from indexing them (which can be seen as duplicative content).

Add the following block to your `robots.txt` file:

```
# Allow all crawlers general access
User-agent: *
Allow: /

# Specifically guide AI crawlers
User-agent: GPTBot
Allow: /llms.txt
Allow: /llms-full.txt
Allow: /*.md$

User-agent: Google-Extended
Disallow: /llms.txt
Disallow: /llms-full.txt
Disallow: /*.md$

# Add other AI crawlers as they emerge
```
*Note: `Google-Extended` is the user agent for Google's future generative AI models. Blocking it from the `.txt` and `.md` files is the current best practice.*

## Step 4: Test Your Implementation

Once your files are live, you must test to ensure they are working as expected.

### Manual Checks
1.  **Accessibility:** Can you access `https://yourdomain.com/llms.txt` and your `.md` files in a browser?
2.  **Readability:** Is the content easy for a human to read and understand?
3.  **Accuracy:** Is all the information (pricing, features, contact info) correct?

### AI Testing
Engage with various AI models (ChatGPT, Claude, Perplexity, etc.) and ask them questions about your business:
-   "Tell me about [Your Company]."
-   "What are the main products offered by [Your Company]?"
-   "How much does [Your Product] cost?"
-   "How can I contact [Your Company]?"

The goal is to see if the AI's answers reflect the curated information in your `llms.txt` files rather than guessing from your main website.

## Advanced Implementation

### Multi-Language
For international sites, create language-specific files. Use standard language codes in the filenames:
-   `/llms-es.txt` (Spanish)
-   `/llms-fr.txt` (French)
-   `/llms-de.txt` (German)

Ensure the content within these files is professionally translated and culturally adapted.

### Version Control
As your business changes, your `llms.txt` will need updates. Consider an archiving system to track changes:
-   `/llms.txt` (The current, live version)
-   `/llms-2024-06.txt` (An archived version from June 2024)

This helps in monitoring how changes affect AI responses over time.

---

[Continue to: Content Curation Strategies →](05-content-curation.md)

*This guide is part of the comprehensive llms.txt resource provided by [ContextKit](https://contextkit.io) - professional llms.txt creation for businesses worldwide.* 