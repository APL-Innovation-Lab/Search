
# README.md for JSON-LD Breadcrumbs Implementation: Event Page Example

## Implementing JSON-LD for Breadcrumbs

Breadcrumbs provide a clear path for users to follow back to the homepage and help search engines understand the structure of a website. JSON-LD structured data for breadcrumbs enhances this by providing search engines with explicit breadcrumb information.

### Example for "Bilingual Gentle Yoga" Event Page

The URL "https://library.austintexas.gov/event/health-wellness/bilingual-gentle-yoga-7738198" represents the "Bilingual Gentle Yoga" event. The breadcrumb path is: Home > Events > Bilingual Gentle Yoga.

Here's the JSON-LD structured data for these breadcrumbs:

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://library.austintexas.gov"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Events",
      "item": "https://library.austintexas.gov/events"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Bilingual Gentle Yoga",
      "item": "https://library.austintexas.gov/event/health-wellness/bilingual-gentle-yoga-7738198"
    }
  ]
}
```

### Steps for Implementation:

1. **Create JSON-LD Block:** Construct a JSON-LD script for the breadcrumb trail, including each step from the homepage to the current page.

2. **Insert JSON-LD in HTML:** Embed this script within the HTML of the event page, ideally within the `<head>` section or just before the closing `</body>` tag.

3. **Validate the JSON-LD:** Use tools like Google's Structured Data Testing Tool to ensure the JSON-LD is correctly formatted and the data is accurate.

By following these steps, the breadcrumb path of your event pages will be clearly communicated to search engines, improving site navigation and search engine visibility.
