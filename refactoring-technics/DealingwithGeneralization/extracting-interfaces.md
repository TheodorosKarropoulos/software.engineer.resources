## Extracting Interfaces (Generalization through Abstraction)
By extracting an interface, you allow classes to depend on abstractions, not concrete implementations. This makes it easier to change the underlying implementation without affecting the consumers of the interface.
### Example in C#
**Before (No Generalization)**:
```csharp
public class EmailService
{
    public void SendEmail(string recipient, string message)
    {
        // Code to send an email
        Console.WriteLine("Email sent to " + recipient);
    }
}

public class NotificationService
{
    private EmailService _emailService;

    public NotificationService()
    {
        _emailService = new EmailService();  // Direct dependency
    }

    public void Notify(string recipient, string message)
    {
        _emailService.SendEmail(recipient, message);  // Using a specific service
    }
}
```
**After (Using an Interface for Generalization)**:
```csharp
public interface INotificationService
{
    void SendNotification(string recipient, string message);
}

public class EmailService : INotificationService
{
    public void SendNotification(string recipient, string message)
    {
        // Code to send an email
        Console.WriteLine("Email sent to " + recipient);
    }
}

public class SMSService : INotificationService
{
    public void SendNotification(string recipient, string message)
    {
        // Code to send an SMS
        Console.WriteLine("SMS sent to " + recipient);
    }
}

public class NotificationHandler
{
    private readonly INotificationService _notificationService;

    // Dependency Injection allows flexibility
    public NotificationHandler(INotificationService notificationService)
    {
        _notificationService = notificationService;
    }

    public void Notify(string recipient, string message)
    {
        _notificationService.SendNotification(recipient, message);  // Uses abstraction
    }
}
```