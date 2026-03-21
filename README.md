# Umbraco Cloud ACME v17

This workspace contains a single Umbraco 17 web application configured as an ASP.NET Core project.

## Project Layout

- `umbraco-cloud.slnx` - solution file for the workspace.
- `umbraco-cloud-develop/` - the main web application.
- `umbraco-cloud-develop/Program.cs` - bootstraps Umbraco, backoffice, and website endpoints.
- `umbraco-cloud-develop/Views/` - Razor views and partials for the site.
- `umbraco-cloud-develop/uSync/` - serialized Umbraco content and configuration.
- `umbraco-cloud-develop/wwwroot/` - static assets served by the site.

## Technology

- .NET 10
- Umbraco CMS 17.2.2
- uSync 17.0.0
- Clean 7.0.5

## Running Locally

1. Install the .NET 10 SDK.
2. Restore dependencies:

   ```bash
   dotnet restore umbraco-cloud.slnx
   ```

3. Start the application:

   ```bash
   dotnet run --project umbraco-cloud-develop
   ```

4. Open the app in a browser.

   The launch profile is configured for:

   - `https://localhost:44376`
   - `http://localhost:15254`

## Notes

- The app uses Umbraco backoffice and website middleware in `Program.cs`.
- Razor compilation is disabled in the project file, while Razor files are copied to the publish output for backoffice support.
- Compression is disabled in the project file to avoid double-compressing backoffice assets.
