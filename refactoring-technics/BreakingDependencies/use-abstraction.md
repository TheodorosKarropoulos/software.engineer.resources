## Use Abstraction (Interfaces or Abstract Classes)
Creating an interface or an abstract class helps decouple the specific implementation of a dependency. The class doesn't need to know about the concrete class, just the contract (interface or abstract class) it implements.

### Example in C#
**Before (Tightly Coupled)**:
```csharp
public class OrderService
{
    private readonly EmailService _emailService;

    public OrderService()
    {
        _emailService = new EmailService(); // Dependency is hardcoded
    }

    public void PlaceOrder(Order order)
    {
        // Process order...
        _emailService.SendOrderConfirmation(order);
    }
}
```
**After (Using Abstraction)**:
```csharp
public interface INotificationService
{
    void SendOrderConfirmation(Order order);
}

public class EmailService : INotificationService
{
    public void SendOrderConfirmation(Order order)
    {
        // Send email logic
    }
}

public class SMSService : INotificationService
{
    public void SendOrderConfirmation(Order order)
    {
        // Send SMS logic
    }
}

public class OrderService
{
    private readonly INotificationService _notificationService;

    // Constructor now accepts an abstraction
    public OrderService(INotificationService notificationService)
    {
        _notificationService = notificationService;
    }

    public void PlaceOrder(Order order)
    {
        // Process order...
        _notificationService.SendOrderConfirmation(order);
    }
}
```