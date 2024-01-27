
# README.md for JSON-LD Implementation: Event Example

## What is JSON-LD?

JSON-LD (JavaScript Object Notation for Linked Data) is a lightweight data-interchange format that is easy for humans to read and write, and easy for machines to parse and generate. It is based on the JavaScript Object Notation (JSON) but is used to represent structured data rather than just arbitrary data structures. This makes it ideal for embedding rich, structured data within web pages, which can then be used by search engines and other web services to better understand and display the content of the pages.

## Example Implementation for an Event

Consider the "Bilingual Gentle Yoga" event held at the Windsor Park Branch of the Austin Public Library. The JSON-LD structured data for this event would be as follows:

```json
{
  "@context": "https://schema.org",
  "@type": "Event",
  "name": "Bilingual Gentle Yoga",
  "description": "Holistic Wellness with the MACC. A gentle flow yoga session suitable for ages 8 and above, focusing on aligning body, mind, and soul through gentle movement guided by breath, including meditation.",
  "startDate": "2024-01-27T10:00",
  "endDate": "2024-01-27T12:00",
  "eventStatus": "https://schema.org/EventScheduled",
  "eventAttendanceMode": "https://schema.org/OfflineEventAttendanceMode",
  "location": {
    "@type": "Place",
    "name": "Windsor Park Branch",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "5833 Westminster Dr.",
      "addressLocality": "Austin",
      "addressRegion": "TX"
    }
  },
  "organizer": {
    "@type": "Organization",
    "name": "Austin Public Library",
    "url": "https://library.austintexas.gov"
  },
  "isAccessibleForFree": true,
  "inLanguage": "English/Spanish"
}
```

### Steps for Implementation:

1. **Create JSON-LD Block:** Construct a JSON-LD script with detailed information about the event such as name, description, dates, location, and organizer.

2. **Insert JSON-LD in HTML:** Embed this script within the HTML of the event page, ideally within the `<head>` section or just before the closing `</body>` tag.

3. **Validate the JSON-LD:** Use tools like Google's Structured Data Testing Tool to ensure the JSON-LD is correctly formatted and the data is accurate.

By following these steps, you can enhance the discoverability and presentation of your event in search engine results, thereby improving user engagement and attendance.
