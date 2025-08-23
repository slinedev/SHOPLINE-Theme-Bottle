# Bottle Theme for SHOPLINE Online Store 3.0

The official foundational theme for SHOPLINE Online Store 3.0, built for performance, flexibility, and a world-class developer experience.

## Introduction

Bottle is the foundational theme for the SHOPLINE Online Store 3.0 platform. It is not a feature-complete, standalone storefront but rather a lightweight and highly performant starter theme. Built on SHOPLINE's proprietary, high-performance Sline template rendering engine, Bottle is designed to serve as the core reference and starting point for all new OS 3.0 themes.

The design philosophy behind Bottle centers on speed, modularity, and developer-friendliness. By providing a standardized, optimized, and reusable core, it dramatically accelerates the development process for theme builders. Developers can bypass the need to construct a basic framework from scratch and instead focus on extending Bottle with new features and unique designs. This approach also ensures that all new themes in the SHOPLINE ecosystem adhere to the latest architectural standards and can leverage the performance benefits of the Sline engine.

## Key Features

The Bottle theme comes with a suite of features specifically engineered for modern e-commerce, enhancing the shopping experience and empowering merchants and developers alike.

### Performance and SEO

Bottle is architecturally optimized for lightning-fast store performance and high search engine visibility.

  * **Blazing-Fast Loading Speeds:** The theme's lightweight design includes zero third-party JavaScript dependencies, significantly reducing page load overhead. All SHOPLINE stores are deployed on a vast edge network (CDN), ensuring rapid global access even during peak holiday traffic.
  * **Automated Structured Data:** The theme automatically generates structured data for search engines, including product image links, names, descriptions, and prices. This clean formatting helps search engines crawl content efficiently, leading to richer search results and improved click-through rates.
  * **Optimized for Search:** The theme's page layouts are designed with clear titles, body text, and meta tags to boost relevance, increase organic traffic, and attract more potential customers.

### Design and Customization

With the new Online Store 3.0 theme editor, Bottle offers an unparalleled level of customization without requiring any code.

  * **Intuitive Drag-and-Drop Editing:** Merchants can easily design and build their storefronts using a simple, intuitive drag-and-drop interface.
  * **Multi-Level Nested Blocks:** A core innovation of OS 3.0, the component structure supports up to five levels of nested blocks within each section. This feature provides unprecedented flexibility in controlling page layouts and achieving complex, layered designs that were previously not possible.
  * **Flexible Layouts:** Merchants and developers can precisely control the position, spacing, and alignment of page elements to match their exact design requirements.

### Extensibility

Bottle provides a robust framework for developers to extend its functionality seamlessly.

  * **Theme Events:** The theme is equipped with a standard set of events that developers can listen to or trigger to perform custom actions. These events include product browsing, SKU switching, adding products to the cart, and more, allowing for rich, customized user experiences.
  * **App Extension Integration:** The theme supports deep integration with apps through **App Blocks** and **App Embed Blocks**. This modular design allows app developers to provide functionalities as self-contained, configurable modules that can be injected into the theme, enabling a more flexible and composable ecosystem.

## Installation

This guide provides steps for both non-technical merchants and developers to get started with the Bottle theme.

### For Merchants

Merchants can access the Bottle theme directly from the SHOPLINE Admin Panel.

  * **Install from Theme Store:** Log in to your SHOPLINE Admin Panel, navigate to **Online Store \> Design**, and search for the free Bottle theme in the **Theme Shop**.

### For Developers

The Bottle theme's source code can be obtained directly from the Theme Shop in the SHOPLINE Admin Panel. It's important to note that while Bottle is the official OS 3.0 theme, the current `shopline theme init` CLI command is documented for cloning the **Seed** theme, which is an OS 2.1 reference theme.

**Prerequisites**:

  * Git
  * Node.js version 14.0.0 or higher

**Development Workflow**:

1.  **Install SHOPLINE CLI**:
    Install the command-line tool for building SHOPLINE themes globally via npm or yarn.

    ```bash
    npm install --global @shoplinedev/cli
    # or
    yarn global add @shoplinedev/cli
    ```

2.  **Initialize a New Theme with Seed**:
    Navigate to your desired working directory and use the `shopline theme init` command to clone the Seed reference theme. This is the recommended starting point for new theme development, as outlined in the documentation.

    ```bash
    shopline theme init <THEME_NAME>
    ```

    Replace `<THEME_NAME>` with your desired folder name. Then, navigate into the new directory:

    ```bash
    cd <THEME_NAME>
    ```

