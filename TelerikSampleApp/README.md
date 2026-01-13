# Telerik Sample App

This is a sample ASP.NET Core MVC application demonstrating how to integrate Telerik UI for ASP.NET Core components.

## Prerequisites

- .NET 10.0 SDK or later
- A Telerik UI for ASP.NET Core license (trial or commercial)

## Project Structure

```
TelerikSampleApp/
├── Controllers/         # MVC Controllers
│   └── HomeController.cs
├── Models/             # Data models
├── Views/              # Razor views
│   ├── Home/
│   │   ├── Index.cshtml
│   │   ├── TelerikDemo.cshtml
│   │   └── Privacy.cshtml
│   ├── Shared/
│   │   └── _Layout.cshtml
│   ├── _ViewImports.cshtml
│   └── _ViewStart.cshtml
├── wwwroot/            # Static files (CSS, JS, images)
├── Program.cs          # Application entry point
└── appsettings.json    # Configuration
```

## Setting Up Telerik UI

To use Telerik UI components in this application, follow these steps:

### Step 1: Obtain a Telerik License

1. Visit [Telerik UI for ASP.NET Core](https://www.telerik.com/aspnet-core-ui)
2. Sign up for a free trial or purchase a license
3. Get your Telerik NuGet feed credentials

### Step 2: Add Telerik NuGet Source

Add the Telerik NuGet feed to your NuGet configuration:

```bash
dotnet nuget add source https://nuget.telerik.com/v3/index.json -n "telerik.com" -u <your-telerik-account-email> -p <your-telerik-password> --store-password-in-clear-text
```

Or add it to your `nuget.config` file:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <packageSources>
    <add key="nuget.org" value="https://api.nuget.org/v3/index.json" protocolVersion="3" />
    <add key="telerik.com" value="https://nuget.telerik.com/v3/index.json" />
  </packageSources>
  <packageSourceCredentials>
    <telerik.com>
      <add key="Username" value="<your-telerik-account-email>" />
      <add key="ClearTextPassword" value="<your-telerik-password>" />
    </telerik.com>
  </packageSourceCredentials>
</configuration>
```

### Step 3: Install Telerik UI NuGet Package

```bash
cd TelerikSampleApp
dotnet add package Telerik.UI.for.AspNet.Core
```

### Step 4: Uncomment Telerik Configuration

After installing the package, uncomment the following lines:

**In `Program.cs`:**
```csharp
// Uncomment this line:
builder.Services.AddKendo();
```

**In `Views/_ViewImports.cshtml`:**
```razor
@* Uncomment this line: *@
@addTagHelper *, Kendo.Mvc
```

**In `Views/Home/TelerikDemo.cshtml`:**
- Uncomment the sample component examples to see them in action

### Step 5: Add Telerik Scripts and Styles

Add the following to your `_Layout.cshtml` in the `<head>` section (after installing the package):

```html
<link rel="stylesheet" href="https://kendo.cdn.telerik.com/themes/10.0.0/default/default-main.css" />
```

And before the closing `</body>` tag:

```html
<script src="https://kendo.cdn.telerik.com/2025.1.130/js/kendo.all.min.js"></script>
<script src="https://kendo.cdn.telerik.com/2025.1.130/js/kendo.aspnetmvc.min.js"></script>
```

## Running the Application

1. Build the project:
   ```bash
   dotnet build
   ```

2. Run the application:
   ```bash
   dotnet run
   ```

3. Open your browser and navigate to `https://localhost:5001` (or the URL shown in the console)

4. Click on "Telerik Demo" in the navigation menu to see the Telerik UI components page

## Available Telerik Components (Examples in TelerikDemo.cshtml)

Once you've completed the setup, the demo page includes examples of:

- **DatePicker**: Date selection component
- **Grid**: Data grid with sorting, filtering, and paging
- **Button**: Styled button component
- **DropDownList**: Dropdown selection component
- **Chart**: Data visualization component

## Resources

- [Telerik UI for ASP.NET Core Documentation](https://docs.telerik.com/aspnet-core/introduction)
- [Live Demos](https://demos.telerik.com/aspnet-core/)
- [API Reference](https://docs.telerik.com/aspnet-core/api/)
- [Knowledge Base](https://docs.telerik.com/aspnet-core/knowledge-base)

## License

This sample application is provided as-is for demonstration purposes. Telerik UI for ASP.NET Core requires a commercial license from Progress Software Corporation.

## Support

For Telerik-specific issues, please refer to:
- [Telerik Support Center](https://www.telerik.com/account/support-center)
- [Telerik Forums](https://www.telerik.com/forums/aspnet-core-ui)

For general ASP.NET Core questions:
- [Microsoft ASP.NET Core Documentation](https://learn.microsoft.com/aspnet/core)
