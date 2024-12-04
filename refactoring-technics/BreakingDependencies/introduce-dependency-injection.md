## Introduce Dependency Injection
Dependency Injection (DI) is a technique where dependencies are injected into a class rather than the class creating the dependencies itself. This can be done via constructor injection, method injection, or property injection.

### Examples in C#
**Before (Tightly Coupled)**:

```csharp
public class OrderService
{
    private readonly EmailService _emailService;
    
    public OrderService()
    {
        _emailService = new EmailService();  // Directly instantiating the dependency
    }

    public void PlaceOrder(Order order)
    {
        // Process order logic...
        _emailService.SendOrderConfirmation(order);
    }
}

public class EmailService
{
    public void SendOrderConfirmation(Order order)
    {
        // Logic to send email
    }
}

```
**After (Using Dependency Injection)**:
```csharp
public interface IEmailService
{
    void SendOrderConfirmation(Order order);
}

public class EmailService : IEmailService
{
    public void SendOrderConfirmation(Order order)
    {
        // Logic to send email
    }
}

public class OrderService
{
    private readonly IEmailService _emailService;
    
    // Dependency injected via constructor
    public OrderService(IEmailService emailService)
    {
        _emailService = emailService;
    }

    public void PlaceOrder(Order order)
    {
        // Process order logic...
        _emailService.SendOrderConfirmation(order);
    }
}

```