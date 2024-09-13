# Generating Web-Based Documentation from C# Code
This document provides guidance on generating web-based documentation from C# code using DocFX. It outlines the steps, best practices, and customization options available for creating professional and consistent documentation. For specific configurations and detailed setups, please refer to the detailed guidelines and resources provided within each individual project.

----------

### Using DocFX

**DocFX** is an open-source tool developed by Microsoft specifically for generating documentation from .NET source code and markdown files. It can produce documentation that closely resembles the style of Microsoft's official documentation.

#### **Features:**

-   Supports C# and .NET projects.
-   Parses XML documentation comments in your code.
-   Generates static websites with customizable templates.
-   Supports conceptual documentation in Markdown.
-   Integrates with CI/CD pipelines.

#### **Steps to Generate Documentation with DocFX:**

**Prerequisites:**

-   Install DocFX by downloading the latest release or using Chocolatey:
-   
`choco install docfx -y`

**1. Add XML Documentation Comments to Your Code:**

-   Ensure your C# code includes XML documentation comments (`///`) for classes, methods, properties, etc.
```csharp
    /// <summary>
    /// Calculates the sum of two integers.
    /// </summary>
    /// <param name="a">First integer.</param>
    /// <param name="b">Second integer.</param>
    /// <returns>The sum of a and b.</returns>
    public int Add(int a, int b)
    {
        return a + b;
    }
```
**2. Enable XML Documentation File Generation:**

-   In Visual Studio:
    
    -   Right-click your project and select **Properties**.
    -   Go to the **Build** tab.
    -   Check **XML documentation file** and specify a path if necessary.
    -   Repeat for all configurations (Debug and Release).
-   In your `.csproj` file, add:
  
  ```xml 
<PropertyGroup>
  <DocumentationFile>bin\Debug\net6.0\YourProject.xml</DocumentationFile>
</PropertyGroup>
```

**3. Initialize a DocFX Project:**

-   Open a command prompt in your project's root directory.
    
-   Run:

 ```bash
docfx init -q

```

-   This creates a `docfx_project` folder with default configurations.
    

**4. Configure DocFX:**

-   Navigate to `docfx_project` and open `docfx.json`.
    
-   Modify the `metadata` section to include your project's source code:

 ```json
"metadata": [
  {
    "src": [
      {
        "files": [ "../YourProject/*.csproj" ],
        "exclude": [ "**/bin/**", "**/obj/**" ]
      }
    ],
    "dest": "api"
  }
],
```
-   Adjust the `build` section if needed.
    

**5. Build the Documentation:**

-   In the command prompt, run:

 ```bash
docfx docfx.json
```

-   This command generates the documentation and outputs it to the `_site` folder by default.
    

**6. Preview the Documentation Locally:**

-   Run the DocFX server to preview your documentation:

 ```bash
docfx serve _site
```
**7. Customize the Documentation:**

-   **Themes:** DocFX supports theming. You can use built-in themes or create a custom one.
-   **Logo and Branding:** Customize the header, footer, and add your project's logo.
-   **Additional Content:** Add Markdown files for conceptual topics and tutorials in the `articles` folder.
-   **Table of Contents:** Modify `toc.yml` files to organize your content.

**8. Deploy the Documentation:**

-   **GitHub Pages:** Push the `_site` folder to a `gh-pages` branch.
-   **Azure Static Web Apps:** Deploy directly from your repository.
-   **Other Hosting Services:** Upload the contents of `_site` to any static web hosting provider.
  

### **Example Using DocFX**

**Project Structure:**

- YourProject/
  - src/
    - YourCode.cs
  - docfx_project/
    - docfx.json
    - api/
    - articles/
    - toc.yml
  


**Sample `docfx.json`:**

 ```json
{
  "metadata": [
    {
      "src": [
        {
          "files": [ "../src/**/*.csproj" ],
          "exclude": [ "**/bin/**", "**/obj/**" ]
        }
      ],
      "dest": "api"
    }
  ],
  "build": {
    "content": [
      {
        "files": [ "articles/**.md", "articles/**/toc.yml" ]
      },
      {
        "files": [ "api/**.yml", "api/index.md" ]
      }
    ],
    "dest": "_site",
    "globalMetadata": {
      "_enableSearch": true
    },
    "template": [
      "default"
    ]
  }
}
```


**Adding Conceptual Documentation:**

-   Create Markdown files in the `articles` directory.
    
-   Update `toc.yml` to include your new pages.

 ```yaml
- name: Home
  href: index.md
- name: Getting Started
  href: getting-started.md
- name: API Reference
  href: api/index.md
```
### **Deploying Your Documentation**

**Options:**

-   **GitHub Pages:**
    
    -   Push the `_site` folder to the `gh-pages` branch.
    -   Configure your repository settings to serve the site from `gh-pages`.
-   **Azure Static Web Apps:**
    
    -   Link your repository and configure the build to output the `_site` folder.
-   **Netlify or Vercel:**
    
    -   Connect your repository and set the build command and publish directory.



**Adding Conceptual Documentation:**

-   Create Markdown files in the `articles` directory.
    
-   Update `toc.yml` to include your new pages.

### **Best Practices**

-   **Consistent Commenting:**
    
    -   Use consistent and thorough XML documentation comments in your code.
    -   Document public APIs, parameters, return values, exceptions, and examples.
-   **Use Code Examples:**
    
    -   Provide code snippets in your documentation to illustrate usage.
-   **Organize Content:**
    
    -   Create a logical structure with clear sections and navigation.
    -   Use table of contents and indexes.
-   **Automate Documentation Generation:**
    
    -   Integrate documentation generation into your build or CI/CD pipeline.
    -   Ensure documentation stays up-to-date with code changes.
-   **Customize Appearance:**
    
    -   Modify themes and styles to match your branding.
    -   Add logos, custom CSS, and templates.



**Conclusion**

To generate web-based documentation from your C# code similar to the Microsoft Docs:

-   **DocFX** is highly recommended due to its compatibility with .NET projects and ability to produce professional, customizable documentation.
-   Ensure your code is well-documented with XML comments.
-   Customize and organize your documentation for the best user experience.
-   Deploy your documentation to a hosting service for public access.
-   

## Additional Resources

- **DocFX Documentation**:
   - **[Getting Started Guide](https://dotnet.github.io/docfx/tutorial/docfx_getting_started.html)**
   - **[DocFX GitHub Repository](https://github.com/dotnet/docfx)**

- **Sandcastle Help File Builder**:

  - **[SHFB Documentation](https://ewsoftware.github.io/SHFB/html/79C5F9D0-64A0-4C8D-B4F5-312B4B481E50.htm)**
 
 
- **Doxygen Manual**:
  - **[Doxygen Documentation](http://www.doxygen.nl/manual/index.html)**

- **Markdown Syntax**:
  - **[Markdown Guide](https://www.markdownguide.org/basic-syntax/)**
