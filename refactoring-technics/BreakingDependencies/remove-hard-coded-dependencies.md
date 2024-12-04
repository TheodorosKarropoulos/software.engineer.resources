## Remove Hard-Coded Dependencies
Hard-coding values or dependencies directly into classes makes your code less flexible. Instead, you can externalize them or inject them, allowing you to easily change or replace them.
### Example in C#
**Before (Hard-Coded Dependencies)**:
```csharp
public class ConfigurationService
{
    public string GetDatabaseConnectionString()
    {
        return "Server=myServerAddress;Database=myDataBase;User Id=myUsername;Password=myPassword;";  // Hardcoded connection string
    }
}
```
**After (Using External Configuration)**:
```csharp
public class ConfigurationService
{
    private readonly IConfiguration _configuration;  // Injected configuration

    public ConfigurationService(IConfiguration configuration)
    {
        _configuration = configuration;
    }

    public string GetDatabaseConnectionString()
    {
        return _configuration["Database:ConnectionString"];  // Read from external configuration
    }
}
```