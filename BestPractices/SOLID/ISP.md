#### Interface Segregation Principle

*Definition:*

The Interface Segregation Principle (ISP) is a software design principle that states that clients should not be forced to depend on interfaces they do not use. This means that you should create small, specialized interfaces rather than large, general-purpose ones.

*Code Example:*

```csharp
public interface IMessage
{
    void Send(string message);
}

public interface IEmailMessage : IMessage
{
    string ToAddress { get; set; }
    string FromAddress { get; set; }
    string Subject { get; set; }
}

public interface ISmsMessage : IMessage
{
    string PhoneNumber { get; set; }
}

public class EmailMessage : IEmailMessage
{
    public string ToAddress { get; set; }
    public string FromAddress { get; set; }
    public string Subject { get; set; }

    public void Send(string message)
    {
        // Send email message
    }
}

public class SmsMessage : ISmsMessage
{
    public string PhoneNumber { get; set; }

    public void Send(string message)
    {
        // Send SMS message
    }
}

public class MessageSender
{
    public void SendMessage(IMessage message)
    {
        message.Send("Hello, world!");
    }
}
```

In this example, the MessageSender class sends a message using the IMessage interface. This means that it does not need to know or care whether the message is an email message or an SMS message. The EmailMessage and SmsMessage classes can both be used with the MessageSender class, since they both implement the IMessage interface. This demonstrates the Interface Segregation Principle, since the MessageSender class is not forced to depend on the additional properties that are specific to email messages or SMS messages. It only needs to know about the Send() method, which is all it needs to use.
