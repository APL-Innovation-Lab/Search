
# README.md for Organization and Library Schema Implementation

## Organization Schema

The Organization schema is used to provide detailed information about an organization, such as the Austin Public Library system. It helps search engines and other web services understand key details about the organization.

### Fields and Example for Austin Public Library

- **@type:** "Organization"
- **name:** "Austin Public Library"
- **url:** "https://library.austintexas.gov"
- **logo:** URL to the library's logo
- **contactPoint:** 
  - **@type:** "ContactPoint"
  - **telephone:** "+1-512-974-7400"
  - **contactType:** "customer service"
- **address:** 
  - **@type:** "PostalAddress"
  - **streetAddress:** "710 W. César Chávez St."
  - **addressLocality:** "Austin"
  - **addressRegion:** "TX"
  - **postalCode:** "78701"
- **sameAs:** URLs to social media or other online profiles
- **founder:** "Founder's Name"
- **foundingDate:** "YYYY-MM-DD"
- **employee:** Details about notable employees

### Library Schema

The Library schema is a subtype of the Organization schema, specifically tailored for libraries. It includes additional details specific to library services and facilities.

### Fields and Example for a Branch of Austin Public Library

- **@type:** "Library"
- **parentOrganization:** Reference to the Austin Public Library as the parent organization
- **name:** "Central Library"
- **url:** "https://library.austintexas.gov/central-library"
- **address:** 
  - **@type:** "PostalAddress"
  - **streetAddress:** "710 W. César Chávez St."
  - **addressLocality:** "Austin"
  - **addressRegion:** "TX"
  - **postalCode:** "78701"
- **telephone:** "+1-512-974-7400"
- **openingHours:** "Mo, Tu, We, Th, Fr, Sa, Su 09:00-21:00"
- **containsPlace:** Include details of any specific sections within the library, like a children's area or study rooms
- **event:** Reference to events held at the library
- **smokingAllowed:** Whether smoking is allowed (typically false for libraries)
- **publicAccess:** If the library is open to the public

By implementing these schemas on the Austin Public Library website, each library branch's webpage can be enriched with structured data, making it easier for search engines to understand and display information about the library in search results. This enhances the online presence and discoverability of the library and its branches.
