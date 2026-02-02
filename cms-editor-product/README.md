# CMS Editor

The CMS Editor is a powerful, user-friendly tool that streamlines the management and translation of content in Axon Ivy's Content Management System (CMS). This solution enables efficient multilingual content editing for UIs, notifications, and emails through an intuitive WYSIWYG (What You See Is What You Get) web interface.

## Description

In Axon Ivy, all language-specific content for user interfaces, notifications, and emails is centrally managed within the CMS. The CMS Editor provides a comprehensive solution that empowers teams to:

- **Streamline Translation Workflows**: Enable multiple translators to work collaboratively on content localization without requiring technical expertise
- **Simplify Content Management**: Edit and manage unlimited languages through an intuitive web interface, eliminating the need to work directly with HTML or technical markup
- **Accelerate Time-to-Market**: Speed up the localization process for global deployments with real-time preview and easy export/import capabilities
- **Reduce Technical Barriers**: Allow non-technical team members to contribute to translations without needing to understand the underlying CMS structure

The CMS Editor brings significant value to organizations by reducing the time and effort required for multilingual content management, improving translation quality through visual editing, and enabling faster deployment of localized applications to global markets.

**Note:** *In this version, real-time CMS updates are not yet supported. Users must download the modified content bundle in ZIP format after editing and re-import it into the project using Axon Ivy Designer. Changes take effect only after creating and deploying a new release package to the engine.*

## Features

The CMS Editor offers a comprehensive set of features designed to make content translation and management efficient and user-friendly:

- **WYSIWYG Web Editor**  
  Intuitive visual editor that allows translators to see exactly how their content will appear in the application, eliminating guesswork and reducing errors.

- **Multi-Language Support**  
  Edit and manage an unlimited number of languages simultaneously, with side-by-side comparison of translations for consistency.

- **Advanced Search & Filtering**  
  Powerful search capabilities by URI and content (case-insensitive), plus specialized filters to identify incomplete translations (TODO items).

- **Rich Text Editing**  
  Simple formatting styles available without requiring knowledge of HTML tags or markup languages, making it accessible to non-technical translators.

- **Application Context Awareness**  
  Work on multiple applications within a single Ivy engine, with easy application switching to manage different projects.

- **Collaborative Translation**  
  Multiple translators can work simultaneously on different content sections, improving team productivity and reducing translation turnaround time.

- **Export & Import Functionality**  
  Download all translated content as a ZIP file for backup, sharing, or deployment purposes.

- **Role-Based Access Control**  
  Secure access management through the CMS_ADMIN role, ensuring only authorized users can modify content.

- **Content Preview Mode**  
  View all languages in preview mode before editing, allowing for review and quality assurance.

- **Pagination Support**  
  Navigate large content repositories efficiently with customizable page sizes and pagination controls.

## Demo

### 1. Starting the CMS Editor Process

To begin using the CMS Editor, users must have the **CMS_ADMIN** role assigned. This role-based access ensures that only authorized personnel can modify CMS content.

![CMS Editor Process Start](./images/1-cms-editor-process.png)

### 2. CMS Editor Main Interface

The CMS Editor provides a comprehensive interface with multiple functional areas designed for efficient content management:

![CMS Editor Main Page](./images/2-cms-editor-main-page.png)

**Interface Components:**

1. **Application Selector**: Select the target application from all available applications in the Ivy engine. Each engine can host multiple applications, and you can switch between them seamlessly.

2. **Search Input**: Enter text to search across URIs and content. The search functionality is case-insensitive, making it easy to find specific content entries quickly.

3. **Selected CMS**: Displays the key identifier of the currently selected content entry, helping you track which content you're working on.

4. **Filter Only TODO**: Toggle this filter to display only content entries that are marked with the 'TODO' prefix, making it easy to identify incomplete or pending translations.

5. **Result Table**: Displays all matching CMS URIs in a paginated table. You can navigate through multiple pages and adjust the page size to suit your workflow preferences.

6. **Selecting Content**: Click on any URI in the table to load its content into the editing area below. This provides quick access to the content you want to modify.

7. **Content Area**: Shows all configured languages for the selected content in preview mode, allowing you to compare translations side-by-side.

8. **Language Name**: Displays the name of each language (e.g., English, German, French) for which content is available.

9. **Content Preview**: Shows the current content for each language in preview mode, allowing you to review translations before making changes.

10. **WYSIWYG Editor**: Switch to edit mode to modify content using the rich text editor. The WYSIWYG interface provides formatting tools and ensures content appears as it will in the application.

11. **Save Button**: Explicitly save your changes by clicking the save button. The editor does not auto-save, giving you full control over when modifications are committed.

12. **Cancel Button**: Close the editor without saving changes, allowing you to discard unwanted modifications.

13. **Download Button**: Export all translated content as a ZIP file for backup, deployment, or sharing with team members.

## Setup

To install and configure the CMS Editor for your Axon Ivy environment, follow these step-by-step instructions:

### 1. Install from Axon Ivy Marketplace

The easiest way to get started with the CMS Editor is to install it directly from the Axon Ivy Marketplace:

1. Open your Axon Ivy Designer
2. Navigate to the Marketplace
3. Search for "CMS Editor"
4. Click "Install" to add it to your workspace

Alternatively, you can add the CMS Editor as a Maven dependency to your project's `pom.xml`:

```xml
<dependency>
  <groupId>com.axonivy.utils.cmseditor</groupId>
  <artifactId>cms-editor</artifactId>
  <version>13.1.3-SNAPSHOT</version>
  <type>iar</type>
</dependency>
```

### 2. Configure User Roles

The CMS Editor requires users to have the **CMS_ADMIN** role to access and modify content:

1. In your project, navigate to `Config/roles.xml`
2. Add the CMS_ADMIN role to the appropriate users or user groups:

```xml
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>
<role>
    <identifier>Everybody</identifier>
    <role>
        <identifier>CMS_ADMIN</identifier>
    </role>
</role>
```

3. Ensure that only trusted users who should have permission to modify CMS content are assigned this role

### 3. Deploy to Axon Ivy Engine

For production deployments:

1. Build your project including the CMS Editor dependency
2. Deploy the application to your Axon Ivy Engine
3. Ensure all required applications are deployed within the same security context
4. Verify that users with the CMS_ADMIN role can access the CMS Editor process

### 4. Start Using the CMS Editor

Once installed and configured:

1. Log in to your Axon Ivy application with a user account that has the CMS_ADMIN role
2. Navigate to the CMS Editor process start link
3. Select your target application from the Application Selector
4. Begin editing and translating your content
5. Use the Download button to export your changes
6. Re-import the downloaded ZIP file into your project using Axon Ivy Designer
7. Create a new release package and deploy it to apply your changes

### Additional Configuration

**Repository Configuration**

The CMS Editor uses Maven repositories for dependency resolution. Ensure your project's `pom.xml` includes:

```xml
<repositories>
  <repository>
    <id>maven.axonivy.com</id>
    <url>https://maven.axonivy.com</url>
    <snapshots>
      <enabled>true</enabled>
    </snapshots>
  </repository>
</repositories>
```

**Dependencies**

The CMS Editor relies on the following key dependencies:
- JSoup for HTML parsing and manipulation
- Apache POI for potential document export features
- Axon Ivy API for CMS integration

These dependencies are automatically managed when installing the CMS Editor through the Marketplace or Maven.
