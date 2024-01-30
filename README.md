# Search


# Search Configuration for library.austintexas.gov

## Overview
This document provides a detailed overview of the Drupal Search API configuration for the library.austintexas.gov website.

## Drupal Index View Configuration Summary

- **Index Status**: Fully indexed with a total count of items mentioned.
- **Status**: The index is currently enabled.
- **Datasources**: Both "Content" and "Taxonomy term" datasources are fully indexed.
- **Tracker**: Set to the default tracking method.
- **Server**: Utilizing the Drupal server for indexing.
- **Server Index Status**: A specific number of items are indexed on the server for this index.
- **Cron Batch Size**: Configured to index 50 items per cron run.


### Content Types Indexed
- AHC Page
- News
- Digital Resource
- Event
- Exhibit
- Keyword Match
- Page
- Staff Recommend

### Taxonomies Indexed
- Recommend Tags
- Digital Resource Subjects
- Event Categories
- Library Location


### Fields Indexed

| Label                | Machine Name       | Property Path       | Type     | Boost |
|----------------------|--------------------|---------------------|----------|-------|
| Aggregated field     | aggregated_field   | aggregated_field    | Fulltext | 21.00 |
| Rendered HTML output | rendered_item      | rendered_item       | Fulltext | 21.00 |
| Audience             | field_sd_audience  | field_sd_audience   | String   |       |
| Body                 | body               | body                | Fulltext | 1.00  |
| Body (Top)           | field_body_top     | field_body_top      | Fulltext | 1.00  |
| Content type         | type               | type                | String   |       |
| Do not index         | field_do_not_index | field_do_not_index  | Boolean  |       |
| Language             | langcode           | langcode            | String   |       |
| Product Names        | field_product_names| field_product_names | String   |       |
| Published            | status             | status              | Boolean  |       |
| Recommend Tags       | field_recommend_tags| field_recommend_tags| String   |       |
| Searchable           | field_searchable   | field_searchable    | Fulltext | 21.00 |
| Search Terms         | field_search_terms | field_search_terms  | String   |       |
| Time Start           | field_sr_time_start| field_sr_time_start | Date     |       |
| Title                | title              | title               | Fulltext | 21.00 |
| URL for Match        | field_url_for_match| field_url_for_match | Fulltext | 21.00 |
| Description          | description        | description         | Fulltext | 0.10  |
| Do not index         | field_do_not_index | field_do_not_index  | Boolean  |       |
| Language             | langcode           | langcode            | String   |       |
| Name                 | name               | name                | Fulltext | 21.00 |
| Vocabulary           | vid                | vid                 | String   |       |


### Processor Configurations
The following processor settings are enabled in the Drupal Search API:

- **Content access**: (not checked).
- **Entity status**: Checked.
- **Highlight**: (not checked).
- **HTML filter**: (not checked).
- **Ignore case**: Checked.
- **Ignore characters**: Checked.
- **Index hierarchy**: (not checked).
- **Number field-based boosting**: (not checked).
- **Reverse entity references**: Checked.
- **Role-based access**: (not checked).
- **Stemmer**: (not checked).
- **Stopwords**: (not checked).
- **Tokenizer**: Checked.
- **Transliteration**: Checked.
- **Type-specific Boosting**: Checked.

### Processor Order
- **Preprocess Index**: Ignore case, Transliteration, Ignore characters, Tokenizer, Type-specific boosting.
- **Preprocess Query**: Ignore case, Transliteration, Ignore characters, Tokenizer.
- **Postprocess Query**: (Not shown in the screenshot).

### Processor Settings
- **Ignore Case**: Enabled on all supported fields.
- **Transliteration**: Enabled on all supported fields.
- **Tokenizer**: Enabled, with a minimum word length to index set at 3 characters.
- **Type-specific Boosting**: Enabled with specific boosts for content bundles like Event, Keyword Match, and others.


### Additional Configurations
## Ignore Case Setting

The "Ignore Case" processor is enabled, applying case-insensitive search across all supported fields. This ensures that the search functionality is not affected by the case of the text entered into the search field. Additionally, this setting is dynamic and will automatically apply to new fields as they are supported by the index.

## Ignore Characters Processor Configuration

The following character properties are currently selected to be ignored:
- Punctuation, Other Characters
- Punctuation, Dash Characters
- Punctuation, Open Characters
- Punctuation, Close Characters
- Punctuation, Final quote Characters
- Punctuation, Initial quote Characters
- Punctuation, Other Characters

