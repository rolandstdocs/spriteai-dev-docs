---
title: Customizing Documentation
sidebar_label: Customizing Docs
---

# Customizing Documentation

This guide will walk you through the process of customizing your documentation to fit your project's specific needs. We'll cover modifying the landing page, adding new pages, and using custom components like JsonToTable.

## Modifying the Landing Page

The landing page is the first thing users see when they visit your documentation. You can customize it to provide a better introduction to your project.

### Using the LandingPage Component

The `LandingPage` component in `src/components/LandingPage.jsx` allows you to create a custom landing page using a drag-and-drop editor.

```jsx
import React from 'react';
import Editor from '@site/src/components/editor.jsx';

export const data = {
  // Your landing page content structure
};

export default function LandingPage() {
    return (
        <Editor data={data} />
    );
}
```

To modify the landing page:

1. Edit the `data` object in `LandingPage.jsx` to change the content structure.
2. Use the `Editor` component to render your custom landing page.

## Adding New Pages

To add a new page to your documentation:

1. Create a new Markdown file in the `docs` directory.
2. Add frontmatter at the top of the file to specify metadata:

```markdown
---
title: Your New Page Title
sidebar_label: Sidebar Label
---

# Your New Page Content

Write your documentation content here.
```

3. Update the `sidebars.js` file to include your new page in the navigation structure.

## Using Custom Components

### JsonToTable Component

The `JsonToTable` component in `src/components/JsonToTable.jsx` allows you to display API information in a structured format.

To use the JsonToTable component in your documentation:

1. Import the component in your Markdown file using MDX:

```mdx
import JsonToTable from '@site/src/components/JsonToTable';

# API Documentation

<JsonToTable />
```

2. Provide the API information in the frontmatter of your Markdown file:

```markdown
---
title: API Documentation
api: <base64_encoded_and_compressed_api_json>
---
```

The `JsonToTable` component will automatically decode and display the API information, including:

- API title and description
- Parameters
- Request body
- Security schemes
- Postman configuration (if available)

## Customizing the Theme

To further customize the appearance of your documentation:

1. Modify the CSS in `src/css/custom.css` to change colors, fonts, and other styles.
2. Update the `docusaurus.config.js` file to change site-wide configurations, such as the title, tagline, and navbar items.

## Best Practices for Customization

1. Keep your customizations consistent with the overall design and structure of the documentation.
2. Test your changes thoroughly, especially when adding custom components or modifying the layout.
3. Ensure that your customizations are responsive and work well on different devices and screen sizes.
4. Document any custom components or significant modifications for future maintainers.

By following these guidelines, you can create a tailored documentation experience that best serves your project and its users.