# CMS Editor

Axon Ivy's CMS Editor is a powerful, user-friendly tool designed to streamline the management and translation of multilingual content within your Axon Ivy applications. Transform the way your team handles UI labels, notifications, and email templates across multiple languages.

## Description

In Axon Ivy, all language content for user interfaces, notifications, and emails is managed through the Content Management System (CMS). The CMS Editor provides an intuitive web-based interface that empowers translators and content managers to efficiently manage multilingual content without requiring technical expertise in HTML or configuration files.

**Key Value Propositions:**

- **Accelerated Translation Workflow**: Enable multiple translators to work simultaneously on different languages, dramatically reducing time-to-market for multilingual applications
- **No Technical Barriers**: Translators can focus on content quality without dealing with HTML tags, YAML syntax, or technical configuration
- **Enhanced Collaboration**: Support unlimited languages with a clean, organized interface that makes content management accessible to non-technical team members
- **Streamlined Content Distribution**: Export and import translated content bundles seamlessly, ensuring consistency across development, testing, and production environments

## Features

The CMS Editor provides comprehensive capabilities for managing multilingual content:

- **WYSIWYG Editor**  
  Intuitive What-You-See-Is-What-You-Get editing experience with rich text formatting, eliminating the need for HTML knowledge

- **Multi-Language Support**  
  Manage and translate unlimited languages simultaneously within a single, unified interface

- **Powerful Search & Filter**  
  Quickly locate content using case-insensitive search across URIs and content, with special filtering for TODO items requiring translation

- **Application-Aware Navigation**  
  Seamlessly switch between multiple applications within your Ivy engine, each with its own content structure

- **Real-Time Preview**  
  View content in preview mode before editing to understand context and ensure translation accuracy

- **Bulk Export Capabilities**  
  Download complete CMS bundles as ZIP files for version control, backup, or deployment to other environments

- **Simple Text Formatting**  
  Apply basic formatting styles directly through the editor interface without writing HTML markup

- **Role-Based Access Control**  
  Secure access through Axon Ivy's permission system, requiring CMS_ADMIN role for content management

- **Collaborative Workflow**  
  Multiple users can work on different content entries simultaneously, improving team productivity

## Demo

### Starting the CMS Editor

To launch the CMS Editor, users must have the **CMS_ADMIN** role assigned. Start the process from your Axon Ivy application:

![CMS Editor Process Start](./images/1-cms-editor-process.png)

### Main Interface Overview

The CMS Editor interface is designed for efficiency and ease of use:

![CMS Editor Main Page](./images/2-cms-editor-main-page.png)

**Interface Components:**

1. **Application Selector**: Choose from multiple applications deployed on your Ivy engine to manage their respective content
2. **Search Input**: Enter text to search across URIs and content (case-insensitive)
3. **Selected CMS**: Displays the URI key of the currently selected content entry
4. **Filter Only TODO**: Toggle to show only content entries marked with the 'TODO' prefix, helping identify untranslated content
5. **Results Table**: Browse all content URIs with pagination controls and adjustable page size
6. **Content Selection**: Click any URI to load its content into the editing area
7. **Content Area**: View all available languages for the selected entry in preview mode
8. **Language Name**: Clear identification of each language in your content structure
9. **Content Preview**: Display content in read-only preview mode to review existing translations
10. **WYSIWYG Editor**: Edit mode with rich text formatting capabilities for content updates
11. **Save Button**: Explicitly save your changes (auto-save is not enabled to prevent accidental modifications)
12. **Cancel Button**: Close the editor without saving changes
13. **Download Button**: Export all translated content as a ZIP file for import into other environments

## Setup

To implement and use the CMS Editor in your Axon Ivy environment, follow these steps:

### Prerequisites

- Axon Ivy Engine version 12.0 or higher
- Administrative access to your Axon Ivy application
- CMS_ADMIN role assigned to users who will manage content

### Installation

**Option 1: Install from Axon Ivy Marketplace**

1. Open your Axon Ivy Designer
2. Navigate to **Marketplace** → **Search for "CMS Editor"**
3. Click **Install** to add the CMS Editor to your workspace
4. The installer will automatically add the cms-editor dependency to your project

**Option 2: Add as Maven Dependency**

Add the following dependency to your project's `pom.xml`:

```xml
<dependency>
  <groupId>com.axonivy.utils.cmseditor</groupId>
  <artifactId>cms-editor</artifactId>
  <version>${version}</version>
  <type>iar</type>
</dependency>
```

Ensure the Axon Ivy Maven repository is configured:

```xml
<repository>
  <id>maven.axonivy.com</id>
  <url>https://maven.axonivy.com</url>
  <snapshots>
    <enabled>true</enabled>
  </snapshots>
</repository>
```

### Configuration

1. **Configure User Permissions**  
   Assign the **CMS_ADMIN** role to users who need to manage content:
   - Navigate to your application's security settings
   - Grant the CMS_ADMIN role to appropriate users or user groups

2. **Access the CMS Editor**  
   - Launch your Axon Ivy application
   - Navigate to the CMS Editor process (typically available in the process list)
   - Select your target application from the application selector

3. **Workflow for Content Updates**  
   
   > **Important**: This version does not support real-time CMS updates. Follow this workflow for content changes:
   
   - Edit content using the CMS Editor interface
   - Save your changes within the editor
   - Click the **Download** button to export all content as a ZIP file
   - Import the ZIP file into your project using Axon Ivy Designer
   - Create a new release package
   - Deploy the updated package to your Axon Ivy Engine
   
   Changes will take effect only after the new release is deployed.

### Best Practices

- **Use TODO Markers**: Prefix incomplete translations with "TODO" to easily track pending work
- **Regular Exports**: Periodically export your CMS content as backups
- **Version Control**: Store exported ZIP files in your version control system alongside your project
- **Translation Review**: Use the preview mode to verify translations in context before deployment
- **Collaborative Guidelines**: Establish a workflow for your team to avoid conflicts when multiple translators work simultaneously
