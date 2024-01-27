
# README.md for JSON-LD Implementation on /locations Page

## What is JSON-LD?

JSON-LD (JavaScript Object Notation for Linked Data) is a method of encoding linked data using JSON. It is widely used in web development to structure and link data in a way that is readable by search engines. This makes the content more discoverable and enhances SEO. JSON-LD is often used to provide additional context to search engines, enabling rich snippets in search results.

## Implementing JSON-LD on the /locations Page

The `/locations` page of the Austin Public Library website can use JSON-LD to provide structured information about different library locations and their operating hours. This will help in improving the visibility of the locations in search results and provide users with quick access to essential information.

### Example Implementation

1. **Central Library:**
   ```json
   {
     "@context": "https://schema.org",
     "@type": "Library",
     "name": "Central Library",
     "telephone": "+1-512-974-7400",
     "address": {
       "@type": "PostalAddress",
       "streetAddress": "710 W. César Chávez St.",
       "addressLocality": "Austin",
       "addressRegion": "TX",
       "postalCode": "78701"
     },
     "openingHoursSpecification": [
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Sunday", "opens": "12:00", "closes": "17:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Monday", "opens": "09:00", "closes": "20:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Tuesday", "opens": "09:00", "closes": "20:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Wednesday", "opens": "09:00", "closes": "20:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Thursday", "opens": "09:00", "closes": "20:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Friday", "opens": "09:00", "closes": "17:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Saturday", "opens": "10:00", "closes": "17:00"}
     ],
     "url": "https://library.austintexas.gov/central-library"
   }
   ```

2. **APL Shop:**
   ```json
   {
     "@context": "https://schema.org",
     "@type": "Store",
     "name": "APL Shop",
     "telephone": "+1-512-974-9676",
     "address": {
       "@type": "PostalAddress",
       "streetAddress": "710 W. César Chávez St., 2nd Floor",
       "addressLocality": "Austin",
       "addressRegion": "TX",
       "postalCode": "78701"
     },
     "openingHoursSpecification": [
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Sunday", "opens": "12:00", "closes": "17:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Monday", "opens": "10:00", "closes": "18:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Tuesday", "opens": "10:00", "closes": "18:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Wednesday", "opens": "10:00", "closes": "18:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Thursday", "opens": "10:00", "closes": "18:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Friday", "opens": "10:00", "closes": "17:00"},
       {"@type": "OpeningHoursSpecification", "dayOfWeek": "Saturday", "opens": "10:00", "closes": "17:00"}
     ],
     "url": "https://library.austintexas.gov/apl-shop"
   }
   ```

### Steps for Implementation:

1. **Create JSON-LD Blocks:** For each location, create a JSON-LD block with details such as name, address, contact number, opening hours, and URL.

2. **Insert JSON-LD in HTML:** Place the JSON-LD scripts in the HTML of the `/locations` page, preferably within the `<head>` tag or just before the closing `</body>` tag.

3. **Test the Implementation:** Use tools like Google's Structured Data Testing Tool to test and validate your JSON-LD implementation.

By following these steps, you can successfully implement JSON-LD on the `/locations` page, improving the discoverability and usability of the Austin Public Library's location information.
