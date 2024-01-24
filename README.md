# Search


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