3.  **Connect to Your Store**:
    Use the `shopline login` command to connect the CLI to your SHOPLINE store. Replace `<DOMAIN>` with your store's URL.

    ```bash
    shopline login --store <DOMAIN>
    ```

    This command will open a browser for you to log in to your store account.

4.  **Local Preview**:
    Run `shopline theme serve` to upload the theme to your connected store as a development theme and start a local preview server. You can view the live preview at `http://127.0.0.1:8282`, which automatically reloads with any local file changes.

## Usage & Customization

The Bottle theme can be customized using the intuitive Theme Editor or by directly editing the theme's code.

### For Merchants (via Theme Editor)

  * **Access the Editor**: From your SHOPLINE Admin Panel, go to **Online Store \> Design** and click the **Design** button on your current theme.
  * **Global Settings**: Adjust the theme's global settings, such as brand colors and typography. The custom theme colors will apply to key elements like buttons, icons, and the shopping cart.
  * **Manage Sections & Blocks**: Use the drag-and-drop interface to add, remove, and reorder content blocks and sections on any page.

### For Developers (via Code)

For advanced customization, developers can directly modify the theme's files.

  * **Theme Configuration**: Theme settings and their values are stored in the `config/settings_data.json` file. You can modify this file to change the theme's settings, such as the page background color.
  * **Extending Code**: Developers can extend the theme by writing custom CSS and JavaScript and utilizing the Handlebars template language to dynamically render content.

## For Developers

This section provides an overview of the Bottle theme's architecture and key development tools.

### Theme Architecture

SHOPLINE themes follow a standard directory structure to ensure that different code modules work together efficiently.

| Directory/File | Description |
| :--- | :--- |
| `├── assets` | Stores all static assets like images, CSS, and JavaScript files. |
| `├── components` | Contains reusable theme components. |
| `├── config` | Holds configuration files that define and store theme settings. |
| `├── i18n` | Stores localization files for multilingual support. |
| `├── layout` | Contains layout files, such as `theme.html`, that define the reusable layout across different page types. |
| `├── public` | Stores public assets. |
| `├── sections` | Contains all theme sections, which are reusable content modules. |
| `├── snippets` | Contains smaller, reusable Handlebars code snippets. |
| `├── templates` | Stores page template files that define the overall structure of store pages. |
| `├── theme.config.json` | The theme's primary configuration file. |
| `├── theme.schema.json` | Defines the schema for theme settings. |

### App Extension Integration

SHOPLINE 3.0 themes provide two main extension types for deep app integration.

  * **App Blocks:** These are UI components that can be added, moved, and reordered within the Theme Editor. They are perfect for injecting app functionality like product review widgets or custom forms directly into a section.
  * **App Embed Blocks:** These are used for non-UI or floating elements like chat widgets, announcement bars, or SEO meta tags. They are automatically injected into the `<head>` or `<body>` of the theme when enabled.

### CLI Command Reference

| Command | Purpose |
| :--- | :--- |
| `shopline theme init <NAME>` | Clones the official Seed reference theme to your local machine. |
| `shopline login --store <DOMAIN>` | Connects the CLI tool to a specified SHOPLINE store. |
| `shopline theme serve` | Starts a local development server for a real-time theme preview. |
| `shopline theme push` | Pushes local theme code to a specified theme in your store. |
| `shopline theme package` | Packages the local theme code into a `.zip` file for manual upload. |

## Contributing

While the Bottle theme's source code is accessible for developers to build upon, it is not an open-source project in the traditional sense, such as under an MIT or Apache 2.0 license.

The theme is provided under the terms of the **SHOPLINE Developer Services Agreement**, which defines a "Source-Available" model. This means developers can view and learn from the code but are restricted from distributing, selling, or licensing it to third parties.

Due to this licensing model, all contributions, including bug reports and feature requests, should be directed to the official SHOPLINE developer support channels rather than submitted via pull requests to a public repository.

## License

This theme is provided under the terms of the SHOPLINE Developer Services Agreement.

## Support

For technical assistance or to provide feedback, please refer to the official([https://developer.shopline.com/](https://developer.shopline.com/)) and([https://help.shopline.com/](https://help.shopline.com/)).
