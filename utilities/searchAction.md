
# README.md for SearchAction Schema Implementation

## SearchAction Schema Overview

The SearchAction schema is a part of the Schema.org vocabulary that enables webmasters to indicate to search engines that their website has an internal search function. This structured data helps search engines understand how the search feature on the site operates and can enable direct search functionalities from the search engine results page.

## Implementing SearchAction for Austin Public Library

### Purpose
- To enhance the user experience by allowing users to perform searches on the Austin Public Library website directly from search engines.

### Example Implementation

Consider the search functionality on the Austin Public Library website. The URL "https://library.austintexas.gov/search-website?search=Online%20payment" represents a search query for "Online payment". Here's how you can implement the SearchAction schema for this feature:

```json
{
  "@context": "http://schema.org",
  "@type": "WebSite",
  "url": "https://library.austintexas.gov/",
  "potentialAction": {
    "@type": "SearchAction",
    "target": "https://library.austintexas.gov/search-website?search={search_term_string}",
    "query-input": "required name=search_term_string"
  }
}
```

In this JSON-LD script:
- **@type:** Specifies that the structured data is about a website with a search action capability.
- **target:** Contains the URL template that leads to the search results page. `{search_term_string}` is a placeholder that gets replaced by the actual search query.
- **query-input:** Defines how the search query is accepted, indicating that the query string is a required part of the search.

### Steps for Implementation

1. **Create JSON-LD Block:** Write the JSON-LD script with details for the SearchAction, including the target URL structure and query-input specifications.

2. **Insert JSON-LD in HTML:** Embed this script within the HTML of the website, ideally in the `<head>` section.

3. **Validate the JSON-LD:** Use tools like Google's Structured Data Testing Tool to validate the format and correctness of the JSON-LD script.

By properly implementing the SearchAction schema, the Austin Public Library can improve user experience by enabling direct searches from search engines, making it easier for users to find specific information on the library's website.
