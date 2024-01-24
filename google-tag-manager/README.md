## Extending GTM for Event Tracking

This README serves as a guide for implementing extended event tracking using Google Tag Manager (GTM) on websites. It's particularly useful for tracking interactive elements like Accordions. The documentation includes essential steps and code snippets, enabling easy understanding and implementation.

### Getting Started with Event Tracking in GTM

To start tracking events like Accordion clicks, ensure that GTM is properly set up on your site. If you're new to GTM, refer to [Google's GTM documentation](https://support.google.com/tagmanager/answer/6102821?hl=en) for initial setup instructions.

### Tracking Accordion Clicks

#### Step 1: Create a Click Trigger in GTM

1. **Open GTM**: Navigate to your GTM dashboard.
2. **New Trigger**: Click 'Triggers' > 'New'.
3. **Configure Trigger**:
   - Name the trigger (e.g., 'Accordion Click Trigger').
   - Select 'Click' as trigger type.
   - Choose either 'All Elements' or specify elements that represent Accordion headers.

#### Step 2: Identifying Accordion Elements

Identify your Accordion headers using unique CSS classes, IDs, or attributes. These will be used in GTM to recognize clicks.


### Step 3: Capturing Accordion Clicks with a JavaScript Variable

#### A. Define a JavaScript Variable in GTM
1. **Go to Variables**: In your GTM dashboard, navigate to 'Variables'.
2. **Create New User-Defined Variable**: Click 'New' to create a variable.
3. **Variable Configuration**:
   - Choose 'Custom JavaScript' as the variable type.
   - Write a JavaScript function that returns a string combining the Accordion ID and the current page URL.

#### B. JavaScript Function Example
```javascript
function() {
  // Assuming each accordion has a unique ID attribute
  var accordionId = event.target.id; // Replace with actual logic to capture the Accordion ID
  var pageUrl = window.location.pathname; // Captures the URL path

  // Combine both values with a separator, for example: 'PageURL | AccordionID'
  return pageUrl + " | " + accordionId;
}
```
This script assumes that when an Accordion is clicked, its ID can be captured from the event target. Adjust the script to match your Accordion's implementation details.

#### C. Use This Variable in Your Event Tag
- When setting up your GTM event tag (as described in previous steps), use this custom JavaScript variable for the 'Label' field.
- This will send an event to Google Analytics with a label formatted as 'PageURL | AccordionID', allowing you to track both the specific Accordion and the page it was on.

### Tips for Implementation
- **Test Thoroughly**: Use GTM's preview mode to test the functionality. Ensure that the variable correctly captures the desired data when an Accordion is clicked.
- **Consistency in ID Assignment**: Make sure each Accordion has a unique and consistent ID across all pages for accurate tracking.
- **Privacy Compliance**: Ensure that the data captured and sent does not violate any user privacy regulations.

#### Step 4: Create a Tag for Event Tracking

1. **New Tag**: In GTM, click 'Tags' > 'New'.
2. **Tag Configuration**:
   - Select 'Google Analytics: Universal Analytics' as the tag type.
   - Set Track Type to 'Event'.
   - Configure the Category (e.g., 'Accordion'), Action (e.g., 'Click'), and Label (use a dynamic variable like `{{Click Text}}`).

#### Step 5: Including Page Context

Include variables like 'Page Path' or 'Page Title' in the tag to track the source page of the click.

#### Step 6: Testing and Deploying

Use GTM's preview and debug mode to test the setup, then publish the changes once verified.

### Code Snippets

Here are essential code snippets for your reference:

**GTM Tag Configuration:**

```markdown
Google Analytics Tag Type: Universal Analytics
Tracking Type: Event
Category: Accordion
Action: Click
Label: {{Click Text}} or Custom JS Variable for Accordion Title
Google Analytics Settings: Your GA Settings Variable
Trigger: Accordion Click Trigger
```

### Best Practices and Tips

- Always test new configurations in a staging environment first.
- Regularly check GTM and Google Analytics to ensure data is being captured accurately.
- Respect user privacy and comply with data protection regulations.

### Conclusion

This guide provides a basic framework for extending event tracking using GTM on Drupal sites. Customizations may be necessary based on specific site configurations and requirements.