The character properties not currently selected but available for consideration are:
- Letter, Modifier Characters
- Letter, Other Characters
- Mark, Spacing Combining Characters
- Mark, Enclosing Characters
- Mark, Nonspacing Characters
- Number, Decimal Digit Characters
- Number, Letter Characters
- Number, Other Characters
- Separator, Line Characters
- Separator, Paragraph Characters
- Other, Control Characters
- Other, Format Characters
- Other, Private Use Characters
- Other, Surrogate Characters
- Other, Not Assigned (no characters in the file have this property)

## Tokenizer Processor Configuration

- **Ignore Case**: Enabled for all supported fields to ensure case-insensitive search.
- **Ignored Characters**: Custom characters to be ignored are not specified (defaults are used).
- **Whitespace Characters**: Default whitespace characters are used as word-delimiters.
- **Simple CJK Handling**: Enabled for overlapping sequences in Chinese, Japanese, and Korean text.
- **Minimum Word Length to Index**: Set to 3, meaning words with fewer than three characters will not be indexed.

These settings determine how text is tokenized and indexed, affecting the granularity and precision of search results.

## Transliteration Processor Configuration

- **Transliteration**: Enabled for all supported fields. This processor converts characters from various scripts into Latin characters, which can greatly assist in normalizing text for indexing and searching. This automatic feature ensures that all current and future supported fields benefit from this setting.

## Type-specific boosting

## Boost Settings for Content

| Bundle                  | Boost Value |
|-------------------------|-------------|
| Default (all items)     | 1.00        |
| AHC Page Bundle         | Default     |
| Article Bundle          | Default     |
| Digital Resource Bundle | 13.00       |
| Event Bundle            | 21.00       |
| Exhibit Bundle          | Default     |
| Keyword Match Bundle    | 21.00       |
| Basic Page Bundle       | Default     |
| Page Bundle             | Default     |
| Staff Recommend Bundle  | Default     |

## Boost Settings for Taxonomy Term

| Bundle                         | Boost Value |
|--------------------------------|-------------|
| Default (all items)            | 1.00        |
| Recommend Tags Bundle          | Default     |
| Digital Resource Subjects Bundle | 13.00     |
| Event Categories Bundle        | 21.00       |
| Library Location Bundle        | 13.00       |




### Upcoming Faceted Navigation
Plans are in place to introduce faceted navigation to enhance search capabilities. This will involve adding specific facets based on the content types and taxonomies indexed.

### Notes
- The detailed configuration information is based on the analysis of the provided HTML files.
- Manual review of the full content of these files is recommended for complete understanding.



# Drupal Search Facets Setup Guide

This guide provides step-by-step instructions on how to add facets to your Drupal search, specifically focusing on facets by content type displayed as horizontal tabs above the search results.

## Prerequisites
- Drupal installation with Search API, Facets, and Search API Database Search modules installed and enabled.
- Basic understanding of Drupal administration and permissions.

## Configuration Steps

### 1. Install and Enable Required Modules
Ensure that you have the `Search API`, `Facets`, and `Search API Database Search` modules installed and enabled.

### 2. Configure a Search Server and Index
- Navigate to `Configuration > Search and Metadata > Search API`.
- Add a new server or use an existing one, selecting a database server as your choice.
- Create a new index for this server, selecting the content types you wish to include, and configure the fields to be indexed.

### 3. Index Your Content
Ensure that all your content is indexed through the index's "View" tab.

### 4. Create and Configure Facets
- Go to `Configuration > Search and Metadata > Facets`.
- Add a new facet for your index, selecting the "Content Type" field.
- Configure the facet to display as 'Links' and enable 'Show as a block' in the "Display Settings".

### 5. Place the Facet Block
- Access `Structure > Block layout`.
- Position the facet block in a region that appears above your search results, typically at the top of the 'Content' region.

### 6. Style the Facets as Horizontal Tabs
- Apply custom CSS to style the facets as horizontal tabs.
- You can add CSS through your theme or a custom module.

### 7. Test Your Facets
- Perform a search on your search page to verify the functionality and appearance of the facets.

## Additional Information
- **Caching**: Adjust caching settings as needed.
- **Permissions**: Set appropriate permissions for facet visibility and interaction.
- **User Experience**: Organize facets for optimal usability.

---

For further assistance or customization details, feel free to reach out or consult Drupal's official documentation.
